# Information Architecture
# PakeAja: Manajemen Proyek & Portal Client

**Versi:** 1.0
**Tanggal:** 28 Oktober 2025
**Untuk:** UI/UX Designer & Development Team

---

## Overview

Dokumen ini mendefin isikan struktur informasi dan navigasi untuk kedua sisi platform PakeAja:
1. **Dashboard Kontraktor** (full access, project management)
2. **Portal Client** (view-only, project monitoring)

---

## 1. Kontraktor Dashboard - Sitemap

```
┌─────────────────────────────────────────────────────────────┐
│                    KONTRAKTOR DASHBOARD                     │
└─────────────────────────────────────────────────────────────┘

├── 🏠 Dashboard (Homepage)
│   ├── Overview Stats (KPI cards)
│   ├── Recent Projects (list/grid)
│   ├── Budget Chart
│   └── Quick Actions

├── 📁 Proyek
│   ├── Daftar Proyek (List View)
│   │   ├── Filter by Status
│   │   ├── Search by Name/Client
│   │   └── Sort options
│   │
│   ├── Buat Proyek Baru (Modal/Page)
│   │   └── Form: Info dasar, Client, Timeline, Budget
│   │
│   └── Detail Proyek ─────────────────────┐
│       ├── Tab: Overview                  │
│       │   ├── Project Info Card          │
│       │   ├── Progress Card              │
│       │   ├── Recent Activity            │
│       │   └── Quick Stats                │
│       │                                  │
│       ├── Tab: Material                  │
│       │   ├── Tambah Material (Modal)    │
│       │   ├── Material Tracker (Kanban/List) │
│       │   └── Material Detail (Modal)    │
│       │                                  │
│       ├── Tab: Foto                      │
│       │   ├── Upload Foto (Modal)        │
│       │   ├── Gallery (Grid/List/Timeline) │
│       │   └── Lightbox View             │
│       │                                  │
│       ├── Tab: Timeline                  │
│       │   ├── Milestone List             │
│       │   ├── Add Milestone (Modal)      │
│       │   └── Timeline Visualization     │
│       │                                  │
│       ├── Tab: Budget                    │
│       │   ├── Budget Overview            │
│       │   ├── Budget Breakdown           │
│       │   ├── Log Expense (Modal)        │
│       │   └── Budget Chart               │
│       │                                  │
│       └── Tab: Invoice                   │
│           ├── Invoice List               │
│           ├── Generate Invoice (Modal)   │
│           └── Invoice Detail + PDF       │

├── 📦 Material (Global view - across all projects)
│   ├── Daftar Semua Material
│   ├── Filter by Status, Project
│   └── Material Analytics (optional Phase 2)

├── 👥 Tim (Phase 2)
│   ├── Daftar User
│   ├── Invite User
│   └── Role Management

├── 💰 Invoice (Global view)
│   ├── Daftar Semua Invoice
│   ├── Filter by Status, Project
│   └── Analytics (Paid, Pending, Overdue)

└── ⚙️ Settings
    ├── Company Profile
    │   ├── Edit Company Info
    │   ├── Upload Logo
    │   └── Branding Colors
    ├── User Profile
    │   ├── Edit Name, Email, Phone
    │   ├── Change Password
    │   └── Notification Preferences
    └── Subscription
        ├── Current Plan
        ├── Usage Stats
        └── Upgrade/Downgrade
```

---

## 2. Client Portal - Sitemap

```
┌─────────────────────────────────────────────────────────────┐
│                      CLIENT PORTAL                          │
│               (Project Owner View-Only)                     │
└─────────────────────────────────────────────────────────────┘

├── 🏠 Overview (Homepage)
│   ├── Hero Card (Featured project status)
│   ├── Alert Banner (if any issues)
│   ├── Quick Stats (4 cards)
│   ├── Recent Updates (Timeline)
│   └── At-a-Glance Progress by Area

├── 📦 Material
│   ├── Material Status Tracker (Kanban/Timeline)
│   ├── Filter by Status
│   └── Material Detail (Modal)
│       ├── Info
│       ├── Status Timeline
│       ├── Supplier
│       ├── Photos
│       └── Delay Reason (if any)

├── 📷 Foto
│   ├── Gallery (Grid view)
│   ├── Filter by Area, Type, Date
│   ├── Lightbox View
│   │   ├── Navigation (prev/next)
│   │   ├── Photo Info
│   │   └── Before/After Comparison
│   └── Download (Single or Bulk)

├── 📅 Timeline
│   ├── Project Timeline Visual
│   ├── Milestone List
│   │   ├── Planned vs Actual Date
│   │   └── Status Indicator
│   └── Delay Explanations (if any)

├── 💰 Budget
│   ├── Budget Overview (high-level)
│   │   ├── Total vs Spent vs Remaining
│   │   └── Visual Progress Bar
│   ├── Spending Pace Indicator
│   └── Breakdown by Category

└── 🧾 Invoice
    ├── Invoice List
    │   ├── Status, Amount, Due Date
    │   └── Download PDF
    └── Payment Instructions
        └── Bank Account Details
```

---

## 3. Authentication & Onboarding Flows

### Kontraktor Authentication

```
┌───────────────────────────┐
│   Login Page              │
│   - Login dengan Google   │
│   - OR Email + Password   │
│   - "Daftar" link         │
└───────────────────────────┘
            │
            ↓
┌───────────────────────────┐
│   First-Time Setup        │
│   1. Create Company       │
│   2. Upload Logo          │
│   3. Invite Team (optional)│
└───────────────────────────┘
            │
            ↓
┌───────────────────────────┐
│   Dashboard Homepage      │
└───────────────────────────┘
```

### Project Owner Authentication

```
┌───────────────────────────┐
│   Email Invitation        │
│   "Anda diundang ke       │
│    Portal Proyek..."      │
│   [Lihat Proyek] button   │
└───────────────────────────┘
            │
            ↓
┌───────────────────────────┐
│   Magic Link Login        │
│   (Auto-login via token)  │
└───────────────────────────┘
            │
            ↓
┌───────────────────────────┐
│   Welcome Modal           │
│   (First-time only)       │
│   - Quick tour option     │
│   - Notification prefs    │
└───────────────────────────┘
            │
            ↓
┌───────────────────────────┐
│   Portal Dashboard        │
└───────────────────────────┘
```

---

## 4. Navigation Patterns

### Kontraktor - Desktop Navigation

```
┌──────────────────────────────────────────────────────────────┐
│  [Logo] PakeAja  [Search...]      🔔 [Notifications] [Avatar]│
└──────────────────────────────────────────────────────────────┘
┌────────────┬─────────────────────────────────────────────────┐
│ Dashboard  │                                                 │
│ 🏠         │                                                 │
│            │                                                 │
│ Proyek     │         MAIN CONTENT AREA                      │
│ 📁         │                                                 │
│            │                                                 │
│ Material   │                                                 │
│ 📦         │                                                 │
│            │                                                 │
│ Tim        │                                                 │
│ 👥         │                                                 │
│            │                                                 │
│ Invoice    │                                                 │
│ 💰         │                                                 │
│            │                                                 │
│ Settings   │                                                 │
│ ⚙️         │                                                 │
│            │                                                 │
└────────────┴─────────────────────────────────────────────────┘
```

**Sidebar:** Collapsible, dengan icons + labels

### Kontraktor - Mobile Navigation

```
┌──────────────────────────────────┐
│  [≡ Menu] PakeAja     🔔 [Avatar]│
├──────────────────────────────────┤
│                                  │
│                                  │
│       MAIN CONTENT               │
│                                  │
│                                  │
│                                  │
├──────────────────────────────────┤
│ 🏠   📁   📦   👥   ⚙️          │
│ Home Proyek Mat Tim  Set         │
└──────────────────────────────────┘
```

**Bottom Tab Bar:** 5 main sections

### Client Portal - Desktop Navigation

```
┌──────────────────────────────────────────────────────────────┐
│  [Logo] PakeAja  [Project Name ▼]   🔔 [Notifications] [Avatar]│
└──────────────────────────────────────────────────────────────┘
┌────────────┬─────────────────────────────────────────────────┐
│ Overview   │                                                 │
│ 🏠         │                                                 │
│            │                                                 │
│ Material   │                                                 │
│ 📦         │         MAIN CONTENT AREA                      │
│            │                                                 │
│ Foto       │                                                 │
│ 📷         │                                                 │
│            │                                                 │
│ Timeline   │                                                 │
│ 📅         │                                                 │
│            │                                                 │
│ Budget     │                                                 │
│ 💰         │                                                 │
│            │                                                 │
│ Invoice    │                                                 │
│ 🧾         │                                                 │
│            │                                                 │
└────────────┴─────────────────────────────────────────────────┘
```

**Simpler sidebar** (fewer items vs kontraktor)

### Client Portal - Mobile Navigation

```
┌──────────────────────────────────┐
│  [Logo] PakeAja          🔔 [×]  │
├──────────────────────────────────┤
│                                  │
│                                  │
│       MAIN CONTENT               │
│                                  │
│                                  │
│                                  │
├──────────────────────────────────┤
│ 🏠   📦   📷   📅   💰          │
│ Over Mat  Foto Time Bud          │
└──────────────────────────────────┘
```

**Bottom Tab Bar:** 5 sections (simplified labels)

---

## 5. Key User Flows (Reference)

### Flow 1: Kontraktor Create Project → Invite Client

```
Dashboard
  → Click "Buat Proyek Baru"
    → Fill Form (Name, Client, Timeline, Budget)
      → Submit
        → Redirect to Project Detail
          → Click "Invite Client"
            → Enter Email, Set Permission
              → Send Invitation
                → Success: "Invitation sent to client@email.com"
```

### Flow 2: Project Owner Check Progress

```
Receive Email Invitation
  → Click "Lihat Proyek"
    → Auto-login (magic link)
      → Welcome Modal (first time)
        → Skip or Take Tour
          → Portal Dashboard
            → See Overall Progress (65%)
              → View Recent Photos
                → Click Photo → Lightbox
                  → Swipe through gallery
                    → Close
                      → Check Material Status
                        → See "All materials delivered ✓"
                          → Feel confident, no need to call contractor!
```

### Flow 3: Field Supervisor Upload Photo (Mobile)

```
Open PakeAja on Phone
  → Navigate to Project
    → Tab "Foto"
      → Click "+ Upload Foto"
        → Camera opens OR file picker
          → Take/select photo
            → Form:
              - Area: Lobby (dropdown)
              - Type: Progress (dropdown)
              - Caption: (optional)
              - Geolocation: Auto-captured ✓
            → Click "Upload"
              → Success: "Foto berhasil di-upload"
                → Notification sent to PM & Client
```

---

## 6. Content Hierarchy (What's Most Important?)

### Kontraktor Dashboard (Priority Order)

1. **Critical:** Projects on-time/delayed status
2. **High:** Budget utilization, upcoming milestones
3. **Medium:** Recent activity, team assignments
4. **Low:** Historical data, analytics

### Project Detail Page (Priority Order)

1. **Critical:** Progress %, status, days remaining
2. **High:** Material status, recent photos, budget
3. **Medium:** Timeline, team, documents
4. **Low:** Detailed logs, change history

### Client Portal (Priority Order)

1. **Critical:** Overall status (On Track / Delayed), Progress %
2. **High:** Photos, Material status, Timeline
3. **Medium:** Budget, Invoices
4. **Low:** Documentation, History

---

## 7. URL Structure

### Kontraktor Dashboard

```
/dashboard                           - Homepage
/projects                            - List all projects
/projects/new                        - Create new project
/projects/[id]                       - Project detail (Overview tab)
/projects/[id]/materials             - Material tab
/projects/[id]/photos                - Photos tab
/projects/[id]/timeline              - Timeline tab
/projects/[id]/budget                - Budget tab
/projects/[id]/invoices              - Invoice tab
/projects/[id]/settings              - Project settings

/materials                           - Global material view
/materials/[id]                      - Material detail

/invoices                            - Global invoice view
/invoices/[id]                       - Invoice detail

/team                                - Team management
/team/invite                         - Invite user

/settings                            - Settings homepage
/settings/company                    - Company profile
/settings/profile                    - User profile
/settings/subscription               - Subscription management
```

### Client Portal

```
/portal                              - Portal homepage (Overview)
/portal/materials                    - Material tracker
/portal/photos                       - Photo gallery
/portal/timeline                     - Timeline view
/portal/budget                       - Budget summary
/portal/invoices                     - Invoice list
/portal/invoices/[id]                - Invoice detail

/portal/settings                     - Notification preferences
```

**Note:** Portal URLs bisa pakai subdomain jika perlu:
- `client.pakeaja.com` untuk portal
- `app.pakeaja.com` untuk kontraktor dashboard

---

## 8. State Management Considerations

### What Needs to be Global State?

**Auth State:**
- Current user (id, name, email, role, company)
- Session token
- Permissions

**UI State:**
- Sidebar collapsed/expanded
- Theme (dark mode - default)
- Language (Bahasa Indonesia)
- Notification preferences

**Data State:**
- Current project (when in project detail)
- Active filters (projects list, material list, etc.)
- Upload queue (photos pending upload)

### What's Local/Component State?

- Form values
- Modal open/closed
- Dropdown expanded
- Loading states
- Error messages

### What's Server State (React Query / SWR)?

- Projects list
- Project detail
- Materials
- Photos
- Invoices
- User data
- Notifications

---

## 9. Breadcrumbs & Back Navigation

### Kontraktor

```
Dashboard > Proyek > Grand Indonesia Mall > Material

[Dashboard] > [Proyek] > [Grand Indonesia Mall] > [Material]
   ↑            ↑              ↑                      ↑
   link         link           link                 current
```

### Client Portal

**No breadcrumbs needed** (flat hierarchy, only 1 project at a time)

Use **← Back** button or browser back

---

## 10. Empty States & First-Time Experience

### Kontraktor - Empty Project List

```
┌─────────────────────────────────────┐
│         [Illustration]              │
│                                     │
│    Belum Ada Proyek                 │
│                                     │
│  Mulai dengan membuat proyek        │
│  pertama Anda                       │
│                                     │
│    [+ Buat Proyek Baru]             │
│                                     │
│    atau [Import dari Excel]         │
│         (Phase 2)                   │
└─────────────────────────────────────┘
```

### Client Portal - First Visit

```
┌─────────────────────────────────────┐
│   Selamat Datang di Portal Proyek!  │
│                                     │
│  ✓ Lihat progres real-time          │
│  ✓ Track material & budget          │
│  ✓ Download foto & dokumen          │
│                                     │
│  [Mulai Tour] atau [Lewati]        │
└─────────────────────────────────────┘
```

---

## 11. Search & Filter Patterns

### Global Search (Header)

- Search across: Projects, Clients, Materials
- Shows recent searches
- Keyboard shortcut: Cmd+K / Ctrl+K

### Project List Filters

```
[Search by name or client...]

Status: [Semua ▼]  [Aktif]  [Selesai]  [Delayed]

Sort by: [Terbaru ▼]  [Nama]  [Progress %]  [Budget]

View: [Grid] [List]
```

### Material List Filters

```
Status: [Semua ▼] [Planned] [Ordered] [Delivered] [Delayed]

Project: [Semua ▼] [Project A] [Project B] ...
```

---

## 12. Notifications & Alerts

### Notification Types

**Kontraktor:**
- Client login pertama kali
- Client commented on photo
- Material delayed
- Invoice overdue
- Milestone due tomorrow

**Client Portal:**
- New photos uploaded
- Material status changed
- Milestone completed
- Invoice issued
- Project delayed

### Notification UI

```
┌────────────────────────────────────┐
│  🔔 Notifications (3 unread)       │
├────────────────────────────────────┤
│  ● 3 foto baru di-upload           │
│    Grand Indonesia Mall            │
│    2 jam lalu                      │
├────────────────────────────────────┤
│  ● Material "Primer" delivered     │
│    Plaza Senayan                   │
│    5 jam lalu                      │
├────────────────────────────────────┤
│    Invoice #INV-001 dibayar        │
│    Grand Indonesia Mall            │
│    Kemarin                         │
└────────────────────────────────────┘
```

---

## Summary untuk UI/UX Designer

**Core Screens Prioritas (Design ini dulu):**

1. ✅ Login Page (Kontraktor)
2. ✅ Dashboard Homepage (Kontraktor)
3. ✅ Daftar Proyek (Kontraktor)
4. ✅ Project Detail - Overview Tab (Kontraktor)
5. ✅ Project Detail - Material Tab (Kontraktor)
6. ✅ Project Detail - Foto Tab (Kontraktor)
7. ✅ Portal Dashboard (Client)
8. ✅ Portal - Material Tracker (Client)
9. ✅ Portal - Photo Gallery (Client)
10. ✅ Upload Photo Modal (Mobile - Supervisor)

**Navigation Components:**
- Sidebar (desktop)
- Bottom Tab Bar (mobile)
- Breadcrumbs
- Top Bar dengan Search & Notifications

**Modals/Overlays:**
- Create Project
- Add Material
- Upload Photo
- Generate Invoice
- Invite Client

Refer to `UI-UX-Design-Brief.md` untuk design specs lengkap.

---

**Next Steps:**
1. UI/UX designer create wireframes based on this sitemap
2. Validate flows dengan user personas
3. Iterate based on feedback
4. Move to high-fidelity mockups
