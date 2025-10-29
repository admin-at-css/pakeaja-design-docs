# PRD - Product Requirements Document

---

**📚 Documentation Journey** | Step 8 of 8

[Project Overview](PROJECT_OVERVIEW.md) → [User Personas](USER_PERSONAS.md) → [Scope](SCOPE.md) → [Design Complexity](DESIGN_COMPLEXITY.md) → [User Flows](USER_FLOWS.md) → [Information Architecture](INFORMATION_ARCHITECTURE.md) → [Design Brief](DESIGN_BRIEF.md) → **PRD**

**[← Previous: Design Brief](DESIGN_BRIEF.md)**

---

**Versi:** 1.0 | **Tanggal:** 28 Oktober 2025
**Status:** Draft untuk Review

---

## 1. Executive Summary

### 1.1 Deskripsi Produk

PakeAja adalah platform manajemen proyek berbasis web yang dirancang khusus untuk kontraktor pengecatan di Indonesia. Platform ini menggunakan model **two-sided B2B** yang melayani dua pengguna utama:

1. **Kontraktor pengecatan** (pelanggan berbayar) - mendapat akses penuh ke sistem manajemen proyek
2. **Project owner/client** (gratis) - mendapat akses ke portal transparan untuk memantau proyek mereka

### 1.2 Masalah yang Dipecahkan

**Untuk Kontraktor:**
- Kesulitan mengelola banyak proyek secara profesional (masih pakai Excel, WhatsApp, kertas)
- Kehilangan kredibilitas karena dokumentasi manual yang berantakan
- Pembayaran lambat karena client tidak percaya progres pekerjaan
- Kalah tender dengan kompetitor yang terlihat lebih profesional

**Untuk Project Owner:**
- Tidak ada visibilitas ke pekerjaan kontraktor (seperti kotak hitam)
- Harus telepon/WhatsApp setiap hari untuk cek progres
- Keterlambatan material baru diketahui terlambat
- Tidak bisa show progres ke atasan/board of directors
- Tidak ada dokumentasi warranty dan maintenance

### 1.3 Solusi

Platform yang memberikan **transparansi penuh** kepada project owner melalui Portal Client, sehingga:
- Kontraktor terlihat lebih profesional → menang lebih banyak tender
- Project owner bisa track proyek 24/7 → mengurangi telepon 80%
- Trust meningkat → pembayaran lebih cepat
- Network effect → project owner demand kontraktor pakai PakeAja

### 1.4 Target Launch

**Q1 2026** (Januari - Maret 2026)

---

## 2. Target Pengguna

### 2.1 Pengguna Primer (Kontraktor - Berbayar)

**Segmen Pasar:**
- Perusahaan pengecatan kecil hingga menengah (5-50 karyawan)
- Lokasi: Kota-kota besar Indonesia (Jakarta, Surabaya, Bandung, Medan, dll)
- Nilai proyek: Rp 100 juta - Rp 5 miliar per proyek
- Jumlah proyek: 3-20 proyek aktif sekaligus

**Persona:**

1. **Pemilik Perusahaan Pengecatan**
   - Usia: 35-55 tahun
   - Kebutuhan: Melihat semua proyek, profitabilitas, win rate
   - Tech savviness: Sedang (pakai WhatsApp, email, Excel)

2. **Project Manager**
   - Usia: 28-45 tahun
   - Kebutuhan: Manage proyek sehari-hari, track budget, material, timeline
   - Tech savviness: Sedang-tinggi

3. **Supervisor Lapangan**
   - Usia: 25-40 tahun
   - Kebutuhan: Upload foto progres, update status dari site
   - Tech savviness: Sedang (mobile-first)

### 2.2 Pengguna Sekunder (Project Owner - Gratis)

**Segmen Pasar:**
- Shopping mall, hotel, gedung perkantoran, developer properti
- Decision maker: General Manager, Operations Manager, Facility Manager
- Budget proyek: Rp 100 juta - Rp 5 miliar+

**Persona:**

1. **General Manager Shopping Mall**
   - Usia: 35-50 tahun
   - Pain point: "CEO saya tanya progres, saya harus telepon kontraktor dulu"
   - Kebutuhan: Summary mingguan yang bisa di-forward ke atasan
   - Tech savviness: Sedang

2. **Operations Manager Hotel**
   - Usia: 30-45 tahun
   - Pain point: "Pengecatan dilakukan saat ada tamu, saya perlu tahu kapan/dimana"
   - Kebutuhan: Real-time schedule updates
   - Tech savviness: Tinggi

3. **Facility Manager Corporate Office**
   - Usia: 30-50 tahun
   - Pain point: "Harus justify biaya ke finance department"
   - Kebutuhan: Detailed budget breakdown, invoice tracking
   - Tech savviness: Sedang-tinggi

---

## 3. Tujuan Produk & Success Metrics

### 3.1 Tujuan Bisnis

1. **Acquisition:** Onboard 50 perusahaan kontraktor pengecatan dalam 6 bulan pertama
2. **Activation:** 80% kontraktor yang sign up membuat minimal 1 proyek dalam 7 hari
3. **Retention:** 70% kontraktor tetap aktif setelah 3 bulan (monthly active usage)
4. **Revenue:** 30% kontraktor convert dari FREE ke STARTER/BUSINESS plan dalam 2 bulan
5. **Network Effect:** Setiap kontraktor invite rata-rata 3 project owner ke portal

### 3.2 Success Metrics - Untuk Kontraktor

**Primary Metrics:**
- Time saved: Hemat 5+ jam/minggu untuk admin proyek
- Faster payments: Siklus pembayaran dari project owner tepat waktu
- Win rate: Naik 15-20% dalam tender/proposal
- Client satisfaction: NPS score >50

**Secondary Metrics:**
- Jumlah proyek aktif per user
- Frekuensi login (daily active users)
- Jumlah foto progress di-upload per minggu
- Jumlah invoice generated

### 3.3 Success Metrics - Untuk Project Owner

**Primary Metrics:**
- Reduction in calls/emails: 80% berkurang
- Time saved: 30 menit telepon → 2 menit di portal
- Satisfaction: NPS score >60
- Repeat business: 90% hire kontraktor yang sama lagi

**Secondary Metrics:**
- Portal login frequency (berapa kali check per minggu)
- Time spent in portal per session
- Mobile vs desktop usage
- Feature adoption rate (berapa % pakai semua fitur)

---

## 4. Scope MVP (Minimum Viable Product)

### 4.1 Modul dalam MVP

MVP fokus pada **2 modul utama**:

1. **Module 1: Manajemen Proyek** (untuk kontraktor)
2. **Module 4: Portal Client** (untuk project owner)

**Modul yang TIDAK termasuk MVP:**
- Module 2: Kalkulator Material (Phase 2)
- Module 3: Laporan Tim Sales (sudah development terpisah di Android)
- Module 5: Asisten AI (Phase 3)

### 4.2 Fitur MVP - Manajemen Proyek (Kontraktor)

#### 4.2.1 Autentikasi & Onboarding
- [x] Login dengan Google OAuth
- [x] Register company (nama, alamat, logo)
- [x] Setup user roles (Owner, PM, Supervisor)
- [x] Onboarding wizard (3-step setup)

#### 4.2.2 Project Management Core
- [x] **Buat proyek baru**
  - Info dasar: nama proyek, client, lokasi, budget total
  - Timeline: tanggal mulai, estimasi selesai
  - Assign project manager
- [x] **Dashboard proyek**
  - List semua proyek (aktif, completed, delayed)
  - Filter by status, date, PM
  - Quick stats per proyek (progress %, budget used, days remaining)
- [x] **Detail proyek**
  - Tab: Overview, Material, Foto, Timeline, Budget, Invoice

#### 4.2.3 Material Tracking
- [x] **Tambah material**
  - Nama, kategori, brand, jumlah, harga
  - Supplier info
  - Expected delivery date
- [x] **Update status material**
  - Planned → Ordered → In Transit → Delivered → In Use → Fully Used
  - Upload foto bukti material delivered
  - Alasan delay (jika ada)
- [x] **Material dashboard**
  - Visual tracker (kanban style atau timeline)
  - Alert untuk material delayed

#### 4.2.4 Progress Tracking & Photos
- [x] **Upload foto progres**
  - Dari desktop atau mobile
  - Auto-capture: geolocation, timestamp
  - Pilih area/lokasi (dropdown)
  - Pilih tipe foto: Before, Progress, After
  - Caption optional
- [x] **Gallery foto**
  - Organize by date, area, photo type
  - Before/after comparison slider
  - Download foto
- [x] **Progress by area**
  - Breakdown proyek ke area/zona (Lobby, Lantai 2, dll)
  - Percentage completion per area
  - Status per area (Not Started, In Progress, Completed)

#### 4.2.5 Timeline & Milestones
- [x] **Milestones**
  - Tambah milestone (nama, tanggal target)
  - Mark as complete (tanggal aktual)
  - Status: Pending, In Progress, Completed, Delayed
- [x] **Timeline view**
  - Simple timeline (bukan Gantt chart di MVP)
  - Show: milestones, current phase, days remaining
  - Alert jika delayed

#### 4.2.6 Budget Tracking
- [x] **Budget overview**
  - Total budget vs actual spending
  - Breakdown: Material, Labor, Equipment, Other
  - Visual progress bar
  - Alert jika trending over budget (>80%)
- [x] **Expense recording** (simplified)
  - Log pembelian material dengan receipt
  - Log biaya lainnya
  - Kategori expense

#### 4.2.7 Invoicing
- [x] **Generate invoice**
  - Invoice untuk milestone/progress billing
  - Auto-calculate PPN 11%
  - Payment terms & bank details
  - Generate PDF
- [x] **Invoice tracking**
  - Status: Draft, Sent, Viewed, Paid, Overdue
  - Payment reminder
- [x] **Project owner bisa lihat & download invoice di portal**

#### 4.2.8 Client Portal Access Management
- [x] **Invite project owner ke portal**
  - Masukkan email client
  - Set permission level (Viewer, Commenter, Approver)
  - Send magic link via email
- [x] **Manage access**
  - Lihat siapa saja yang punya akses
  - Revoke access (jika perlu)

### 4.3 Fitur MVP - Portal Client (Project Owner)

#### 4.3.1 Autentikasi
- [x] **Magic link login**
  - Click link dari email → auto login (no password)
  - Session management
- [x] **First-time onboarding**
  - Welcome modal
  - Quick tour (optional)
  - Notification preferences

#### 4.3.2 Dashboard Portal
- [x] **Project overview**
  - Status: On Track, Delayed, At Risk
  - Progress percentage (big visual circle)
  - Days remaining until completion
  - Next milestone & date
  - Alert banner (jika ada issue urgent)
- [x] **Quick stats**
  - Budget: X% used of total
  - Photos: X new photos this week
  - Material: X items delivered
  - Last update: Timestamp

#### 4.3.3 Material Status Viewer
- [x] **Material tracker**
  - Visual kanban atau timeline
  - Status per material: Ordered, In Transit, Delivered, In Use
  - Expected vs actual delivery date
  - Supplier info
  - Foto material delivered
- [x] **Delay notifications**
  - Alert jika ada material delayed
  - Alasan delay visible

#### 4.3.4 Photo Gallery
- [x] **Browse foto progres**
  - Organize by: Date (newest first), Area, Photo Type
  - Thumbnail view
  - Click to expand full image
- [x] **Before/After comparison**
  - Slider untuk compare before vs after
- [x] **Photo details**
  - Timestamp, location/area, uploader name
  - Caption/description
- [x] **Download foto**
  - Download individual atau bulk download

#### 4.3.5 Budget Summary
- [x] **Budget visibility** (high-level, no detail profit margin)
  - Total project value
  - Amount spent vs remaining
  - Percentage: X% spent, Y% remaining
  - Visual progress bar
- [x] **Spending pace**
  - "On track" vs "Over budget" indicator
  - Simple breakdown: Materials X%, Labor Y%, Other Z%

#### 4.3.6 Timeline View
- [x] **Project timeline**
  - Start date, estimated completion, current phase
  - Milestones: Planned date vs actual
  - Status indicator: On Schedule, Minor Delay, Major Delay
- [x] **Delay explanations**
  - Jika ada delay, tampilkan alasan
  - Updated completion date

#### 4.3.7 Invoice & Payment
- [x] **View invoices**
  - List all invoices
  - Status: Pending, Paid
  - Due date, amount, download PDF
- [x] **Payment instructions**
  - Bank account details
  - Payment confirmation (manual mark as paid)

#### 4.3.8 Mobile Experience
- [x] **Mobile-responsive design**
  - Semua fitur accessible di mobile
  - Touch-friendly buttons (min 44px tap target)
  - Fast loading (<2 sec on 4G)
- [x] **Mobile-optimized views**
  - Dashboard simplified for mobile
  - Photo gallery swipe gesture
  - Easy navigation (bottom nav or hamburger)

### 4.4 Fitur yang TIDAK termasuk MVP (Phase 2/3)

**Phase 2:**
- Change order approval workflow
- Comment threads & collaboration
- QA checklist & inspections
- BAST digital certificate
- Advanced analytics & reporting
- Export report to PDF
- Team resource management

**Phase 3:**
- Warranty claim submission & tracking
- Native mobile app (iOS/Android)
- AI Assistant (Module 5)
- Material calculator (Module 2)
- Integration dengan supplier systems
- Integration dengan accounting software (Jurnal.id, Accurate)
- WhatsApp Business API integration
- Multi-language support (English)

---

## 5. User Stories & Acceptance Criteria

**Catatan:** User stories lengkap ada di dokumen terpisah: `User-Stories-Acceptance-Criteria.md`

### 5.1 Epic: Project Creation & Setup

**US-001: Sebagai PM, saya ingin membuat proyek baru, sehingga saya bisa mulai manage pekerjaan**

**Acceptance Criteria:**
- [ ] PM bisa akses "Buat Proyek Baru" dari dashboard
- [ ] Form berisi: Nama proyek, Client, Lokasi, Start date, Estimated end date, Total budget
- [ ] PM bisa assign diri sendiri atau PM lain sebagai project manager
- [ ] Sistem generate project number otomatis (PRJ-2025-001)
- [ ] Setelah create, redirect ke project detail page
- [ ] Project muncul di list dengan status "Planning"

### 5.2 Epic: Client Portal Access

**US-002: Sebagai PM, saya ingin invite client ke portal, sehingga client bisa lihat progres**

**Acceptance Criteria:**
- [ ] Ada button "Invite Client" di project detail page
- [ ] PM input email client
- [ ] PM set permission (Viewer/Commenter/Approver)
- [ ] Sistem kirim email dengan magic link
- [ ] Email contains: Project name, invitation message, "Lihat Proyek" button
- [ ] Jika email sudah terdaftar, langsung link access; jika baru, create user baru
- [ ] PM bisa lihat status: "Invited" vs "Accepted" (sudah login)

**US-003: Sebagai Project Owner, saya ingin login ke portal via email, sehingga saya bisa track proyek tanpa password**

**Acceptance Criteria:**
- [ ] Project owner click link dari email invitation
- [ ] Auto redirect ke portal, auto login (magic link)
- [ ] First-time user: Welcome modal muncul
- [ ] User bisa skip atau take tour
- [ ] Setelah login, bisa lihat project dashboard
- [ ] Session bertahan 7 hari (atau sampai logout)

*(Lihat dokumen User Stories lengkap untuk semua 50+ user stories)*

---

## 6. Requirements Fungsional

### 6.1 Authentication & Authorization

**Kontraktor:**
- Google OAuth (login via Google account)
- Email/password sebagai fallback
- Role-based access control: Company Owner, Project Manager, Supervisor, Accountant

**Project Owner:**
- Magic link authentication (passwordless)
- Session management (auto logout setelah 7 hari inactive)
- Access control per project (bisa lihat project A tapi tidak project B)

### 6.2 Data Management

**Multi-Tenancy:**
- Setiap company data isolated (tidak bisa lihat data company lain)
- Soft delete (data tidak benar-benar dihapus, hanya di-flag deletedAt)

**Audit Trail:**
- Track who created/updated record (createdBy, updatedBy)
- Track when (createdAt, updatedAt, deletedAt)

**Data Privacy:**
- Project owner TIDAK bisa lihat:
  * Profit margin kontraktor
  * Internal notes kontraktor
  * Supplier pricing details (hanya total material cost)
- Project owner BISA lihat:
  * Total budget & spending
  * High-level cost breakdown
  * Material status & photos
  * Progress photos
  * Timeline & milestones
  * Invoices

### 6.3 File Upload & Storage

**Photo Upload:**
- Support format: JPG, PNG, HEIC (auto-convert)
- Max file size: 10MB per photo
- Client-side compression (jika >2MB, compress to ~1MB)
- Auto-extract EXIF data: geolocation, timestamp, device
- Generate thumbnail (300x300px) untuk fast loading

**Document Upload:**
- Support format: PDF, JPG, PNG
- Max file size: 20MB per document
- Kontrak, BAST, drawings, specifications

**Storage Strategy:**
- Cloud storage (Supabase Storage atau Cloudinary atau AWS S3)
- CDN untuk fast delivery di Indonesia
- Backup otomatis

### 6.4 Notifications

**Email Notifications:**
- Project owner: Material delayed, milestone completed, new invoice, new photos
- Kontraktor: Client login pertama kali, client comment, payment received
- Frequency: Bisa diatur (immediate, daily digest, weekly digest)

**In-App Notifications:**
- Bell icon dengan unread count
- List notifications dengan timestamp
- Mark as read/unread

### 6.5 Reporting & Export

**For Project Owner:**
- Export project report to PDF (progress, photos, budget, timeline)
- Download all photos as ZIP
- Download invoice PDF

**For Kontraktor:**
- Export project profitability report
- Export material usage report
- Export invoice list to Excel

---

## 7. Requirements Non-Fungsional

### 7.1 Performance

**Response Time:**
- Page load: <2 detik (desktop), <3 detik (mobile 4G)
- API response: <500ms untuk kebanyakan endpoint
- Photo upload: Progress indicator, tidak blocking UI
- Database query: Indexed untuk fast retrieval

**Scalability:**
- Support 100 concurrent users (MVP)
- Support 10,000+ projects total
- Support 100,000+ photos
- Plan untuk scale ke 1,000+ concurrent users (Phase 2)

**Caching:**
- Photo thumbnails di-cache di CDN
- Static assets (CSS, JS) di-cache
- API response caching untuk data yang jarang berubah

### 7.2 Security

**Authentication:**
- OAuth 2.0 untuk Google login
- JWT tokens untuk session management
- Token expiry & refresh mechanism
- Rate limiting: Max 100 requests/minute per user

**Data Protection:**
- HTTPS only (SSL certificate)
- SQL injection prevention (ORM/Prisma)
- XSS prevention (sanitize user input)
- CSRF protection
- Environment variables untuk secrets (no hardcode)

**Access Control:**
- Row-level security (RLS) jika pakai Supabase
- Atau API-level authorization checks
- Prevent horizontal privilege escalation (user A tidak bisa akses data company B)

### 7.3 Usability & Accessibility

**Usability:**
- Bahasa Indonesia sebagai primary language
- Intuitive UI (minimal training needed)
- Consistent design system
- Clear error messages
- Confirmation modals untuk destructive actions

**Accessibility:**
- WCAG 2.1 Level AA compliance (target)
- Keyboard navigation support
- Alt text untuk images
- Adequate color contrast (dark theme)
- Screen reader friendly

**Mobile Experience:**
- Touch-friendly (min 44x44px tap targets)
- Responsive breakpoints: 320px, 768px, 1024px, 1440px
- Mobile-first design approach
- Fast loading on 4G connection
- Offline-friendly (cache critical data) - Phase 2

### 7.4 Browser & Device Support

**Desktop Browsers:**
- Chrome (latest 2 versions)
- Firefox (latest 2 versions)
- Safari (latest 2 versions)
- Edge (latest 2 versions)

**Mobile Browsers:**
- Chrome Mobile (Android)
- Safari Mobile (iOS)
- Support iOS 14+ and Android 9+

**Devices:**
- Desktop: 1920x1080, 1440x900, 1366x768
- Tablet: iPad, Android tablets
- Mobile: iPhone 12/13/14/15, Samsung Galaxy S series, Xiaomi

### 7.5 Reliability & Availability

**Uptime:**
- Target: 99.5% uptime (MVP)
- Maintenance window: Announce 24 hours before
- Max 4 hours downtime per month

**Backup:**
- Database backup: Daily automated
- Retention: 30 days
- Photo storage: Redundant (cloud provider handles this)

**Error Handling:**
- Graceful degradation (jika service down, show cached data)
- User-friendly error messages (no technical jargon)
- Error logging & monitoring (Sentry atau similar)

**Monitoring:**
- Uptime monitoring (UptimeRobot atau similar)
- Performance monitoring (Vercel Analytics atau similar)
- Error tracking (Sentry)
- Usage analytics (PostHog atau Mixpanel)

---

## 8. Tech Stack (Rekomendasi)

### 8.1 Frontend

**Framework:**
- Next.js 14+ (App Router)
- TypeScript (type safety)
- React 18+

**Styling:**
- Tailwind CSS 3.4+
- Dark theme as default
- shadcn/ui component library (optional)

**State Management:**
- React Context API (untuk simple state)
- Zustand atau Jotai (jika butuh global state yang complex)

**Forms:**
- React Hook Form
- Zod untuk validation

**Photo Upload:**
- react-dropzone
- browser-image-compression

### 8.2 Backend & Database

**Option A: Supabase (Recommended untuk MVP)**
- PostgreSQL database (hosted by Supabase)
- Supabase Auth (passwordless, OAuth)
- Supabase Storage (file storage)
- Supabase Realtime (optional untuk live updates)
- Row-level security built-in

**Keuntungan Supabase:**
- Consistency dengan Sales App (sudah pakai Supabase)
- All-in-one (database, auth, storage, hosting)
- Free tier generous (500MB database, 1GB storage, 50,000 monthly active users)
- Scalable (bisa upgrade ke paid plan)
- Fast setup (no DevOps needed)

**Option B: Self-Hosted PostgreSQL + Prisma**
- PostgreSQL (DigitalOcean, AWS RDS, atau Railway)
- Prisma ORM
- NextAuth.js untuk authentication
- AWS S3 atau Cloudinary untuk file storage

**Keuntungan Self-Hosted:**
- More control
- Potentially cheaper at scale
- Flexibility

**Rekomendasi:** **Supabase untuk MVP** (speed to market, team sudah familiar)

### 8.3 Infrastructure

**Hosting:**
- Vercel (recommended untuk Next.js) - Easy deployment, edge functions, CDN
- OR Supabase Hosting (jika full Supabase stack)

**CDN:**
- Vercel Edge Network (global)
- Cloudflare (jika self-host)

**Email Service:**
- Resend (recommended - developer-friendly, affordable)
- OR SendGrid
- OR AWS SES

**Monitoring & Analytics:**
- Vercel Analytics (performance)
- Sentry (error tracking)
- PostHog atau Mixpanel (product analytics)
- Google Analytics (optional)

---

## 9. Estimasi Budget Infrastructure (Monthly)

### 9.1 Supabase Stack (Recommended)

**Supabase:**
- Free tier: $0 (sampai 500MB DB, 1GB storage, 50K MAU)
- Pro: $25/month (8GB DB, 100GB storage, 100K MAU) - **target setelah 3 bulan**
- Team: $599/month (jika butuh priority support) - Phase 2

**Vercel Hosting:**
- Hobby: $0 (unlimited personal projects)
- Pro: $20/month per member (commercial projects, better limits)

**Resend Email:**
- Free: $0 (3,000 emails/month)
- Pro: $20/month (50,000 emails/month) - **target setelah beta**

**Monitoring:**
- Sentry: $0 (5K errors/month)
- PostHog: $0 (1M events/month)

**Total MVP (First 3 months):**
- $0-45/month (FREE atau Pro plan)

**Total After Growth (Month 4-6):**
- ~$100-150/month

### 9.2 Self-Hosted Stack (Alternative)

**Database:**
- Railway PostgreSQL: $5-20/month
- OR DigitalOcean Managed DB: $15-60/month

**Hosting:**
- Vercel Pro: $20/month
- OR DigitalOcean Droplet: $12-24/month

**File Storage:**
- Cloudflare R2: $0.015/GB (sangat murah)
- OR AWS S3: ~$5-20/month

**Email:**
- Resend: $20/month

**Total:** ~$50-120/month

**Rekomendasi:** Mulai dengan **Supabase Free Tier**, scale sesuai kebutuhan.

---

## 10. Timeline & Milestones

### 10.1 Development Timeline (Oktober 2025 - Maret 2026)

**Week 1-2: Setup & Design (Oct 28 - Nov 10)**
- [ ] Hire UI/UX designer
- [ ] Create Figma wireframes (10 core screens)
- [ ] Setup development environment
- [ ] Initialize Next.js + Supabase project
- [ ] Setup database schema

**Week 3-4: Sprint 1 - Authentication & Project Setup (Nov 11 - Nov 24)**
- [ ] Google OAuth login
- [ ] Company registration
- [ ] User management
- [ ] Project CRUD
- [ ] Basic dashboard

**Week 5-6: Sprint 2 - Material & Progress Tracking (Nov 25 - Dec 8)**
- [ ] Material management
- [ ] Photo upload (with geolocation)
- [ ] Material status updates
- [ ] Progress by area

**Week 7-8: Sprint 3 - Timeline & Budget (Dec 9 - Dec 22)**
- [ ] Milestone management
- [ ] Timeline view
- [ ] Budget tracking
- [ ] Expense recording

**Week 9-10: Sprint 4 - Client Portal Foundation (Dec 23 - Jan 5, 2026)**
- [ ] Magic link authentication
- [ ] Portal dashboard
- [ ] Material status viewer (for project owner)
- [ ] Photo gallery viewer

**Week 11-12: Sprint 5 - Client Portal Complete (Jan 6 - Jan 19)**
- [ ] Budget summary view
- [ ] Timeline view (project owner)
- [ ] Invoice viewer
- [ ] Mobile responsive polish

**Week 13-14: Sprint 6 - Invoicing & Polish (Jan 20 - Feb 2)**
- [ ] Invoice generation
- [ ] PDF generation
- [ ] Invoice tracking
- [ ] Email notifications

**Week 15-16: Sprint 7 - Testing & Bug Fixes (Feb 3 - Feb 16)**
- [ ] Internal testing
- [ ] Bug fixes
- [ ] Performance optimization
- [ ] Security audit

**Week 17-19: Beta Testing (Feb 17 - Mar 9)**
- [ ] Recruit 3-5 contractors
- [ ] Onboard & train users
- [ ] Gather feedback
- [ ] Iterate based on feedback

**Week 20-21: Launch Prep (Mar 10 - Mar 23)**
- [ ] Final polish
- [ ] Create help documentation
- [ ] Prepare marketing materials
- [ ] Soft launch

**Week 22: Official Launch (Mar 24 - Mar 31, 2026)**
- [ ] Public launch
- [ ] Marketing campaign
- [ ] Monitor & support

### 10.2 Key Milestones

| Milestone | Target Date | Deliverables |
|-----------|-------------|--------------|
| Kickoff & Design | Nov 10, 2025 | Figma wireframes, PRD approved |
| MVP Development Start | Nov 11, 2025 | Dev environment ready |
| Authentication Complete | Nov 24, 2025 | Login & project CRUD working |
| Core Features Complete | Dec 22, 2025 | Material, photo, timeline, budget |
| Client Portal Complete | Jan 19, 2026 | Full portal functional |
| Internal Testing Done | Feb 16, 2026 | Bug-free, ready for beta |
| Beta Testing Complete | Mar 9, 2026 | User feedback implemented |
| **Official Launch** | **Mar 24, 2026** | **Public release** |

---

## 11. Risks & Mitigation

### 11.1 Technical Risks

**Risk 1: Performance issues dengan banyak foto**
- **Mitigation:** Image compression, lazy loading, CDN, thumbnail generation

**Risk 2: Supabase free tier limit tercapai lebih cepat**
- **Mitigation:** Monitor usage, upgrade ke Pro plan jika perlu

**Risk 3: Complex database queries lambat**
- **Mitigation:** Proper indexing, caching, pagination

**Risk 4: Mobile upload gagal dengan koneksi jelek**
- **Mitigation:** Retry mechanism, queue system, offline support (Phase 2)

### 11.2 User Adoption Risks

**Risk 1: Kontraktor tidak mau update data secara konsisten**
- **Mitigation:** Gamification, reminders, onboarding training, show value

**Risk 2: Project owner tidak pakai portal (tetap telepon)**
- **Mitigation:** Email notifications, push updates, show time saved

**Risk 3: Learning curve terlalu tinggi**
- **Mitigation:** Simple UX, onboarding wizard, video tutorials, customer support

### 11.3 Business Risks

**Risk 1: Kontraktor tidak mau bayar subscription**
- **Mitigation:** Generous free tier, show clear ROI, testimonials

**Risk 2: Kompetitor launch produk serupa**
- **Mitigation:** Speed to market (Q1 2026), focus on niche (painting-specific), network effect

**Risk 3: Budget overrun untuk infrastructure**
- **Mitigation:** Start with free tiers, monitor spending, optimize costs

---

## 12. Out of Scope (Tidak Termasuk MVP)

Fitur-fitur ini bagus tapi **TIDAK** akan dibangun di MVP:

1. ❌ Native mobile app (iOS/Android) - PWA responsive web sudah cukup
2. ❌ Offline mode - Internet required untuk MVP
3. ❌ WhatsApp integration - Email notifications saja
4. ❌ Payment gateway integration - Manual payment tracking
5. ❌ Accounting software integration (Jurnal.id, Accurate)
6. ❌ Supplier system integration (auto material status update)
7. ❌ Multi-language support - Bahasa Indonesia only
8. ❌ Advanced analytics & business intelligence
9. ❌ AI-powered features (Module 5 - AI Assistant)
10. ❌ Material calculator (Module 2)
11. ❌ QA checklist automation
12. ❌ BAST digital signature (e-signature integration)
13. ❌ Warranty claim workflow
14. ❌ Change order approval workflow (comment only)
15. ❌ Team resource management & scheduling
16. ❌ Time tracking untuk labor hours
17. ❌ Custom branding (white-label) untuk contractors
18. ❌ API access untuk third-party integrations

**Prinsip:** Build core value proposition dulu (transparansi via portal), tambah fitur advanced setelah validated.

---

## 13. Approval & Sign-Off

### 13.1 Document Approvers

| Role | Name | Approval Status | Date |
|------|------|-----------------|------|
| Product Owner | Kevin Zakaria | ⏳ Pending | - |
| Lead Developer | Kevin Zakaria | ⏳ Pending | - |
| UI/UX Designer | TBD (akan di-hire) | ⏳ Pending | - |

### 13.2 Change Log

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | Oct 28, 2025 | Kevin Z + Claude | Initial PRD creation |

### 13.3 Next Steps Setelah Approval

1. [ ] Share PRD dengan co-founders/stakeholders untuk review
2. [ ] Finalize budget & infrastructure decisions
3. [ ] Hire UI/UX designer
4. [ ] Kick off design phase (wireframes di Figma)
5. [ ] Setup development environment
6. [ ] Create detailed technical specification
7. [ ] Begin Sprint 1 development

---

## 14. Appendix

### 14.1 Referensi Dokumen

- `User-Stories-Acceptance-Criteria.md` - Detailed user stories
- `UI-UX-Design-Brief.md` - Design guidelines untuk UI/UX team
- `User-Personas.md` - Detailed user personas
- `Information-Architecture.md` - Site map & navigation structure
- `database-schema.md` - Database design (English)
- `user-flows.md` - User journey maps (English)
- `Infrastructure-Comparison.md` - Tech stack comparison

### 14.2 Glossary (Istilah)

| Istilah | Definisi |
|---------|----------|
| **Project Owner** | Client kontraktor (pemilik proyek seperti mall, hotel) yang dapat akses Portal Client |
| **Kontraktor** | Perusahaan pengecatan yang membayar subscription PakeAja |
| **Portal Client** | Interface web khusus untuk project owner melihat progres proyek |
| **MVP** | Minimum Viable Product - versi produk paling sederhana yang punya value |
| **Magic Link** | Link di email yang auto-login tanpa perlu password |
| **Two-sided Platform** | Platform dengan 2 tipe user yang saling benefit (kontraktor & project owner) |
| **BAST** | Berita Acara Serah Terima - dokumen official handover project |

### 14.3 Competitive Analysis Reference

Kompetitor yang sudah dianalisa:
- Procore (US - too complex, enterprise)
- Buildertrend (US - too complex, expensive)
- PaintScout (US - estimating only, no portal)
- KANNA (Japan - contractor efficiency, minimal transparency)
- Fieldwire (US - general construction, not painting-specific)

**PakeAja Advantages:**
- ✅ Painting-specific (bukan generic construction)
- ✅ Indonesia focus (bahasa, workflow, BAST, PPN)
- ✅ Client Portal as key differentiator
- ✅ Affordable pricing untuk SME Indonesia
- ✅ Network effect strategy

---

**Dokumen ini adalah living document dan akan di-update sesuai feedback dan learnings.**

---

## 🎯 Ready to Apply?

You've completed the full documentation journey! Now you understand:
- ✅ The problem PakeAja solves
- ✅ Who you're designing for (user personas)
- ✅ What you need to deliver (scope & deliverables)
- ✅ How complex this project is
- ✅ How users flow through the system
- ✅ How everything is structured
- ✅ The design direction and guidelines
- ✅ Complete product requirements

**Next Step: Submit Your Application**

📋 **Application Form:** https://forms.gle/7tZRm69iqestsrKr9

💼 **Job Posting:** https://jobboard.fastwork.id/jobs/ad3adbd8-03e0-476d-a4ba-159c0135cde0

Looking forward to seeing your portfolio! 🚀
