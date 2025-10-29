# UI/UX Design Brief - PakeAja

---

**📚 Documentation Journey** | Step 7 of 8

[Project Overview](PROJECT_OVERVIEW.md) → [User Personas](USER_PERSONAS.md) → [Scope](SCOPE.md) → [Design Complexity](DESIGN_COMPLEXITY.md) → [User Flows](USER_FLOWS.md) → [Information Architecture](INFORMATION_ARCHITECTURE.md) → **→ Design Brief** → [PRD](PRD.md)

**[← Previous: Information Architecture](INFORMATION_ARCHITECTURE.md)**

---

**Versi:** 1.0 | **Tanggal:** 28 Oktober 2025
**Untuk:** UI/UX Designer (Freelancer)

---

## 1. Project Overview

### 1.1 Apa yang Kita Bangun?

PakeAja adalah **platform manajemen proyek untuk kontraktor pengecatan** di Indonesia dengan fitur unik: **Portal Client** yang memberikan transparansi penuh kepada project owner.

**Dua sisi platform:**
1. **Dashboard Kontraktor** - tools lengkap untuk manage proyek
2. **Portal Client** - view-only portal untuk project owner track progres

### 1.2 Target Launch

**Q1 2026** (Maret 2026)

### 1.3 Deliverables yang Dibutuhkan

**Phase 1 - Wireframes (2 minggu):**
- [ ] 10 core screens dalam wireframe (low-fidelity)
- [ ] User flow diagrams
- [ ] Mobile responsive layouts

**Phase 2 - High-Fidelity Mockups (2-3 minggu):**
- [ ] Design system (colors, typography, components)
- [ ] 10 core screens dalam high-fidelity mockup
- [ ] Interactive prototype di Figma
- [ ] Mobile & desktop versions

**Phase 3 - Handoff (1 minggu):**
- [ ] Developer handoff documentation
- [ ] Component specifications
- [ ] Asset export (icons, illustrations jika ada)

**Total:** 5-6 minggu design work

---

## 2. Design Principles & Philosophy

### 2.1 Core Principles

**1. Transparency First**
- Semua data harus mudah dilihat dan dipahami
- No hidden information
- Visual indicators for status (colors, icons)

**2. Mobile-First**
- Field workers upload foto dari hp
- Project owners check dari hp (on the go)
- Desktop adalah nice-to-have, tapi mobile adalah must-have

**3. Simplicity Over Features**
- Project owners bukan tech experts
- Minimal clicks untuk accomplish tasks
- Clear hierarchy, no clutter

**4. Trust Through Professionalism**
- Design harus terlihat premium & professional
- Contractors ingin terlihat credible di mata clients
- Clean, modern, business-appropriate

**5. Indonesian Context**
- Bahasa Indonesia sebagai primary language
- Workflow sesuai kebiasaan lokal (BAST, PPN, etc.)
- Design yang familiar untuk Indonesian users

### 2.2 Design Don'ts

❌ Jangan terlalu "playful" - **ini business tool**, bukan social media
❌ Jangan terlalu banyak animasi - prioritas performance
❌ Jangan gunakan istilah/pattern yang unfamiliar di Indonesia
❌ Jangan abaikan dark mode - ini primary theme
❌ Jangan lupa accessibility (contrast, font size, etc.)

**PENTING - Klarifikasi "Jangan Terlalu Playful":**

Yang dimaksud adalah **APPLICATION/PRODUCT (tool) harus professional**, bukan brand personality-nya. Ada perbedaan antara:

**❌ JANGAN - Playful Product UI:**
- Animasi berlebihan di dashboard
- Warna-warna "fun" untuk data visualization
- Ilustrasi kartun di business forms
- Micro-interactions yang terlalu "cute"
- Consumer app vibes

**✅ BOLEH - Approachable Brand Personality:**
- Friendly, warm tone di copy/messaging
- Helpful, encouraging empty states
- Human, understanding error messages
- Welcoming onboarding experience
- Supportive help text

**Kesimpulan:** Design **professional business tool** untuk **approachable brand**.

---

## 3. Design Direction & Brand Guidelines

### 3.1 Brand Positioning

**PENTING: Bedakan antara Product UX dan Brand Personality**

Ada **DUA layer** yang perlu Anda understand:

#### Layer 1: PRODUCT/APPLICATION (Tool Interface)
**Harus:** Professional, efficient, business-focused

**Karakteristik:**
- ✅ Clean dashboard interface (tidak playful)
- ✅ Professional data visualization (charts, tables, metrics)
- ✅ Efficient workflows (minimal clicks)
- ✅ Serious business tool untuk manage Rp 500M+ projects
- ✅ Think: Asana, Linear, Monday.com tapi lebih simple

**Applies to:**
- Dashboard layouts
- Data tables & charts
- Forms & input fields
- Navigation structure
- Interactive components (buttons, dropdowns, etc.)

#### Layer 2: BRAND/COMPANY (PakeAja Personality)
**Harus:** Approachable, friendly, warm - tapi tetap professional

**Karakteristik:**
- ✅ Friendly, helpful tone (bukan corporate kaku)
- ✅ Welcoming untuk SME contractors (not intimidating)
- ✅ Human, understanding (bukan cold/robotic)
- ✅ "Kami siap bantu Anda" vibes
- ✅ Think: Friendly tech startup, bukan enterprise corporation

**Applies to:**
- Copy & messaging
- Onboarding screens & welcome messages
- Empty states ("Belum ada project? Yuk mulai yang pertama!")
- Error messages ("Oops, ada yang salah. Coba lagi ya?")
- Help text & tooltips
- Support/chat interface
- Email notifications

#### Kesimpulan:
**Design professional business tool (Product UX) untuk approachable, friendly brand (Brand Personality).**

**Note tentang Branding:**
- Landing page (www.pakeaja.com) ada tapi masih proof of concept - belum ada branding material
- **Anda bebas create brand identity dari scratch** (colors, typography, visual style)
- Ikuti brand positioning guidelines di atas sebagai panduan

**Design References (Aesthetic Direction):**

Berikut beberapa design references yang kami suka sebagai inspirasi aesthetic direction:

1. **Gantt View Example:**
   - https://dribbble.com/shots/21099259-Projects-Gantt-View
   - Yang kami suka: Clean layout, professional data visualization, good use of color for timeline view
   - Apply to: Project timeline screens, milestone tracking

2. **SaaS Dashboard Overview:**
   - https://dribbble.com/shots/22988502-Overview-SaaS-Web-App-UI-UX-Design
   - Yang kami suka: Modern, clean dashboard layout, good information hierarchy, professional but not too corporate
   - Apply to: Main dashboard, overview screens, data-heavy interfaces

**Catatan:**
- Kami **sangat suka** aesthetic dari references ini - feel free to closely follow the design approach
- Adapt/adjust sesuai functional requirements kami dan konteks Indonesian users
- Yang penting: maintain balance antara professional (seperti examples) dan approachable (brand personality)
- Selama memenuhi functional requirements, Anda bebas mengadopsi layout, color scheme, atau visual style dari references

### 3.2 Color Direction (Suggestions, Not Requirements)

**Status Indicator Colors** (functional requirement):
- 🟢 **Success state:** Completed, On Track, Delivered (use green spectrum)
- 🟡 **Warning state:** In Progress, Minor Delay (use yellow/orange spectrum)
- 🔵 **Info/Planned state:** Planned, Pending (use blue spectrum)
- 🔴 **Error/Danger state:** Delayed, Overdue, Error (use red spectrum)
- ⚪ **Neutral state:** Not Started, Cancelled (use gray spectrum)

**Dark Theme Consideration:**
- Banyak kontraktor akan pakai app di outdoor (laptop di site)
- Dark theme bisa bantu reduce eye strain
- Tapi optional - designer bebas choose light/dark/both

**Anda bebas tentukan:**
- Exact color codes
- Primary brand color
- Accent colors
- Text colors
- Background colors

### 3.3 Typography Direction

**Functional Requirements:**
- **Readability** adalah priority #1 (banyak data, numbers, text)
- Support **Bahasa Indonesia** (pastikan font support Indonesian characters)
- **Mobile readability** - minimum 14px untuk body text di mobile
- **Hierarchy jelas** - headings vs body text easily distinguishable

**Suggestions (bukan requirement):**
- Sans-serif fonts generally work better untuk business apps
- System fonts (-apple-system, Segoe UI) untuk fast loading
- Google Fonts OK jika Anda prefer custom font

**Anda bebas tentukan:**
- Font family
- Font sizes
- Font weights
- Line heights

### 3.4 Visual Style (Your Creative Freedom)

**Required:**
- Consistent design system
- Responsive (mobile, tablet, desktop)
- Accessible (WCAG 2.1 AA minimum)

**Your Choice:**
- Flat design vs subtle shadows/gradients
- Icon style (outline, filled, duotone)
- Border radius (sharp corners vs rounded)
- Spacing system
- Grid system
- Animation style

---

## 4. Screens to Design (Priority Order)

### 4.1 Authentication & Onboarding

**Screen 1: Login Page**
- **Users:** Kontraktor
- **Elements:**
  - Logo PakeAja (top center)
  - "Masuk ke PakeAja" heading
  - "Login dengan Google" button (prominent, primary blue)
  - Divider: "atau"
  - Email input + Password input
  - "Lupa password?" link
  - "Masuk" button
  - "Belum punya akun? Daftar" link
- **Notes:** Simple, clean, trust-building. Dark theme.

**Screen 2: Client Portal - Magic Link Login**
- **Users:** Project owner
- **Flow:**
  - User clicks link dari email
  - Auto-redirect ke portal
  - Loading screen (1-2 detik)
  - Welcome modal (first-time only)
- **Welcome Modal:**
  - "Selamat datang di Portal Proyek Anda!"
  - Bullets: "Lihat progres real-time", "Track material & budget", "Download foto"
  - "Mulai Tour" button atau "Lewati" link
- **Notes:** Make first impression count. Friendly but professional.

### 4.2 Kontraktor Dashboard

**Screen 3: Dashboard Utama (Homepage after login)**
- **Users:** Kontraktor (PM, Owner)
- **Sections:**
  1. **Top Bar:**
     - Logo + company name (kiri)
     - Search bar (tengah)
     - Notifications bell + User avatar (kanan)
  2. **Sidebar (kiri, collapsible):**
     - Dashboard
     - Proyek
     - Material
     - Tim
     - Invoice
     - Settings
     - (Mobile: bottom navigation atau hamburger menu)
  3. **Main Content:**
     - **KPI Cards** (4 cards dalam row):
       * Total Proyek Aktif: 12
       * Proyek On Track: 9 (green)
       * Proyek Delayed: 3 (red)
       * Total Revenue: Rp 2.5M
     - **Chart:** Budget Utilization (bar chart atau line)
     - **Recent Projects List:**
       * Project name, client, progress %, status badge, PM assigned
       * Action buttons: View, Edit
     - **Quick Actions:**
       * "+ Proyek Baru" button (prominent, blue)
       * "Upload Foto Progres" button
- **Notes:** Information-dense tapi tidak overwhelming. Use cards for organization.

**Screen 4: Daftar Proyek (Projects List)**
- **Users:** Kontraktor
- **Features:**
  - **Filters (top):**
    * Status: Semua, Aktif, Selesai, Delayed
    * Search by project name atau client
    * Sort by: Date created, Completion %, Budget
  - **View Toggle:** Grid view atau List view
  - **Project Cards (Grid):**
    * Featured image (thumbnail foto terakhir) atau placeholder
    * Project name (bold)
    * Client name (muted)
    * Progress bar + percentage (60%)
    * Status badge (On Track, Delayed, etc.)
    * Budget: Rp 500M / Rp 800M
    * Days remaining: 15 hari lagi
    * Action dots menu: View, Edit, Archive, Invite Client
  - **List View:**
    * Table format dengan columns: Name, Client, Progress, Budget, Status, PM, Action
  - **Empty State:**
    * Illustration + "Belum ada proyek"
    * "Buat proyek pertama Anda" button
- **Notes:** Scannable. Quick overview tanpa perlu click in.

**Screen 5: Detail Proyek (Project Detail Page)**
- **Users:** Kontraktor
- **Layout:**
  - **Header:**
    * Breadcrumb: Dashboard > Proyek > Grand Indonesia Mall
    * Project name (large, bold)
    * Status badge (On Track)
    * Action buttons: Edit, Invite Client, Archive, More
  - **Tab Navigation:**
    * Overview (active)
    * Material
    * Foto
    * Timeline
    * Budget
    * Invoice
  - **Overview Tab Content:**
    * **Project Info Card:**
      - Client: PT Grand Indonesia
      - Location: Jl. MH Thamrin, Jakarta (with map icon → click to see map)
      - Project Manager: John Doe (avatar)
      - Duration: 1 Mar - 15 May 2025 (10 weeks)
      - Total Budget: Rp 500,000,000
    * **Progress Card:**
      - Overall progress: 65% (big circular progress)
      - Progress by area (list):
        + Lobby: 100% ✓ (green)
        + Lantai 2: 75% (yellow)
        + Lantai 3: 30% (blue)
        + Lantai 4: 0% (gray)
    * **Recent Activity (timeline style):**
      - "3 foto baru di-upload" - 2 jam lalu
      - "Material 'Primer' status: Delivered" - 5 jam lalu
      - "Milestone 'Surface Prep' completed" - Yesterday
    * **Quick Stats (4 mini cards):**
      - Materials: 8 of 10 delivered
      - Photos: 45 uploaded
      - Invoices: 2 of 4 paid
      - Days Left: 15 hari
- **Notes:** This is the "command center" untuk satu proyek. Must be comprehensive.

### 4.3 Material Management

**Screen 6: Material Tracking (Tab dalam Project Detail)**
- **Users:** Kontraktor
- **Layout:**
  - **Top Actions:**
    * "+ Tambah Material" button
    * Filter by status: Semua, Planned, Ordered, Delivered, etc.
    * Search material
  - **Material Cards (Kanban style atau List):**
    * **Option A - Kanban Board:**
      - Columns: Planned | Ordered | In Transit | Delivered | In Use
      - Drag & drop cards between columns
      - Card content:
        + Material name (bold)
        + Brand + quantity
        + Supplier
        + Expected delivery: 5 Mar
        + Status badge
        + Photo thumbnail (jika ada)
    * **Option B - List View:**
      - Table dengan columns: Material, Brand, Qty, Status, Supplier, Expected Date, Action
  - **Material Detail Modal (click card):**
    * Full info: Name, category, brand, product code
    * Quantity: Planned 200L | Ordered 200L | Delivered 200L | Used 150L
    * Unit price & total cost
    * Supplier info
    * Status timeline (visual):
      - Ordered (✓ 1 Mar)
      - In Transit (✓ 3 Mar)
      - Delivered (✓ 5 Mar)
      - In Use (current)
    * Photos (jika ada)
    * Notes
    * Actions: Edit, Update Status, Delete
- **Notes:** Visual tracker adalah key. Project owner akan lihat versi simplified di portal.

### 4.4 Progress Photos

**Screen 7: Foto Progres (Tab dalam Project Detail)**
- **Users:** Kontraktor
- **Layout:**
  - **Top Actions:**
    * "+ Upload Foto" button (prominent)
    * Filters: Semua area, Semua tipe, Date range
    * Sort by: Newest, Oldest, Area
    * View: Grid, List, Timeline
  - **Photo Gallery (Grid default, 3-4 columns):**
    * Thumbnail images (square crop)
    * Hover: Show date, area, uploader
    * Click: Open lightbox
  - **Lightbox View:**
    * Full-size photo (centered)
    * Left/Right arrows untuk navigate
    * Close button (X)
    * **Photo Info (sidebar kanan):**
      - Date & time
      - Location/area (with map pin icon)
      - Photo type: Progress
      - Uploaded by: John Doe (avatar)
      - Caption (if any)
      - Actions: Download, Edit caption, Delete
    * **Before/After Comparison (optional):**
      - Jika ada before photo, show slider comparison
  - **Upload Modal:**
    * Drag & drop area (or click to browse)
    * Multiple file selection
    * Preview thumbnails
    * For each photo:
      - Select area (dropdown)
      - Select photo type (Before, Progress, After, etc.)
      - Caption (optional)
      - Geolocation auto-captured (show map preview)
    * "Upload X Foto" button
- **Notes:** Photos adalah jantung dari Portal Client. Harus mudah upload & view.

### 4.5 Client Portal (Project Owner View)

**Screen 8: Portal Dashboard (Homepage untuk Project Owner)**
- **Users:** Project owner (client)
- **Layout:**
  - **Top Bar:**
    * Logo PakeAja (kiri)
    * Project name dropdown (jika client punya multiple projects)
    * Notifications + User avatar (kanan)
  - **Navigation:**
    * Sidebar (desktop) atau Tab bar (mobile):
      - Overview (icon: home)
      - Material (icon: box)
      - Foto (icon: image)
      - Timeline (icon: calendar)
      - Budget (icon: dollar-sign)
      - Invoice (icon: file-text)
  - **Overview Content:**
    * **Hero Card (big, top):**
      - Project name + featured photo (background)
      - Status badge: On Track (green) atau Delayed (red)
      - Progress: 65% (big circular progress atau progress bar)
      - Timeline: Week 4 of 10 weeks
      - Next milestone: Topcoat Application - starts today
    * **Alert Banner (jika ada issue):**
      - ⚠️ "Material delivery delayed by 3 days. New completion date: May 18"
      - Color: Orange/yellow background
    * **Quick Stats (4 cards):**
      1. Budget: Rp 280M / Rp 500M used (56%)
      2. Materials: 8 of 10 delivered
      3. Photos: 12 new this week
      4. Last Update: 2 hours ago
    * **Recent Updates (timeline):**
      - "3 new photos uploaded - Lantai 2" (2h ago) [Lihat →]
      - "Material 'Topcoat' delivered" (5h ago)
      - "Milestone 'Primer Application' completed - 2 days ahead!" (yesterday)
    * **At-a-Glance Progress by Area:**
      - Visual cards atau progress bars:
        + Lobby: 100% ✓
        + Lantai 2: 75%
        + Lantai 3: 30%
        + Lantai 4: 0%
- **Notes:** **MOST IMPORTANT SCREEN.** Project owner harus instantly understand status. Clean, scannable, trustworthy.

**Screen 9: Portal - Material Tracker (Project Owner View)**
- **Users:** Project owner
- **Layout:**
  - **Material Status Visual Tracker:**
    * **Option A - Timeline Style:**
      - Horizontal timeline dengan stages: Planned → Ordered → In Production → In Transit → Delivered → In Use
      - Material cards positioned at their current stage
    * **Option B - Kanban Style (simplified):**
      - Columns: Pending, Ordered, In Transit, Delivered
      - Material cards in columns
  - **Material Card Content:**
    * Material name (bold)
    * Brand + quantity
    * Status badge (color-coded)
    * Expected delivery: 5 Mar (or "Delivered ✓ 5 Mar")
    * Supplier name
    * Photo thumbnail (jika sudah delivered)
    * Click card → expand details:
      - Full info
      - Status timeline
      - Photos
      - Delay reason (jika delayed)
  - **Delay Alert:**
    * Jika ada material delayed, banner di top:
      - "⚠️ 1 material delayed: Topcoat - Production delay at supplier. New ETA: 20 Mar"
- **Notes:** Transparency adalah goal. Show exactly "where is my material".

**Screen 10: Portal - Photo Gallery (Project Owner View)**
- **Users:** Project owner
- **Layout:**
  - **Filters (top):**
    * Semua area / Pilih area (dropdown)
    * Semua tipe / Before, Progress, After (tabs atau dropdown)
    * Date range picker
  - **Gallery (Grid, 3-4 columns on desktop, 2 on mobile):**
    * Thumbnail images
    * Hover: Show date & area (desktop only)
    * Click: Open lightbox
  - **Lightbox:**
    * Full-size photo (centered, max width 90vw)
    * Navigation arrows
    * Photo info (overlay or sidebar):
      - Date & time
      - Location/area
      - Photo type
      - Caption
    * **Before/After Slider:**
      - Jika ada before & after, show comparison slider
    * Actions: Download foto, Download all (ZIP)
  - **Empty State:**
    * "Belum ada foto di-upload"
    * "Check kembali nanti untuk update progres terbaru"
- **Notes:** Photos adalah "proof of work". Must be beautiful, easy to browse, fast loading.

---

## 5. Component Library Needed

### 5.1 Core Components

Tolong design reusable components ini:

**Buttons:**
- Primary button (blue, bold action)
- Secondary button (outline, less emphasis)
- Tertiary button (text only, minimal)
- Danger button (red, destructive action)
- Icon button (square, circular)
- States: Default, Hover, Active, Disabled

**Form Inputs:**
- Text input (dengan label, placeholder, error state, success state)
- Textarea
- Select dropdown (single-select, multi-select)
- Date picker
- File upload (drag & drop area)
- Checkbox
- Radio button
- Toggle switch

**Cards:**
- Basic card (dengan header, content, footer)
- Stat card (untuk KPI metrics)
- Project card (untuk project list)
- Material card (untuk material tracker)

**Navigation:**
- Sidebar (collapsible, with icons)
- Top navigation bar
- Breadcrumb
- Tab navigation
- Bottom navigation (mobile)

**Data Display:**
- Table (sortable, filterable)
- List (simple, with avatars)
- Progress bar (horizontal, circular)
- Badge (status indicator)
- Tag
- Avatar (user, company logo)
- Timeline

**Feedback:**
- Modal / Dialog
- Drawer (side panel)
- Toast notification (success, error, warning, info)
- Alert banner
- Loading spinner
- Empty state (illustration + message)
- Error state

**Media:**
- Image (dengan lazy loading indicator)
- Thumbnail
- Lightbox / Image viewer
- Gallery grid

**Charts (optional - atau gunakan library):**
- Line chart (progress over time)
- Bar chart (budget breakdown)
- Donut chart (progress %, budget %)

---

## 6. Responsive Design Guidelines

### 6.1 Breakpoints

```
Mobile: 320px - 767px
Tablet: 768px - 1023px
Desktop: 1024px - 1439px
Large Desktop: 1440px+
```

### 6.2 Priority per Screen Size

**Mobile (primary focus untuk project owner & field workers):**
- Portal dashboard - MUST be perfect
- Photo gallery - MUST be perfect
- Photo upload - MUST work seamlessly
- Material tracker - simplified view OK
- Budget summary - high-level OK

**Desktop (primary focus untuk kontraktor PM/owners):**
- Dashboard utama - full featured
- Project detail - all tabs accessible
- Material management - full CRUD
- Invoice generation - complex forms
- Multi-column layouts

**Tablet:**
- Best of both worlds
- 2-column layouts preferred
- Collapsible sidebar

### 6.3 Mobile-Specific Considerations

**Navigation:**
- Bottom tab bar (5 main sections) atau Hamburger menu
- Minimize depth (max 2 levels)

**Touch Targets:**
- Minimum 44x44px (Apple guideline)
- Prefer 48x48px (Android guideline)
- Adequate spacing between tappable elements

**Forms:**
- Stack form fields vertically
- Large input fields (min 48px height)
- Show one input at a time for complex forms (wizard style)

**Images:**
- Lazy loading for performance
- Compress automatically
- Show placeholder while loading

---

## 7. Interaction & Animation Guidelines

### 7.1 Micro-interactions

**Hover States:**
- Buttons: Darken 10%, scale slightly (1.02x)
- Cards: Lift with shadow (shadow-sm → shadow-md)
- Links: Underline or color change

**Click/Tap Feedback:**
- Buttons: Scale down slightly (0.98x) on press
- Cards: No scale (too jarring), but show active state

**Loading States:**
- Skeleton screens untuk content loading (bukan spinner di tengah layar)
- Progress bar untuk file uploads
- Spinner untuk button actions

**Transitions:**
- Duration: 150-300ms (fast, not sluggish)
- Easing: ease-out (natural deceleration)
- Fade in: opacity 0 → 1
- Slide in: translateY(10px) → 0

### 7.2 Animations to AVOID

❌ Overly playful animations (bouncing, spinning excessively)
❌ Automatic carousels (user-controlled only)
❌ Background videos (performance killer)
❌ Parallax scrolling (nice-to-have, not priority)

### 7.3 Accessibility Animations

- Respect `prefers-reduced-motion` (disable animations jika user prefers)
- Focus states clearly visible (outline atau background color change)
- Keyboard navigation support

---

## 8. Design System Deliverables

### 8.1 Figma File Structure

Tolong organize Figma project seperti ini:

```
📁 PakeAja - Design System
  📄 Cover (intro, team, timeline)
  📄 Design Tokens (colors, typography, spacing, shadows)
  📄 Components (button, input, card, etc.) ← Master components
  📄 Icons (all icons used)

📁 PakeAja - Wireframes
  📄 Sitemap & User Flows
  📄 Wireframes - Authentication
  📄 Wireframes - Kontraktor Dashboard
  📄 Wireframes - Portal Client
  📄 Mobile Wireframes

📁 PakeAja - High-Fidelity Mockups
  📄 Mockups - Kontraktor (Desktop)
  📄 Mockups - Kontraktor (Mobile)
  📄 Mockups - Portal Client (Desktop)
  📄 Mockups - Portal Client (Mobile)

📁 PakeAja - Prototype
  📄 Interactive Prototype (linked screens)
```

### 8.2 Design Handoff Checklist

Untuk developer handoff, tolong sediakan:

- [ ] **Design tokens:**
  - Color variables (HEX, RGB)
  - Font sizes, weights, line heights
  - Spacing scale
  - Border radius values
  - Shadow values
- [ ] **Component specs:**
  - Dimensions (width, height, padding, margin)
  - Responsive behavior (how it changes across breakpoints)
  - States (default, hover, active, disabled, error)
  - Typography (font, size, weight, color)
- [ ] **Assets:**
  - Logo (SVG, PNG @1x @2x @3x)
  - Icons (SVG preferred, atau PNG @1x @2x)
  - Illustrations (jika ada)
  - Background images (optimized)
- [ ] **Prototype:**
  - Interactive Figma prototype dengan:
    * Main user flows clickable
    * Hover states visible
    * Transitions demonstrated
- [ ] **Documentation:**
  - Notes untuk tricky interactions
  - Animation specs (duration, easing)
  - Conditional logic ("Show this only if...")

---

## 9. Reference & Inspiration

### 9.1 Competitor UX Analysis

**Procore (US):**
- ✅ Professional, trust-building
- ❌ Too complex, overwhelming untuk SME Indonesia

**Buildertrend (US):**
- ✅ Good photo gallery, timeline visualization
- ❌ Too feature-heavy, expensive

**Fieldwire (US):**
- ✅ Clean mobile UX, simple task management
- ❌ Generic construction, not painting-specific

**Takeaway:** Ambil profesionalisme mereka, tapi simplify untuk Indonesian SME market.

### 9.2 Design Inspiration (non-competitor)

**For Dashboards:**
- Linear (https://linear.app) - Clean, fast, minimal
- Notion (https://notion.so) - Flexible layouts, good information hierarchy
- Stripe Dashboard (https://stripe.com) - Clear data visualization

**For Client Portal:**
- Loom (video sharing) - Simple viewer experience
- Dropbox (file sharing) - Clean file browser, easy download
- FreshBooks (invoicing) - Clear invoice presentation

**For Photo Gallery:**
- Unsplash (https://unsplash.com) - Beautiful grid, lightbox
- Instagram (web) - Grid layout, swipe gestures (mobile)

**For Construction Context:**
- Buildertrend (https://buildertrend.com) - Lihat timeline & photo gallery mereka

---

## 10. Questions & Clarifications

Jika ada yang tidak clear, silakan tanya:

**Product Questions:**
- Reach out ke Product Owner
- Reference: `PRD-Product-Requirements-Document.md`

**User Stories:**
- Reference: `User-Stories-Acceptance-Criteria.md` (akan dibuat)

**User Research:**
- Reference: `User-Personas.md` (akan dibuat)

**Technical Constraints:**
- Reference: `Infrastructure-Comparison.md` (akan dibuat)

---

## 11. Timeline & Milestones

**Week 1-2: Wireframes**
- Buat wireframes untuk 10 core screens
- Review session di akhir Week 2
- Iterate berdasarkan feedback

**Week 3-4: Design System & High-Fidelity**
- Establish design system (colors, typography, components)
- Design high-fidelity mockups untuk core screens
- Review session di akhir Week 4

**Week 5: Prototype & Polish**
- Create interactive prototype di Figma
- Polish details (animations, micro-interactions)
- Final review

**Week 6: Handoff**
- Prepare developer handoff documentation
- Export assets
- Knowledge transfer session dengan developers

---

## 12. Success Criteria

Design akan dianggap sukses jika:

✅ **Usability:**
- User bisa accomplish key tasks tanpa kebingungan
- Information hierarchy jelas (what's important stands out)
- Mobile experience smooth (no pinch-to-zoom needed)

✅ **Aesthetics:**
- Professional, trust-building, modern
- Consistent dengan brand PakeAja
- Dark theme implemented well (not jarring)

✅ **Technical Feasibility:**
- Design bisa di-implement dengan Next.js + Tailwind
- No overly complex animations yang slow down app
- Responsive across all breakpoints

✅ **Stakeholder Approval:**
- Product Owner approves final design
- Developers confirm design is implementable

---

## 13. Contact & Communication

**Product Owner:**
**Contact:**
- Review sessions: Weekly (every Monday, tentative)
- Feedback: Via Figma comments

**Questions:**
Jangan ragu untuk tanya! Better to clarify early daripada re-design later.

---

**Let's build something amazing! 🚀**

Terima kasih sudah join tim PakeAja. Kami excited untuk lihat kreativitas Anda membawa vision ini jadi reality.

---

## ➡️ Continue Reading

**[Next: PRD (Product Requirements) →](PRD.md)**
