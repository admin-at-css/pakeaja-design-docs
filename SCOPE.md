# PakeAja - Design Scope & Deliverables

## MVP Scope Overview

This document outlines the complete design deliverables for PakeAja MVP (Minimum Viable Product).

---

## Total Screens: 23

### Contractor Dashboard: 15 Screens

**Core Screens:**
1. Login / Sign Up
2. Dashboard Home (overview metrics, recent activity)
3. Project List (all projects dengan filtering & search)
4. Create New Project (form untuk setup project baru)
5. Project Detail (overview, progress, team)

**Project Management Screens:**
6. Progress Timeline (milestone tracking, Gantt-style view)
7. Photo Upload & Gallery (before/after progress photos)
8. Material Management (inventory, usage tracking)
9. Budget Tracking (actual vs planned spending)
10. Invoice Management (create, send, track invoices)

**Reporting & Communication:**
11. Client Reports (generate & share progress reports)
12. Team Management (assign roles, permissions)
13. Activity Log (audit trail untuk semua project activities)
14. Settings & Profile (account settings, company info)
15. Notifications Center (alerts, reminders, updates)

---

### Client Portal: 8 Screens

**Core Screens:**
1. Client Login (separate authentication flow)
2. Dashboard Home (project overview, key metrics)
3. Progress Tracking (real-time project status)
4. Photo Gallery (view before/after photos by date/milestone)

**Financial & Communication:**
5. Budget Overview (spending breakdown, budget vs actual)
6. Milestone Tracker (upcoming milestones, completion status)
7. Invoice View (received invoices, payment status)
8. Profile & Settings (client account management)

---

## Design Deliverables

### Deliverable 1: Low-Fidelity Wireframes

**Scope:**
- All 23 screens in wireframe format (black & white, basic layouts)
- Mobile-responsive design (desktop primary, mobile-optimized views)
- Clear information hierarchy and layout structure
- Navigation flow between screens
- Basic component placement (buttons, forms, tables, cards)

**Format:** Figma frames, organized by user type (Contractor vs Client)

---

### Deliverable 2: High-Fidelity Mockups

**Scope:**
- All 23 screens with full visual design
- Consistent color palette, typography, spacing
- Indonesian UI/UX conventions applied
- Responsive design for desktop and mobile viewports
- Real content examples (not lorem ipsum)
- Hover states, active states, disabled states for interactive elements

**Design Requirements:**
- Professional B2B SaaS aesthetic (clean, efficient, not playful)
- Approachable brand personality in copy/messaging
- Accessibility considerations (color contrast, readable fonts)
- Data visualization design (charts, graphs, progress indicators)

**Format:** Figma frames with production-ready designs

---

### Deliverable 3: Complete Design System

**Scope:**
- **Component Library** (reusable UI components):
  - Buttons (primary, secondary, tertiary, icon buttons)
  - Form inputs (text fields, dropdowns, checkboxes, radio buttons, date pickers)
  - Cards & containers
  - Navigation elements (sidebar, top nav, breadcrumbs)
  - Tables & data grids
  - Modals & dialogs
  - Alerts & notifications
  - Progress indicators (spinners, progress bars, status badges)
  - Icons set (navigation, actions, status indicators)
  - Empty states & error messages

- **Design Tokens:**
  - Color palette (primary, secondary, neutrals, semantic colors)
  - Typography scale (font families, sizes, weights, line heights)
  - Spacing system (margins, paddings, gaps)
  - Border radius, shadows, elevation levels
  - Breakpoints for responsive design

- **Style Guide Documentation:**
  - Usage guidelines for each component
  - Do's and don'ts examples
  - Accessibility notes
  - Responsive behavior patterns

**Format:** Figma with organized component library using variants, auto-layout, and proper naming conventions

---

### Deliverable 4: Interactive Prototypes

**Scope:**
- Clickable prototypes for key user flows (minimum 8 flows):
  1. Contractor: Login → Create Project → Upload Photos
  2. Contractor: Dashboard → Project Detail → Generate Report
  3. Contractor: Invoice Creation & Sending to Client
  4. Contractor: Material Management & Budget Tracking
  5. Client: Login → View Progress → Browse Photo Gallery
  6. Client: Dashboard → Budget Overview → View Invoices
  7. Navigation between all main screens (global nav testing)
  8. Mobile responsive prototype (key flows on mobile viewport)

- **Interaction Details:**
  - Smooth transitions between screens
  - Button click interactions
  - Form input behavior (focus states, validation feedback)
  - Dropdown menus & modal overlays
  - Hover effects and micro-interactions

**Format:** Figma prototype with presentation mode ready for user testing

---

## Total Estimated Timeline

**Full Project (All 23 Screens):** 6-8 weeks

---

## Split Project Option

If working in phases, we offer two projects:

### Project 1: Contractor Dashboard (15 screens)
- All 4 deliverables for 15 contractor-facing screens

### Project 2: Client Portal (8 screens)
- All 4 deliverables for 8 client-facing screens
- Uses design system from Project 1 (faster execution)

---

## What's NOT Included in This Scope

This is a **design project**, NOT a development project. The following are **excluded**:

- ❌ Frontend/backend development (coding)
- ❌ Database setup or API integration
- ❌ User testing or usability research
- ❌ Content writing or copywriting (you'll use placeholder copy provided)
- ❌ Logo design or full brand identity (logo will be provided if available)
- ❌ Marketing materials (landing page redesign, pitch decks, social media)
- ❌ Post-launch design support (this is negotiated separately)

**Note:** Marketing materials, icons, illustrations, and ongoing design support are potential **Phase 2 opportunities** for long-term collaboration.

---

## Design Complexity Considerations

This project is **NOT a simple landing page or marketing website**. Key complexity factors:

1. **Two-sided platform:** Different interfaces for contractors vs clients (different needs, permissions, data views)
2. **Data-heavy dashboards:** Complex data visualization, tables, charts, financial tracking
3. **Complete design system from scratch:** No existing brand guidelines or component library
4. **Mobile-responsive across 23 screens:** Desktop primary + mobile-optimized layouts
5. **B2B SaaS UX patterns:** Workflow optimization for non-tech-savvy users managing Rp 500M+ projects

For detailed complexity analysis, see [DESIGN_COMPLEXITY.md](DESIGN_COMPLEXITY.md).

---

## Deliverables Checklist

Use this checklist to ensure all deliverables are complete:

### Wireframes ✅
- [ ] All 23 screens designed in low-fidelity
- [ ] Desktop and mobile layouts shown
- [ ] Navigation flow is clear
- [ ] Information hierarchy established
- [ ] Organized in Figma with clear naming

### High-Fidelity Mockups ✅
- [ ] All 23 screens with full visual design
- [ ] Consistent color palette applied
- [ ] Typography system implemented
- [ ] Responsive designs for desktop + mobile
- [ ] Hover/active/disabled states included
- [ ] Real content examples (not lorem ipsum)

### Design System ✅
- [ ] Component library created with variants
- [ ] Design tokens documented
- [ ] Style guide with usage examples
- [ ] Organized using auto-layout and proper naming
- [ ] Ready for developer handoff

### Interactive Prototypes ✅
- [ ] Minimum 8 key user flows prototyped
- [ ] Smooth transitions and interactions
- [ ] Mobile prototype included
- [ ] Presentation mode tested and working
- [ ] Ready for stakeholder review

---

**Last Updated:** October 29, 2025
