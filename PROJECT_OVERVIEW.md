# PakeAja - Project Overview

---

**📚 Documentation Journey** | Step 1 of 8

[**→ Project Overview**](PROJECT_OVERVIEW.md) → [User Personas](USER_PERSONAS.md) → [Scope](SCOPE.md) → [Design Complexity](DESIGN_COMPLEXITY.md) → [User Flows](USER_FLOWS.md) → [Information Architecture](INFORMATION_ARCHITECTURE.md) → [Design Brief](DESIGN_BRIEF.md) → [PRD](PRD.md)

---

## What is PakeAja?

PakeAja adalah **B2B SaaS platform** yang dirancang untuk membantu perusahaan kontraktor pengecatan mengelola proyek skala besar secara lebih profesional dan transparan. Platform ini menyediakan dashboard lengkap untuk kontraktor dan client portal untuk project owners.

---

## The Problem We're Solving

### Current State: WhatsApp-Based Project Management

Kontraktor pengecatan Indonesia (especially SMEs) saat ini mengelola proyek dengan **WhatsApp groups**:

**Pain Points:**
- 📱 **Progress photos scattered** across WA chats (susah dicari, no organization)
- 💰 **Budget tracking in Excel** (manual, error-prone, not real-time)
- 📄 **Invoices sent as PDF via WA** (no tracking, lost messages, unprofessional)
- 📅 **Timeline updates verbal** (no accountability, client confusion)
- 👥 **No transparency** untuk clients (harus tanya PM: "Gimana progress-nya?")
- 🔍 **No audit trail** (can't prove apa yang dikomunikasikan kapan)

**Result:**
- Clients feel uninformed dan anxious (constantly asking for updates)
- Contractors spend jam-jam answering repetitive questions
- Disputes muncul ("I never said that!", "Where's the photo from last week?")
- Unprofessional image (hard to win larger contracts)

---

## The PakeAja Solution

### Two-Sided Platform Architecture

**1. Contractor Dashboard (Power Users)**
- **Project Management:** Create projects, set milestones, assign teams
- **Progress Tracking:** Upload before/after photos, update timeline, mark milestones complete
- **Material Management:** Track inventory, record usage, monitor supplier costs
- **Budget Tracking:** Real-time budget vs actual spending, expense categorization
- **Invoicing:** Generate professional invoices, link to milestones, send via platform
- **Reporting:** Create progress reports, share dengan clients automatically
- **Team Collaboration:** Assign roles (PM, site supervisor, finance), permission management

**2. Client Portal (Read-Heavy Interface)**
- **Dashboard Overview:** See all project metrics at a glance (progress %, budget status, timeline)
- **Progress Tracking:** Real-time project status updates (no need to call PM)
- **Photo Gallery:** Browse before/after photos organized by date, milestone, location
- **Budget Transparency:** See spending breakdown, compare to original budget
- **Milestone Tracker:** Upcoming milestones, completion status, payment schedules
- **Invoice Management:** View invoices, download PDFs, track payment status
- **Communication:** Message PM directly through platform (all logged)

---

## Target Users

### Primary Users: Painting Contractors in Indonesia

**Company Profile:**
- **Size:** SME (5-50 employees)
- **Projects:** Commercial, residential, industrial painting projects
- **Examples:** Office building repainting, apartment complex painting, mall renovations
- **Challenges:** Managing 3-10 concurrent projects, multiple clients, 10-30 workers per project

**User Demographics:**
- **Age:** 35-55 tahun (established businesses)
- **Tech Savvy:** Low-to-medium (use WhatsApp, Excel, tapi not complex software)
- **Education:** High school sampai bachelor's degree (practical experience > formal education)
- **Language:** Bahasa Indonesia (some English for technical terms)

**User Personas:**

Lihat [USER_PERSONAS.md](USER_PERSONAS.md) untuk detailed personas:
- **Budi** (Project Manager, 42 tahun) - Heavy platform user, manages daily operations
- **Siti** (Site Supervisor, 38 tahun) - Mobile user, uploads progress photos from field
- **Andi** (Finance Staff, 35 tahun) - Handles invoicing, budget tracking, payment management
- **Pak Hasan** (Project Owner, 50 tahun) - Client portal user, monitors project progress
- **Ibu Linda** (Finance Approver, 45 tahun) - Reviews dan approves invoices, checks budgets
- **David** (Property Manager, 40 tahun) - Oversees multiple projects, needs consolidated reporting

---

## Why Understanding Users Matters for Design

### Contractor Side (Complex, Data-Heavy)
Design Anda harus help contractors:
- ✅ **Work faster** - Save time vs WhatsApp/Excel (jika tool lebih lambat, they won't adopt)
- ✅ **Reduce errors** - Clear forms, validation, prevent budget mistakes
- ✅ **Look professional** - Contractors show this to clients to win contracts
- ✅ **Handle complexity** - Manage 10+ concurrent projects, 100s of photos, detailed budgets

**Design Considerations:**
- Power-user features (bulk actions, keyboard shortcuts, filters)
- Efficient workflows (minimal clicks for common tasks)
- Data visualization (charts, progress indicators, status at a glance)
- Mobile-responsive (supervisors use tablets/phones on-site)

---

### Client Side (Simple, Transparency-Focused)
Design Anda harus help clients:
- ✅ **Feel informed** - See progress tanpa calling PM every day
- ✅ **Build trust** - Transparent budget tracking, photo proof of work
- ✅ **Take action** - Approve milestones, review invoices, communicate easily
- ✅ **Reduce anxiety** - Clear status, timeline visibility, no surprises

**Design Considerations:**
- Simple navigation (clients are occasional users, not daily)
- Clear visual hierarchy (most important info first: progress %, budget status)
- Mobile-first (many clients check on phones)
- Non-technical language (friendly copy, helpful empty states)

---

## Design Success Criteria

**Design Anda successful jika:**

1. **Contractors adopt it** - It's faster than WhatsApp (they switch voluntarily)
2. **Clients use the portal** - Reduces "Gimana progress-nya?" phone calls by 80%+
3. **Non-tech users understand it** - 50+ tahun contractors can navigate tanpa training
4. **Platform looks professional** - Contractors confidently show it to clients untuk win larger contracts
5. **Design system scales** - Supports Phase 2 features (CRM, Inventory, Mobile App) tanpa redesign

**The wrong design = users abandon platform dan return to WhatsApp.**

---

## Questions Designers Often Have

### Q: Mengapa two-sided platform instead of one dashboard?
**A:** Contractors dan clients punya fundamentally different needs:
- **Contractors** need to INPUT data (photos, budgets, invoices) - complex, power-user UI
- **Clients** need to VIEW data (progress, spending) - simple, read-only UI
- Jika kita give clients access ke contractor dashboard, it's overwhelming dan confusing

### Q: Mengapa focus on painting contractors specifically?
**A:** Painting projects punya unique characteristics:
- Heavy photo documentation (before/after, progress tracking)
- Material-intensive (paint, primer, equipment tracking)
- Milestone-based payments (per floor completed, per building section)
- Generic PM tools don't fit this workflow

### Q: Apa biggest design challenge-nya?
**A:** Balancing simplicity untuk non-tech users dengan power features untuk daily operations. Contractors need efficiency (they're busy), tapi juga clarity (they're not tech-savvy). Avoid making it "dumbed down" (frustrating for power users) atau overly complex (intimidating for beginners).

---

## ➡️ Continue Reading

**[Next: User Personas →](USER_PERSONAS.md)**

---

*Last Updated: October 29, 2025*
