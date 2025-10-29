# PakeAja - Project Overview

## What is PakeAja?

PakeAja is a **B2B SaaS platform** designed to help painting contractor companies manage large-scale projects more professionally and transparently. The platform provides a comprehensive dashboard for contractors and a client portal for project owners.

---

## The Problem We're Solving

### Current State: WhatsApp-Based Project Management

Indonesian painting contractors (especially SMEs) currently manage multi-million rupiah projects using **WhatsApp groups**:

**Pain Points:**
- 📱 **Progress photos scattered** across WA chats (hard to find, no organization)
- 💰 **Budget tracking in Excel** (manual, error-prone, not real-time)
- 📄 **Invoices sent as PDF via WA** (no tracking, lost messages, unprofessional)
- 📅 **Timeline updates verbal** (no accountability, client confusion)
- 👥 **No transparency** for clients (have to ask PM: "Gimana progress-nya?")
- 🔍 **No audit trail** (can't prove what was communicated when)

**Result:**
- Clients feel uninformed and anxious (constantly asking for updates)
- Contractors spend hours answering repetitive questions
- Disputes arise ("I never said that!", "Where's the photo from last week?")
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
- **Reporting:** Create progress reports, share with clients automatically
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
- **Projects:** Rp 100 juta - Rp 2 miliar per project (commercial, residential, industrial)
- **Examples:** Office building repainting, apartment complex painting, mall renovations
- **Challenges:** Managing 3-10 concurrent projects, multiple clients, 10-30 workers per project

**User Demographics:**
- **Age:** 35-55 years old (established businesses)
- **Tech Savvy:** Low-to-medium (use WhatsApp, Excel, but not complex software)
- **Education:** High school to bachelor's degree (practical experience > formal education)
- **Language:** Bahasa Indonesia (some English for technical terms)

**User Personas:**

See [USER_PERSONAS.md](USER_PERSONAS.md) for detailed personas:
- **Budi** (Project Manager, 42 years) - Heavy platform user, manages daily operations
- **Siti** (Site Supervisor, 38 years) - Mobile user, uploads progress photos from field
- **Andi** (Finance Staff, 35 years) - Handles invoicing, budget tracking, payment management
- **Pak Hasan** (Project Owner, 50 years) - Client portal user, monitors project progress
- **Ibu Linda** (Finance Approver, 45 years) - Reviews and approves invoices, checks budgets
- **David** (Property Manager, 40 years) - Oversees multiple projects, needs consolidated reporting

---

## Why Understanding Users Matters for Design

### Contractor Side (Complex, Data-Heavy)
Your designs must help contractors:
- ✅ **Work faster** - Save time vs WhatsApp/Excel (if tool is slower, they won't adopt)
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
Your designs must help clients:
- ✅ **Feel informed** - See progress without calling PM every day
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

**Your design is successful if:**

1. **Contractors adopt it** - It's faster than WhatsApp (they switch voluntarily)
2. **Clients use the portal** - Reduces "Gimana progress-nya?" phone calls by 80%+
3. **Non-tech users understand it** - 50+ year old contractors can navigate without training
4. **Platform looks professional** - Contractors confidently show it to clients to win larger contracts
5. **Design system scales** - Supports Phase 2 features (CRM, Inventory, Mobile App) without redesign

**The wrong design = users abandon platform and return to WhatsApp.**

---

## Questions Designers Often Have

### Q: Why two-sided platform instead of one dashboard?
**A:** Contractors and clients have fundamentally different needs:
- **Contractors** need to INPUT data (photos, budgets, invoices) - complex, power-user UI
- **Clients** need to VIEW data (progress, spending) - simple, read-only UI
- If we give clients access to contractor dashboard, it's overwhelming and confusing

### Q: Why focus on painting contractors specifically?
**A:** Painting projects have unique characteristics:
- Heavy photo documentation (before/after, progress tracking)
- Material-intensive (paint, primer, equipment tracking)
- Milestone-based payments (per floor completed, per building section)
- Generic PM tools don't fit this workflow

### Q: What's the biggest design challenge?
**A:** Balancing simplicity for non-tech users with power features for daily operations. Contractors need efficiency (they're busy), but also clarity (they're not tech-savvy). Avoid making it "dumbed down" (frustrating for power users) or overly complex (intimidating for beginners).

---

## Next Steps for Designers

After understanding the problem, solution, and users:

1. **Review detailed personas** → [USER_PERSONAS.md](USER_PERSONAS.md)
2. **Understand information architecture** → [INFORMATION_ARCHITECTURE.md](INFORMATION_ARCHITECTURE.md)
3. **Study user flows** → [USER_FLOWS.md](USER_FLOWS.md)
4. **Read design guidelines** → [DESIGN_BRIEF.md](DESIGN_BRIEF.md)
5. **Check deliverables scope** → [SCOPE.md](SCOPE.md)

---

*Last Updated: October 29, 2025*
