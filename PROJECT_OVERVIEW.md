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

## Target Market

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
- Budi (Project Manager, 42 years) - Heavy platform user
- Siti (Site Supervisor, 38 years) - Mobile user, photo uploads
- Andi (Finance Staff, 35 years) - Invoicing, budget tracking
- Pak Hasan (Project Owner, 50 years) - Client portal user
- Ibu Linda (Finance Approver, 45 years) - Invoice approval
- David (Property Manager, 40 years) - Multi-project oversight

---

## Market Opportunity

### Indonesian Construction Industry Context

**Market Size:**
- Construction industry: Rp 2,000+ trillion annual market (2024)
- Painting contractors: Estimated 10,000+ registered businesses in Indonesia
- Target segment (SME contractors): ~3,000-5,000 companies

**Current Software Landscape:**
- ❌ **No specialized tools** for painting contractors (use generic PM software or Excel)
- ❌ **Global SaaS too expensive** (Asana, Monday.com = $100-300/month, not ROI for Indonesian SMEs)
- ❌ **Complex enterprise software** (SAP, Oracle = overkill for contractors)
- ✅ **PakeAja opportunity:** Affordable, purpose-built, Indonesian-market-fit

**Competitive Advantage:**
- **Indonesian-first design:** Bahasa Indonesia, local UX conventions, WA-like simplicity
- **Construction-specific:** Features tailored for painting contractors (not generic PM)
- **Affordable pricing:** Target Rp 300k-500k/month (vs Rp 1-3 juta for global tools)
- **Client portal included:** Transparency = competitive advantage for contractors

---

## Business Model

### SaaS Subscription (Per Company)

**Pricing Tiers (Planned):**

**Starter Plan:** Rp 300,000/month
- 1-3 active projects
- 1 project manager account
- 3 client portal accounts
- Basic reporting

**Professional Plan:** Rp 500,000/month
- Up to 10 active projects
- 3 PM/supervisor accounts
- Unlimited client accounts
- Advanced reporting, material tracking

**Enterprise Plan:** Rp 800,000/month
- Unlimited projects
- Unlimited team accounts
- Custom branding, API access
- Dedicated support

**Revenue Potential:**
- 100 customers @ Rp 400k avg/month = Rp 40 juta/month (Rp 480 juta/year)
- 500 customers @ Rp 400k avg/month = Rp 200 juta/month (Rp 2.4 miliar/year)
- 1,000 customers = Rp 400 juta/month (Rp 4.8 miliar/year)

**Note:** Above projections are illustrative. Actual pricing and tiers subject to market testing.

---

## Go-to-Market Strategy

### Phase 1: MVP Launch (Current Focus)

**Goals:**
- Launch with 23 core screens (contractor dashboard + client portal)
- Acquire first 10-20 beta customers (Jakarta, Surabaya, Bandung)
- Validate product-market fit
- Gather feedback for iteration

**Distribution:**
- Direct sales (founder-led outreach to contractor networks)
- Industry associations (Indonesian Contractors Association / GAPENSI)
- Word-of-mouth (contractors share success stories with peers)
- Content marketing (blog posts, case studies on construction management)

### Phase 2: Feature Expansion (6-12 months post-MVP)

**Planned Features:**
- CRM module (lead tracking, quotation management)
- Inventory management (paint stock, equipment tracking)
- Supplier portal (vendor management, purchase orders)
- Mobile app (iOS + Android for field workers)
- Integrations (accounting software, e-invoicing)

See [FUTURE_PHASES.md](FUTURE_PHASES.md) for detailed roadmap.

### Phase 3: Scale & Enterprise (12-24 months)

**Goals:**
- Expand to 500+ customers
- Add enterprise features (multi-branch, advanced analytics)
- Explore adjacent markets (other construction trades: electrical, plumbing, HVAC)

---

## Why This Project Matters

### For Contractors:
- ✅ **Win bigger contracts:** Professional tools = professional image
- ✅ **Save time:** Stop answering "Gimana progress-nya?" every day
- ✅ **Reduce disputes:** Everything documented, audit trail available
- ✅ **Improve cash flow:** Faster invoicing, payment tracking
- ✅ **Scale business:** Manage more projects with same team size

### For Clients (Project Owners):
- ✅ **Peace of mind:** Real-time progress visibility, no need to call PM
- ✅ **Budget control:** See spending breakdown, catch overruns early
- ✅ **Quality assurance:** Before/after photos prove work completion
- ✅ **Accountability:** Timeline tracking, milestone-based payments
- ✅ **Transparency:** All communication logged, no he-said-she-said

### For the Design Partner:
- ✅ **Portfolio piece:** Real B2B SaaS product (not just mockup)
- ✅ **Impact:** Your designs used by hundreds of Indonesian businesses
- ✅ **Long-term income:** Ongoing design work as product scales
- ✅ **Creative freedom:** Build design system from scratch
- ✅ **Market knowledge:** Deep dive into Indonesian construction industry

---

## Product Vision (3-Year Horizon)

**Year 1: Launch & Validate**
- 100+ customers, Rp 40-50 juta MRR
- Core platform stable, high customer satisfaction (NPS 40+)
- Strong case studies (3-5 contractors share success stories)

**Year 2: Expand & Integrate**
- 500+ customers, Rp 200 juta MRR
- Phase 2 features live (CRM, inventory, mobile app)
- Integrations with popular accounting software (Accurate, Jurnal)

**Year 3: Dominate & Diversify**
- 1,500+ customers, Rp 600 juta MRR
- Market leader for painting contractors in Indonesia
- Expand to adjacent trades (electrical contractors, HVAC, plumbing)
- Explore international markets (Malaysia, Philippines, Thailand)

---

## Team & Resources

### Current Team:
- **Kevin Zakaria:** Founder, Product Manager (you're working with Kevin)
- **Development Team:** To be hired post-design completion
- **UI/UX Designer:** **This is where you come in!**

### Your Role as Design Partner:
- **Phase 1 (Now):** Complete design for MVP (23 screens, design system, prototypes)
- **Phase 2 (Future):** Ongoing design support as product scales
- **Long-term:** Potential monthly retainer, become dedicated PakeAja designer

---

## Why We Need a Great Designer

**PakeAja's success depends on UX.**

Contractors won't adopt complex software (they'll stick with WhatsApp). Clients won't use portals that are confusing (they'll keep calling PMs).

**Your design must:**
- ✅ Make contractors **more productive** (save time, not add work)
- ✅ Make clients **feel informed** (reduce anxiety, build trust)
- ✅ Be **approachable** for non-tech users (Indonesian SME contractors)
- ✅ Look **professional** (contractors show to clients to win contracts)
- ✅ Scale **efficiently** (design system supports rapid feature development)

**The right design = product success.**
**The wrong design = users abandon platform.**

This is why we're investing time and budget to find the **right design partner**.

---

## What Happens After Design is Complete?

### Development Timeline (Estimated):
- **Month 1-3:** Frontend development (React/Next.js)
- **Month 4-5:** Backend development (Supabase, API integrations)
- **Month 6:** Testing, bug fixes, deployment
- **Month 7:** Beta launch (10-20 customers)
- **Month 8+:** Iteration based on feedback

**Designer Involvement:**
- Design QA (ensure dev matches designs)
- Iteration support (refine based on user feedback)
- New feature design (Phase 2 modules)

---

## Questions You Might Have

### Q: Is there existing branding or design?
**A:** Minimal. Landing page exists (proof of concept, no branding). **You have full creative freedom.**

### Q: Who are the key stakeholders?
**A:** Kevin (founder) is primary stakeholder. Feedback will come from beta customers during development.

### Q: What's the tech stack for development?
**A:** React/Next.js frontend, Supabase backend. **You don't need to know this** - just design in Figma.

### Q: Will designs be user-tested?
**A:** Yes, during development phase. Initial designs will be reviewed by 2-3 contractor contacts for early feedback.

### Q: What if PakeAja pivots or changes direction?
**A:** Unlikely (problem is validated, market research done). But if scope changes, we'll discuss compensation adjustments.

---

## Ready to Be Part of PakeAja's Journey?

This is more than a design project - it's an **opportunity to shape a product** that will impact thousands of Indonesian businesses.

**Next Steps:**
1. Review all documentation ([README.md](README.md) has full reading list)
2. Calculate your budget & timeline ([HOW_TO_PROPOSE.md](HOW_TO_PROPOSE.md))
3. Submit application via Google Form (link in job posting)
4. Wait for interview invite (top 3-5 candidates)

**We're excited to see your portfolio and proposal!**

---

**Last Updated:** October 29, 2025
