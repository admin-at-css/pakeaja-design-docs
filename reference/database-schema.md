# Database Schema Design

**Last Updated:** October 28, 2025
**Status:** Initial Design (Brainstorming Phase)

---

## Overview

This document defines the database schema for PakeAja's Project Management and Client Portal modules. The schema is designed to support a two-sided platform where contractors manage projects and project owners view transparent updates.

**Database:** PostgreSQL (via Prisma ORM)

---

## Design Principles

1. **Separation of Concerns:** Contractor data vs Project Owner data clearly separated
2. **Audit Trail:** Track who created/updated records and when (createdAt, updatedAt)
3. **Soft Deletes:** Never truly delete data (use deletedAt field)
4. **Scalability:** Design for multi-tenant (each contractor company is isolated)
5. **Flexibility:** Support future features without major schema changes

---

## Core Entities

### 1. User & Authentication

```prisma
model User {
  id            String    @id @default(cuid())
  email         String    @unique
  name          String?
  phone         String?
  role          UserRole
  companyId     String?   // Null for project owners, set for contractor employees

  // OAuth fields
  googleId      String?   @unique
  emailVerified DateTime?

  // Profile
  avatar        String?
  language      String    @default("id") // "id" = Indonesian
  timezone      String    @default("Asia/Jakarta")

  // Relations
  company       Company?  @relation(fields: [companyId], references: [id])

  // What this user has created/managed
  projectsManaged     Project[]         @relation("ProjectManager")
  materialsCreated    Material[]
  photosUploaded      ProjectPhoto[]
  invoicesCreated     Invoice[]

  // Project owner access
  projectAccess       ProjectAccess[]   // Which projects this user can view in Client Portal

  // Timestamps
  createdAt     DateTime  @default(now())
  updatedAt     DateTime  @updatedAt
  deletedAt     DateTime? // Soft delete
}

enum UserRole {
  SUPER_ADMIN       // PakeAja platform admin
  COMPANY_OWNER     // Painting company owner (full access to their company)
  PROJECT_MANAGER   // Manages specific projects
  FIELD_SUPERVISOR  // On-site updates only
  SALES_REP         // Sales module access only
  ACCOUNTANT        // Finance/invoicing access only
  PROJECT_OWNER     // Client (portal view-only access)
}
```

---

### 2. Company (Painting Contractor)

```prisma
model Company {
  id              String    @id @default(cuid())
  name            String
  slug            String    @unique // e.g., "abc-painting" for subdomain

  // Business info
  registrationNumber  String?  // Indonesian company registration (NIB/SIUP)
  taxId               String?  // NPWP
  address             String?
  city                String?
  province            String?
  postalCode          String?
  phone               String?
  email               String?
  website             String?

  // Branding
  logo            String?
  primaryColor    String?   @default("#3B82F6")

  // Subscription
  plan            SubscriptionPlan  @default(FREE)
  subscriptionStatus String?  // "active", "trial", "cancelled"
  trialEndsAt     DateTime?
  subscriptionEndsAt DateTime?

  // Settings
  defaultCurrency String    @default("IDR")
  defaultLanguage String    @default("id")

  // Relations
  users           User[]
  projects        Project[]
  materials       Material[]
  suppliers       Supplier[]

  // Timestamps
  createdAt       DateTime  @default(now())
  updatedAt       DateTime  @updatedAt
  deletedAt       DateTime?
}

enum SubscriptionPlan {
  FREE        // 1 active project, limited features
  STARTER     // 5 active projects
  BUSINESS    // 20 active projects
  ENTERPRISE  // Unlimited
}
```

---

### 3. Project

**The core entity that everything else relates to.**

```prisma
model Project {
  id              String    @id @default(cuid())
  companyId       String

  // Basic Info
  name            String
  description     String?   @db.Text
  projectNumber   String    @unique  // e.g., "PRJ-2025-001"

  // Client Info
  clientName      String
  clientEmail     String?
  clientPhone     String?
  clientCompany   String?   // "Grand Indonesia Mall"

  // Location
  address         String?
  city            String?
  province        String?
  latitude        Float?
  longitude       Float?

  // Timeline
  startDate       DateTime?
  estimatedEndDate DateTime?
  actualEndDate   DateTime?

  // Status
  status          ProjectStatus @default(PLANNING)

  // Budget
  totalBudget     Float?
  currency        String    @default("IDR")

  // Team
  projectManagerId String?

  // Relations
  company         Company   @relation(fields: [companyId], references: [id])
  projectManager  User?     @relation("ProjectManager", fields: [projectManagerId], references: [id])

  materials       Material[]
  areas           ProjectArea[]
  photos          ProjectPhoto[]
  milestones      Milestone[]
  invoices        Invoice[]
  budgetItems     BudgetItem[]
  documents       ProjectDocument[]
  comments        Comment[]
  changeOrders    ChangeOrder[]
  qaChecklists    QAChecklist[]
  warranties      Warranty[]

  // Client Portal access
  projectAccess   ProjectAccess[]

  // Timestamps
  createdAt       DateTime  @default(now())
  updatedAt       DateTime  @updatedAt
  deletedAt       DateTime?

  @@index([companyId])
  @@index([status])
}

enum ProjectStatus {
  PLANNING      // Not started yet
  IN_PROGRESS   // Active work
  ON_HOLD       // Paused (weather, client request, etc.)
  DELAYED       // Behind schedule
  COMPLETED     // Work finished
  CLOSED        // Fully closed (invoiced, warranty period started)
  CANCELLED     // Cancelled before completion
}
```

---

### 4. ProjectAccess (Client Portal Permissions)

**Controls which project owners can see which projects.**

```prisma
model ProjectAccess {
  id          String    @id @default(cuid())
  projectId   String
  userId      String    // Project owner's user ID

  // Access level
  accessLevel AccessLevel @default(VIEWER)

  // What they can do (granular permissions)
  canComment       Boolean @default(true)
  canDownload      Boolean @default(true)
  canApproveChanges Boolean @default(false) // Change orders

  // Invitation
  invitedBy   String?   // User ID who sent invitation
  invitedAt   DateTime?
  acceptedAt  DateTime? // When they first logged in

  // Relations
  project     Project   @relation(fields: [projectId], references: [id])
  user        User      @relation(fields: [userId], references: [id])

  // Timestamps
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt

  @@unique([projectId, userId])
  @@index([userId])
}

enum AccessLevel {
  VIEWER      // Can only view
  COMMENTER   // Can view and comment
  APPROVER    // Can view, comment, approve change orders
}
```

---

### 5. Material

**Materials used in the project (paint, primer, tools).**

```prisma
model Material {
  id              String    @id @default(cuid())
  projectId       String
  companyId       String

  // Material details
  name            String    // "Nippon Weathershield White"
  category        MaterialCategory
  brand           String?
  productCode     String?   // Manufacturer's SKU
  unit            String    @default("liter") // "liter", "kg", "gallon", "can"

  // Quantity
  quantityPlanned Float
  quantityOrdered Float     @default(0)
  quantityDelivered Float   @default(0)
  quantityUsed    Float     @default(0)

  // Cost
  unitPrice       Float?
  totalCost       Float?    // quantityPlanned * unitPrice
  currency        String    @default("IDR")

  // Supplier
  supplierId      String?

  // Status tracking
  status          MaterialStatus @default(PLANNED)

  // Dates
  orderedDate     DateTime?
  expectedDeliveryDate DateTime?
  actualDeliveryDate   DateTime?

  // Technical Data Sheet
  tdsUrl          String?   // Link to Technical Data Sheet

  // Notes
  notes           String?   @db.Text

  // Relations
  project         Project   @relation(fields: [projectId], references: [id])
  company         Company   @relation(fields: [companyId], references: [id])
  supplier        Supplier? @relation(fields: [supplierId], references: [id])

  createdBy       String?
  creator         User?     @relation(fields: [createdBy], references: [id])

  photos          MaterialPhoto[]

  // Timestamps
  createdAt       DateTime  @default(now())
  updatedAt       DateTime  @updatedAt
  deletedAt       DateTime?

  @@index([projectId])
  @@index([status])
}

enum MaterialCategory {
  PAINT         // Topcoat paint
  PRIMER        // Primer/undercoat
  PUTTY         // Wall putty/filler
  SEALER        // Sealers
  THINNER       // Thinners/solvents
  TOOL          // Brushes, rollers, tape
  EQUIPMENT     // Spray guns, scaffolding
  OTHER
}

enum MaterialStatus {
  PLANNED       // In project plan, not ordered yet
  ORDERED       // Purchase order sent
  IN_PRODUCTION // Custom/special order being manufactured
  IN_TRANSIT    // Shipped, on the way
  DELIVERED     // Arrived on site
  IN_USE        // Currently being applied
  FULLY_USED    // All quantity consumed
  CANCELLED     // Order cancelled
}
```

---

### 6. Supplier

```prisma
model Supplier {
  id          String    @id @default(cuid())
  companyId   String

  name        String
  contactName String?
  email       String?
  phone       String?
  address     String?
  website     String?

  // Relations
  company     Company   @relation(fields: [companyId], references: [id])
  materials   Material[]

  // Timestamps
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt
  deletedAt   DateTime?
}
```

---

### 7. ProjectArea (Zones/Floors)

**Breakdown project into areas for granular progress tracking.**

```prisma
model ProjectArea {
  id          String    @id @default(cuid())
  projectId   String

  name        String    // "Lobby", "Floor 2", "Exterior Wall A"
  description String?

  // Size
  areaSize    Float?    // Square meters

  // Progress
  progress    Float     @default(0) // 0-100 percentage

  // Status
  status      AreaStatus @default(NOT_STARTED)

  // Dates
  startDate   DateTime?
  endDate     DateTime?

  // Relations
  project     Project   @relation(fields: [projectId], references: [id])
  photos      ProjectPhoto[]

  // Timestamps
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt

  @@index([projectId])
}

enum AreaStatus {
  NOT_STARTED
  PREP_IN_PROGRESS      // Surface preparation
  PRIMER_IN_PROGRESS    // Primer application
  TOPCOAT_IN_PROGRESS   // Topcoat application
  QA_INSPECTION         // Quality check
  COMPLETED
  REWORK_NEEDED         // Failed QA, needs rework
}
```

---

### 8. ProjectPhoto

**Progress photos - The heart of the Client Portal!**

```prisma
model ProjectPhoto {
  id          String    @id @default(cuid())
  projectId   String
  areaId      String?   // Optional: link to specific area

  // File info
  url         String    // Cloud storage URL (S3, Cloudinary, etc.)
  thumbnailUrl String?  // Optimized thumbnail
  filename    String
  fileSize    Int?      // Bytes
  mimeType    String?   // "image/jpeg"

  // Metadata
  caption     String?
  description String?   @db.Text

  // Photo type
  photoType   PhotoType @default(PROGRESS)

  // Location & time
  latitude    Float?
  longitude   Float?
  takenAt     DateTime  @default(now())

  // Who uploaded
  uploadedBy  String

  // Relations
  project     Project   @relation(fields: [projectId], references: [id])
  area        ProjectArea? @relation(fields: [areaId], references: [id])
  uploader    User      @relation(fields: [uploadedBy], references: [id])

  // Timestamps
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt
  deletedAt   DateTime?

  @@index([projectId])
  @@index([takenAt])
}

enum PhotoType {
  BEFORE        // Before starting work
  PROGRESS      // During work
  AFTER         // Completed work
  QA_INSPECTION // Quality assurance photos
  ISSUE         // Problem/defect photos
  MATERIAL      // Material delivery photos
  OTHER
}
```

---

### 9. MaterialPhoto

**Photos of delivered materials (proof of quality brands).**

```prisma
model MaterialPhoto {
  id          String    @id @default(cuid())
  materialId  String

  url         String
  thumbnailUrl String?
  caption     String?

  uploadedBy  String

  material    Material  @relation(fields: [materialId], references: [id])

  createdAt   DateTime  @default(now())

  @@index([materialId])
}
```

---

### 10. Milestone

**Key project milestones for timeline tracking.**

```prisma
model Milestone {
  id              String    @id @default(cuid())
  projectId       String

  name            String    // "Site Preparation Complete"
  description     String?   @db.Text

  // Timeline
  plannedDate     DateTime
  actualDate      DateTime?

  // Status
  status          MilestoneStatus @default(PENDING)

  // Progress
  percentageWeight Float   @default(0) // Contribution to overall project progress (0-100)

  // Relations
  project         Project   @relation(fields: [projectId], references: [id])

  // Timestamps
  createdAt       DateTime  @default(now())
  updatedAt       DateTime  @updatedAt

  @@index([projectId])
}

enum MilestoneStatus {
  PENDING       // Not reached yet
  IN_PROGRESS   // Currently working on
  COMPLETED     // Done
  DELAYED       // Behind schedule
  CANCELLED     // No longer applicable
}
```

---

### 11. BudgetItem

**Detailed budget breakdown.**

```prisma
model BudgetItem {
  id          String    @id @default(cuid())
  projectId   String

  category    BudgetCategory
  itemName    String
  description String?

  // Amounts
  budgetedAmount  Float
  actualAmount    Float   @default(0)
  currency        String  @default("IDR")

  // Relations
  project     Project   @relation(fields: [projectId], references: [id])

  // Timestamps
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt

  @@index([projectId])
}

enum BudgetCategory {
  MATERIALS
  LABOR
  EQUIPMENT
  TRANSPORTATION
  OVERHEAD
  PROFIT_MARGIN
  OTHER
}
```

---

### 12. Invoice

**Payment tracking.**

```prisma
model Invoice {
  id              String    @id @default(cuid())
  projectId       String

  invoiceNumber   String    @unique  // "INV-2025-001"

  // Amounts
  amount          Float
  currency        String    @default("IDR")
  taxAmount       Float?    // VAT/PPN
  totalAmount     Float     // amount + taxAmount

  // Dates
  issueDate       DateTime  @default(now())
  dueDate         DateTime
  paidDate        DateTime?

  // Status
  status          InvoiceStatus @default(DRAFT)

  // Payment
  paymentMethod   String?   // "Bank Transfer", "Check", etc.
  paymentReference String?  // Transaction ID

  // Documents
  pdfUrl          String?   // Generated PDF

  // Notes
  notes           String?   @db.Text

  // Relations
  project         Project   @relation(fields: [projectId], references: [id])

  createdBy       String?
  creator         User?     @relation(fields: [createdBy], references: [id])

  // Timestamps
  createdAt       DateTime  @default(now())
  updatedAt       DateTime  @updatedAt

  @@index([projectId])
  @@index([status])
}

enum InvoiceStatus {
  DRAFT         // Not sent yet
  SENT          // Sent to client
  VIEWED        // Client opened it
  OVERDUE       // Past due date
  PAID          // Fully paid
  PARTIALLY_PAID // Partial payment received
  CANCELLED     // Cancelled
}
```

---

### 13. ChangeOrder

**Scope changes during project.**

```prisma
model ChangeOrder {
  id              String    @id @default(cuid())
  projectId       String

  orderNumber     String    // "CO-001"
  title           String
  description     String    @db.Text

  // Impact
  costImpact      Float     // Positive (increase) or negative (decrease)
  timeImpact      Int?      // Days added/removed

  // Approval
  status          ChangeOrderStatus @default(PENDING)
  requestedBy     String    // User ID
  approvedBy      String?   // Project owner user ID
  approvedAt      DateTime?
  rejectedReason  String?

  // Relations
  project         Project   @relation(fields: [projectId], references: [id])

  // Timestamps
  createdAt       DateTime  @default(now())
  updatedAt       DateTime  @updatedAt

  @@index([projectId])
}

enum ChangeOrderStatus {
  PENDING       // Waiting for client approval
  APPROVED      // Client approved
  REJECTED      // Client rejected
  IMPLEMENTED   // Work completed
}
```

---

### 14. QAChecklist

**Quality assurance inspections.**

```prisma
model QAChecklist {
  id              String    @id @default(cuid())
  projectId       String

  checklistName   String    // "Final Inspection"
  inspectionDate  DateTime  @default(now())

  // Inspector
  inspectorId     String

  // Overall result
  overallStatus   QAStatus  @default(PENDING)
  score           Float?    // 0-100 or 0-10

  // Checklist items
  items           QAChecklistItem[]

  // Notes
  notes           String?   @db.Text

  // Sign-off
  signedOffAt     DateTime?

  // Relations
  project         Project   @relation(fields: [projectId], references: [id])
  inspector       User      @relation(fields: [inspectorId], references: [id])

  // Timestamps
  createdAt       DateTime  @default(now())
  updatedAt       DateTime  @updatedAt

  @@index([projectId])
}

enum QAStatus {
  PENDING       // Not inspected yet
  PASSED        // All checks passed
  PASSED_WITH_NOTES // Passed but minor issues noted
  FAILED        // Failed, rework required
}

model QAChecklistItem {
  id          String    @id @default(cuid())
  checklistId String

  itemName    String    // "Surface preparation adequate"
  category    String?   // "Preparation", "Application", "Finish"

  status      ItemStatus @default(PENDING)
  notes       String?

  checklist   QAChecklist @relation(fields: [checklistId], references: [id])

  @@index([checklistId])
}

enum ItemStatus {
  PENDING
  PASS
  FAIL
  NOT_APPLICABLE
}
```

---

### 15. Comment

**Comments and discussions on projects.**

```prisma
model Comment {
  id          String    @id @default(cuid())
  projectId   String

  content     String    @db.Text

  // Threading
  parentId    String?   // For replies

  // Who posted
  authorId    String

  // Visibility
  visibleToClient Boolean @default(false) // Show in Client Portal?

  // Relations
  project     Project   @relation(fields: [projectId], references: [id])
  author      User      @relation(fields: [authorId], references: [id])
  parent      Comment?  @relation("CommentReplies", fields: [parentId], references: [id])
  replies     Comment[] @relation("CommentReplies")

  // Timestamps
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt
  deletedAt   DateTime?

  @@index([projectId])
}
```

---

### 16. ProjectDocument

**Contracts, drawings, specs, certificates.**

```prisma
model ProjectDocument {
  id          String    @id @default(cuid())
  projectId   String

  title       String
  description String?

  // File
  url         String
  filename    String
  fileSize    Int?
  mimeType    String?   // "application/pdf", "image/jpeg"

  // Type
  documentType DocumentType

  // Visibility
  visibleToClient Boolean @default(false)

  // Upload info
  uploadedBy  String

  // Relations
  project     Project   @relation(fields: [projectId], references: [id])
  uploader    User      @relation(fields: [uploadedBy], references: [id])

  // Timestamps
  createdAt   DateTime  @default(now())
  updatedAt   DateTime  @updatedAt
  deletedAt   DateTime?

  @@index([projectId])
}

enum DocumentType {
  CONTRACT
  DRAWING
  SPECIFICATION
  PERMIT
  CERTIFICATE_BAST
  WARRANTY
  INVOICE
  RECEIPT
  TECHNICAL_DATASHEET
  OTHER
}
```

---

### 17. Warranty

**Post-project warranty tracking.**

```prisma
model Warranty {
  id              String    @id @default(cuid())
  projectId       String

  warrantyType    String    // "Painting work", "Material defect"
  description     String?   @db.Text

  // Coverage
  startDate       DateTime
  endDate         DateTime
  durationMonths  Int       // 12, 24, etc.

  // Coverage details
  coverageDetails String?   @db.Text

  // Claim history
  claims          WarrantyClaim[]

  // Relations
  project         Project   @relation(fields: [projectId], references: [id])

  // Timestamps
  createdAt       DateTime  @default(now())
  updatedAt       DateTime  @updatedAt

  @@index([projectId])
}

model WarrantyClaim {
  id              String    @id @default(cuid())
  warrantyId      String

  title           String
  description     String    @db.Text

  // Photos of issue
  photoUrls       String[]  // Array of URLs

  // Status
  status          ClaimStatus @default(SUBMITTED)

  // Resolution
  resolution      String?   @db.Text
  resolvedAt      DateTime?

  // Submitted by
  submittedBy     String    // Project owner user ID

  // Relations
  warranty        Warranty  @relation(fields: [warrantyId], references: [id])

  // Timestamps
  createdAt       DateTime  @default(now())
  updatedAt       DateTime  @updatedAt

  @@index([warrantyId])
}

enum ClaimStatus {
  SUBMITTED     // Claim submitted
  UNDER_REVIEW  // Contractor reviewing
  APPROVED      // Valid claim
  REJECTED      // Not covered
  SCHEDULED     // Repair scheduled
  RESOLVED      // Fixed
}
```

---

## Relationships Summary

```
Company (1) ─── (many) Users
Company (1) ─── (many) Projects
Company (1) ─── (many) Materials
Company (1) ─── (many) Suppliers

Project (1) ─── (many) Materials
Project (1) ─── (many) ProjectAreas
Project (1) ─── (many) ProjectPhotos
Project (1) ─── (many) Milestones
Project (1) ─── (many) BudgetItems
Project (1) ─── (many) Invoices
Project (1) ─── (many) ChangeOrders
Project (1) ─── (many) QAChecklists
Project (1) ─── (many) Comments
Project (1) ─── (many) ProjectDocuments
Project (1) ─── (many) Warranties
Project (1) ─── (many) ProjectAccess (Client Portal permissions)

User (1) ─── (many) ProjectAccess (as project owner)

Material (many) ─── (1) Supplier
Material (1) ─── (many) MaterialPhotos

ProjectArea (1) ─── (many) ProjectPhotos

QAChecklist (1) ─── (many) QAChecklistItems

Warranty (1) ─── (many) WarrantyClaims
```

---

## Indexes Strategy

**For fast queries:**

```sql
-- Project queries
CREATE INDEX idx_project_company ON Project(companyId);
CREATE INDEX idx_project_status ON Project(status);
CREATE INDEX idx_project_dates ON Project(startDate, estimatedEndDate);

-- Material tracking
CREATE INDEX idx_material_project ON Material(projectId);
CREATE INDEX idx_material_status ON Material(status);

-- Photos (frequently accessed in Client Portal)
CREATE INDEX idx_photo_project ON ProjectPhoto(projectId);
CREATE INDEX idx_photo_date ON ProjectPhoto(takenAt);

-- Client Portal access
CREATE INDEX idx_access_user ON ProjectAccess(userId);
CREATE INDEX idx_access_project ON ProjectAccess(projectId);

-- Invoices
CREATE INDEX idx_invoice_project ON Invoice(projectId);
CREATE INDEX idx_invoice_status ON Invoice(status);
```

---

## Data Privacy & Security Considerations

### 1. Multi-Tenancy Isolation
- Every query must filter by `companyId` to prevent data leaks between contractors
- Row-Level Security (RLS) in PostgreSQL (if needed)

### 2. Project Owner Access Control
- `ProjectAccess` table controls which users see which projects
- API must validate: "Does this user have access to this project?"

### 3. Sensitive Data
- **Hide from project owners:**
  * Contractor profit margins
  * Internal team notes
  * Supplier pricing details
- **Show to project owners:**
  * Total budget and spending
  * High-level cost breakdown
  * Material status and photos

### 4. Audit Trail
- All critical actions logged (who created/updated/deleted)
- `createdAt`, `updatedAt`, `deletedAt` timestamps on all tables

---

## Sample Queries

### Get all projects for a contractor
```sql
SELECT * FROM Project
WHERE companyId = 'xyz'
AND deletedAt IS NULL;
```

### Get all projects visible to a project owner
```sql
SELECT p.* FROM Project p
INNER JOIN ProjectAccess pa ON p.id = pa.projectId
WHERE pa.userId = 'abc' AND pa.deletedAt IS NULL;
```

### Get material status for a project (for Client Portal)
```sql
SELECT * FROM Material
WHERE projectId = 'proj123'
AND deletedAt IS NULL
ORDER BY status, name;
```

### Get recent progress photos
```sql
SELECT * FROM ProjectPhoto
WHERE projectId = 'proj123'
AND photoType IN ('PROGRESS', 'AFTER')
ORDER BY takenAt DESC
LIMIT 20;
```

---

## Next Steps

1. [ ] Review schema with your input - Any missing fields?
2. [ ] Convert to Prisma schema file (`schema.prisma`)
3. [ ] Set up PostgreSQL database
4. [ ] Generate Prisma Client
5. [ ] Create seed data for development
6. [ ] Write API endpoints to interact with this schema

---

## Notes

- **File Storage:** Photos/documents stored in cloud (S3/Cloudinary), only URLs in database
- **Currency:** Default to IDR, but support other currencies for international projects
- **Geolocation:** Store lat/long for projects and photos (useful for multi-site contractors)
- **Soft Deletes:** Use `deletedAt` instead of hard deletes for audit trail
- **Future:** Consider time-series database for analytics/reporting (module 5 - AI Assistant)

---
