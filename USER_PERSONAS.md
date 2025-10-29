# User Personas - PakeAja

---

**📚 Documentation Journey** | Step 2 of 8

[Project Overview](PROJECT_OVERVIEW.md) → **→ User Personas** → [Scope](SCOPE.md) → [Design Complexity](DESIGN_COMPLEXITY.md) → [User Flows](USER_FLOWS.md) → [Information Architecture](INFORMATION_ARCHITECTURE.md) → [Design Brief](DESIGN_BRIEF.md) → [PRD](PRD.md)

**[← Previous: Project Overview](PROJECT_OVERVIEW.md)**

---

**Versi:** 1.0 | **Tanggal:** 28 Oktober 2025

---

## Overview

Dokumen ini mendefin isikan personas untuk kedua sisi platform PakeAja:
1. **Kontraktor** (pengguna berbayar)
2. **Project Owner** (pengguna portal gratis)

Personas ini based on user research dan interview dengan calon pengguna.

---

## Kontraktor Personas

### Persona 1: Budi - Pemilik Perusahaan Pengecatan

**Demographics:**
- **Nama:** Budi Santoso
- **Usia:** 45 tahun
- **Posisi:** Owner & CEO, PT Mitra Cat Indonesia
- **Lokasi:** Jakarta Selatan
- **Pendidikan:** S1 Teknik Sipil
- **Pengalaman:** 15 tahun di industri pengecatan

**Company Profile:**
- **Ukuran perusahaan:** 25 karyawan (5 PM, 20 field workers)
- **Proyek aktif:** 8-12 proyek simultaneously
- **Nilai proyek:** Rp 200 juta - Rp 2 miliar per proyek
- **Clients:** Shopping malls, perkantoran, hotel

**Tech Savviness:**
- 🟡 **Sedang** - Pakai WhatsApp Business, email, Excel
- Tidak familiar dengan software management yang complex
- Lebih suka interface yang simple dan straightforward

**Goals:**
- Menang lebih banyak tender (target: naik 20% win rate)
- Terlihat lebih profesional di mata clients
- Get paid faster (reduce payment cycle dari 45 hari ke 30 hari)
- Scale business tanpa hire lebih banyak admin staff

**Pain Points:**
- *"Client selalu telepon tanya progres, team saya buang waktu jawab pertanyaan yang sama berkali-kali"*
- *"Susah track semua proyek sekaligus, kadang ada yang terlewat"*
- *"Kalah tender sama kompetitor yang terlihat lebih 'tech-savvy' dan professional"*
- *"Payment lambat karena client tidak trust progress yang kita report"*

**Behavior Patterns:**
- Check proyek status setiap pagi (1 jam)
- Meeting dengan PMs setiap Senin pagi
- Site visit 2-3x per minggu ke proyek yang critical
- Fokus pada profitability dan cash flow

**Jobs to Be Done:**
- *"When saya harus report ke client tentang project progress, I want to show transparent data dengan proof, so that client trust kami dan approve invoice tanpa delay"*
- *"When saya evaluate team performance, I want to see KPIs semua proyek dalam satu dashboard, so that saya tahu siapa yang perform well dan siapa yang perlu improvement"*

**Preferred Features:**
- Dashboard overview semua proyek (traffic light: green, yellow, red)
- One-click invite client ke portal (untuk show professionalism)
- Budget vs actual spending (profitability tracking)
- Invoice generation & tracking

**Frustrations with Current Tools:**
- Excel: Manual, error-prone, susah share dengan team
- WhatsApp: Messy, conversation hilang, no structure
- Email: Delayed responses, document versions confusing

**Quote:**
> *"Saya butuh sistem yang bisa tunjukkan ke client bahwa perusahaan saya profesional. Kalau client bisa lihat sendiri progress proyek mereka, saya yakin mereka akan lebih trust dan bayar tepat waktu."*

---

### Persona 2: Rina - Project Manager

**Demographics:**
- **Nama:** Rina Wulandari
- **Usia:** 32 tahun
- **Posisi:** Project Manager, PT Mitra Cat Indonesia
- **Lokasi:** Jakarta
- **Pendidikan:** D3 Teknik Arsitektur
- **Pengalaman:** 8 tahun di konstruksi, 4 tahun sebagai PM

**Responsibilities:**
- Manage 2-3 proyek secara bersamaan
- Daily coordination dengan field team, suppliers, clients
- Track budget, timeline, material
- Report progress ke owner & client

**Tech Savviness:**
- 🟢 **Tinggi** - Comfortable dengan berbagai apps
- Pakai Google Sheets, Trello, WhatsApp, Google Drive

**Goals:**
- Selesaikan proyek on-time dan on-budget (bonus tergantung ini!)
- Minimize rework (quality control)
- Good relationship dengan client (untuk repeat business)
- Dokumentasi lengkap untuk warranty & future reference

**Pain Points:**
- *"Terlalu banyak waktu untuk admin: update Excel, compile foto, buat laporan manual untuk client"*
- *"Material supplier sering telat, tapi saya baru tahu pas field team complain"*
- *"Client minta update foto, saya harus minta field team via WhatsApp, tunggu mereka balas, baru forward ke client - inefficient!"*
- *"Kalau client telpon pas saya meeting, saya miss info penting dan harus chase down info lagi"*

**Typical Day:**
- 7am: Check WhatsApp messages dari field team
- 8-9am: Site visit proyek A
- 10am: Meeting dengan supplier
- 11am-12pm: Update Excel tracker, compile foto progres
- 1-2pm: Call client untuk report progress
- 3pm: Site visit proyek B
- 5pm: Email laporan ke owner
- Evening: Respond WhatsApp dari team

**Jobs to Be Done:**
- *"When field team upload foto progres, I want it to automatically organize by project & date, so that saya tidak perlu manual compile waktu client minta update"*
- *"When material status berubah (ordered, delivered, delayed), I want client to see it immediately in the portal, so that saya tidak perlu jawab pertanyaan 'kapan cat datang?' berkali-kali"*

**Preferred Features:**
- Quick photo upload dari mobile (dari site)
- Material status tracker (visual, easy to update)
- Client portal invitation (so client self-serve untuk info)
- Budget alerts (warn jika trending over budget)
- Milestone checklist

**Frustrations with Current Tools:**
- Excel: Slow, not real-time, no collaboration
- WhatsApp: Too many groups, susah cari info lama
- Google Drive: Folder organization messy, client bingung cara akses

**Quote:**
> *"Kalau ada sistem yang bisa auto-update client tentang progress, saya bisa save 1-2 jam sehari yang biasa saya pakai untuk jawab pertanyaan client yang sama terus. Itu waktu bisa saya pakai untuk actually manage project!"*

---

### Persona 3: Agus - Field Supervisor

**Demographics:**
- **Nama:** Agus Prasetyo
- **Usia:** 38 tahun
- **Posisi:** Field Supervisor
- **Lokasi:** Tangerang
- **Pendidikan:** SMA
- **Pengalaman:** 12 tahun sebagai applicator, 5 tahun sebagai supervisor

**Responsibilities:**
- On-site supervision (1 proyek at a time)
- Manage 3-5 workers
- Quality control
- Report daily progress ke PM
- Coordinate material delivery

**Tech Savviness:**
- 🟡 **Sedang** - Pakai smartphone untuk WhatsApp, camera, Google Maps
- Tidak familiar dengan apps yang complex
- Prefer simple, intuitive interface

**Goals:**
- Selesaikan pekerjaan sesuai standard kualitas
- Avoid rework
- Keep PM & owner happy
- Aman (safety first)

**Pain Points:**
- *"PM selalu minta foto progres, tapi saya sibuk supervise team. Kadang lupa foto, nanti PM marah"*
- *"Susah explain ke PM kondisi di lapangan via WhatsApp text. Foto lebih jelas tapi ribet kalau harus kirim banyak foto via WA (compress quality, lama upload)"*
- *"Material datang terlambat, tapi saya tidak tahu harus inform siapa dan bagaimana"*

**Typical Day:**
- 7am: Arrive on-site, briefing dengan workers
- 8am-12pm: Supervise pekerjaan, quality check
- 10am: Foto before/during work (kalau ingat)
- 12-1pm: Lunch break
- 1-4pm: Supervise, handle issues yang muncul
- 3pm: Material delivery arrived, need to inspect
- 4:30pm: Cleanup, briefing untuk besok
- 5pm: WhatsApp PM dengan update, kirim foto

**Jobs to Be Done:**
- *"When saya di site dan lihat something worth documenting, I want to quickly take photo & upload dengan 2-3 taps, so that saya tidak waste time dan lupa later"*
- *"When material datang, I want to upload foto + update status easily dari hp, so that PM dan client langsung tahu tanpa saya perlu telepon"*

**Preferred Features:**
- Mobile-first photo upload (simple, fast, no complicated forms)
- Auto-capture geolocation (tidak perlu manual input lokasi)
- Minimal text input required (prefer dropdown & selections)
- Offline queue (jika internet jelek di site, foto ke-queue dan auto-upload nanti)

**Frustrations with Current Tools:**
- WhatsApp: Foto ke-compress (quality buruk), susah organize nanti
- Google Drive: Ribet upload dari mobile, folder structure confusing
- Email: Tidak praktis dari hp, especially dengan attachment banyak

**Quote:**
> *"Saya butuh app yang simple. Foto, pilih area, upload - done. Kalau terlalu banyak form isi, saya tidak sempat. Pekerjaan saya di lapangan, bukan di depan komputer."*

---

## Project Owner Personas

### Persona 4: Dian - General Manager Shopping Mall

**Demographics:**
- **Nama:** Dian Pratama
- **Usia:** 42 tahun
- **Posisi:** General Manager, Grand Plaza Mall
- **Lokasi:** Jakarta Pusat
- **Pendidikan:** S1 Manajemen Bisnis, S2 MBA
- **Pengalaman:** 15 tahun di retail & mall management

**Responsibilities:**
- Overall mall operations
- Report ke CEO & board of directors
- Budget management (operational & CAPEX)
- Vendor management (security, cleaning, maintenance, construction)

**Tech Savviness:**
- 🟢 **Sedang-Tinggi** - Pakai laptop & smartphone daily
- Familiar dengan dashboard & reporting tools
- Expect professional software (not Excel spreadsheets)

**Project Context:**
- **Proyek:** Repainting seluruh mall (Rp 800 juta)
- **Duration:** 8 minggu
- **Pain:** Painting harus dilakukan malam hari (mall tutup) agar tidak ganggu pengunjung
- **Stakeholders:** CEO, Maintenance Manager, Marketing (grand re-opening planning)

**Goals:**
- Proyek selesai on-time (grand re-opening sudah dijadwalkan!)
- Budget tidak overrun (already approved by board, sulit minta tambahan)
- Quality bagus (ini akan di-foto untuk marketing materials)
- Minimal disruption ke mall operations

**Pain Points:**
- *"CEO saya tanya 'bagaimana painting progress?' setiap weekly meeting. Saya harus telepon kontraktor dulu untuk cari tahu, terus compile info sendiri untuk presentation"*
- *"Kontraktor bilang 'material delayed', tapi saya tidak tahu detail: delayed berapa lama? Kenapa? Apakah affect timeline completion?"*
- *"Saya busy dengan operations, tidak bisa ke site setiap hari untuk check progress. Tapi kalau tidak check, saya khawatir kontraktor asal-asalan"*
- *"Invoice dari kontraktor kadang tidak jelas: charge untuk apa? Sesuai scope atau ada extra?"*

**Behavior Patterns:**
- Check email 5-10x per hari
- Weekly meeting dengan CEO (Senin pagi, need project update!)
- Monthly meeting dengan board (report all CAPEX spending)
- Site inspection 1x per minggu (jika sempat)

**Jobs to Be Done:**
- *"When CEO tanya project progress, I want to quickly show dashboard dengan visual data (photos, timeline, budget), so that saya terlihat on-top-of-things dan CEO trust saya"*
- *"When ada delay atau issue, I want to understand the reason immediately & see how it affects timeline, so that saya bisa plan accordingly (adjust grand opening date jika perlu)"*
- *"When finance department review invoice, I want to show them detailed breakdown & proof of work (photos, milestones completed), so that payment approval tidak delay"*

**Preferred Features:**
- Dashboard yang professional (untuk screenshot dan kirim ke CEO)
- Material tracking (where's my paint?)
- Budget transparency (am I on track?)
- Photo gallery (proof of progress)
- Download report as PDF (untuk board meeting presentation)

**Frustrations with Contractors:**
- Lack of transparency ("trust me" bukan good enough)
- Delayed responses (saya busy, jangan bikin saya chase)
- Unclear invoicing (detail breakdown tolong!)

**Quote:**
> *"Saya appreciate kalau kontraktor proactive update saya, instead of saya harus telepon mereka. Portal yang bisa saya check kapan saja adalah game-changer. Saya akan prioritize kontraktor yang offer transparency ini untuk future projects."*

---

### Persona 5: Hendra - Facility Manager Corporate Office

**Demographics:**
- **Nama:** Hendra Kusuma
- **Usia:** 35 tahun
- **Posisi:** Facility Manager, PT Teknologi Nusantara (tech company)
- **Lokasi:** Jakarta Selatan (office di SCBD)
- **Pendidikan:** S1 Teknik Industri
- **Pengalaman:** 10 tahun di facility & building management

**Responsibilities:**
- Manage facility team (cleaning, security, maintenance)
- Vendor management (20+ vendors)
- Budget tracking (operational & maintenance)
- Ensure office environment optimal untuk employee productivity

**Tech Savviness:**
- 🟢🟢 **Tinggi** - Very comfortable dengan technology
- Pakai CMMS (facility management software), Slack, project management tools
- Expect vendors to be tech-savvy juga

**Project Context:**
- **Proyek:** Repainting office (5 floors, Rp 600 juta)
- **Duration:** 6 minggu (harus minimal disruption - painting weekend & after-hours)
- **Stakeholders:** HR (employee experience), Finance (budget approval), Management

**Goals:**
- Minimal disruption ke employees (painting harus off-hours)
- Budget control (CFO scrutinize every expense!)
- Quality control (office adalah face of company untuk clients & candidates)
- Proper documentation (untuk audit & future reference)

**Pain Points:**
- *"Finance department selalu minta justification untuk setiap invoice payment. Saya harus compile evidence sendiri: foto, milestone checklist, scope of work. Inefficient!"*
- *"Painting smell bisa ganggu employees. Saya perlu tahu exact schedule: lantai berapa, hari apa, jam berapa, supaya saya bisa inform HR & employees"*
- *"Saya manage 20+ vendors. Kalau setiap vendor saya harus chase untuk update, I don't have time for anything else. Self-service portal adalah must."*
- *"Documentation penting untuk warranty. Kalau 6 bulan kemudian cat mengelupas, saya perlu bukti: paint brand apa yang dipakai? Application nya sesuai standard atau tidak?"*

**Behavior Patterns:**
- Morning routine: Check dashboards untuk all facility metrics
- Weekly vendor review: Check semua ongoing projects
- Monthly reporting: Compile budget actuals vs forecast untuk CFO
- Quarterly audit: Prepare documentation untuk internal audit

**Jobs to Be Done:**
- *"When finance tanya 'invoice ini untuk apa?', I want to instantly show them: milestone completed, photos, detailed breakdown, so that payment approval tidak delay dan vendor tidak complain"*
- *"When employees complain about smell atau disruption, I want to see exact schedule & area yang sedang dikerjakan, so that saya bisa explain & set expectations"*
- *"When CFO ask 'are we on budget?', I want to show real-time spending vs budget dengan visual chart, so that CFO trust my budget management"*

**Preferred Features:**
- Professional, data-driven dashboard (untuk screenshot untuk reports)
- Real-time budget tracking (trending over/under budget?)
- Detailed timeline with areas (so I can inform HR which floor affected when)
- Invoice integration (link invoice to milestones & photos - easy justification)
- Warranty documentation (TDS, application process, QA reports)
- Download all documents as ZIP (for audit archive)

**Frustrations with Contractors:**
- Manual processes (why still use Excel?!)
- Poor documentation (saya minta TDS, mereka lupa kasih)
- Reactive communication (I have to ask for updates, they don't proactively inform)

**Quote:**
> *"In 2025, I expect vendors to be digital. Kalau kontraktor masih pakai WhatsApp untuk project management, itu red flag. Portal yang professional dengan real-time data adalah basic expectation saya. PakeAja is exactly what I've been looking for."*

---

### Persona 6: Siti - Operations Manager Hotel

**Demographics:**
- **Nama:** Siti Nurhaliza
- **Usia:** 38 tahun
- **Posisi:** Operations Manager, Grandview Hotel (4-star, 200 rooms)
- **Lokasi:** Surabaya
- **Pendidikan:** S1 Hospitality Management
- **Pengalaman:** 12 tahun di hotel operations

**Responsibilities:**
- Daily hotel operations (front desk, housekeeping, F&B, maintenance)
- Guest satisfaction (reviews, complaints, feedback)
- Coordinate renovations & maintenance projects
- Report ke General Manager & Regional Manager

**Tech Savviness:**
- 🟢 **Sedang-Tinggi** - Pakai hotel management system (PMS) daily
- Comfortable dengan dashboards & reports

**Project Context:**
- **Proyek:** Repainting hotel exterior & common areas (Rp 500 juta)
- **Duration:** 4 minggu (kritical: occupancy season ahead!)
- **Challenge:** Cannot disrupt guests! Painting harus strategic (area by area, night time untuk lobby)

**Goals:**
- Zero guest complaints tentang painting
- Selesai sebelum high-season (occupancy naik 80%+)
- Quality harus premium (ini 4-star hotel, tidak bisa terlihat murahan)
- Photo documentation untuk marketing materials

**Pain Points:**
- *"Tamu complain tentang smell, noise, scaffolding. Saya perlu tahu exact schedule kontraktor supaya bisa inform guests & minimize impact"*
- *"General Manager tanya 'kapan selesai?' setiap hari. Kontraktor bilang 'on track' tapi tidak jelas definition nya. I need exact timeline!"*
- *"Marketing mau foto 'after renovation' untuk website & Instagram. Tapi saya harus coordinate dengan kontraktor untuk photo session timing. Kalau punya access ke progress photos, marketing bisa planning ahead"*

**Behavior Patterns:**
- Morning: Walk-through hotel (check cleanliness, maintenance issues)
- Throughout day: Handle guest issues, staff coordination
- Evening: Review day's operations, plan tomorrow
- Weekly: Meeting dengan GM, report projects & challenges
- Monthly: Review guest satisfaction scores, occupancy, revenue

**Jobs to Be Done:**
- *"When planning daily operations, I want to see kontraktor's schedule (today kerja di area mana, jam berapa), so that saya bisa brief team & inform guests jika perlu"*
- *"When guests ask 'kapan renovation selesai?', I want to give them exact date, so that they're reassured dan tidak check-out early"*
- *"When GM asks for progress, I want to show photos & timeline instantly from my phone (even during walk-through), so that I'm always informed & look competent"*

**Preferred Features:**
- Mobile-first (saya always on the go di hotel)
- Schedule visibility (today's work area & timing)
- Photo gallery (untuk marketing & my own QA checks)
- Timeline with clear milestones
- Alerts/notifications (jika ada delay or schedule change)

**Frustrations with Contractors:**
- Poor communication (last-minute changes, I don't have time for surprises!)
- No visibility ke schedule (I need to plan around their work!)
- Quality issues discovered late (if I can see progress photos earlier, I can catch issues sooner)

**Quote:**
> *"Hotel operations adalah 24/7. I don't have luxury untuk sit down dan compile reports. I need information at my fingertips, from my phone, anytime. Portal yang mobile-friendly with clear schedule & photos is exactly what I need."*

---

## Persona Summary Table

| Persona | Type | Tech Savvy | Primary Device | Key Need | Most Important Feature |
|---------|------|------------|----------------|----------|------------------------|
| **Budi** | Owner | 🟡 Sedang | Desktop | Professionalism, Win more deals | Client Portal invitation |
| **Rina** | PM | 🟢 Tinggi | Desktop + Mobile | Time saving, Efficiency | Auto-updates to client |
| **Agus** | Field Supervisor | 🟡 Sedang | Mobile | Simple, Quick | Easy photo upload |
| **Dian** | GM Mall | 🟢 Sedang-Tinggi | Desktop + Mobile | Report to CEO, Transparency | Professional dashboard |
| **Hendra** | FM Corporate | 🟢🟢 Tinggi | Desktop | Budget justification, Documentation | Budget tracking, Invoice detail |
| **Siti** | Ops Manager Hotel | 🟢 Sedang-Tinggi | Mobile | Schedule visibility, Guest satisfaction | Timeline, Notifications |

---

## How to Use These Personas

### For Product Decisions:
- *"Would Rina find this feature useful in her daily workflow?"*
- *"Is this too complex for Agus to use from site?"*
- *"Does this help Dian report to her CEO?"*

### For Design Decisions:
- *"Can Siti use this on mobile while walking through hotel?"*
- *"Is this dashboard professional enough for Hendra to screenshot for CFO?"*
- *"Will Budi understand this without training?"*

### For Feature Prioritization:
- **Must-have:** Features that all personas need
- **High-priority:** Features that 4+ personas need
- **Nice-to-have:** Features that only 1-2 personas need

### For Marketing:
- Use personas' quotes in marketing materials
- Craft messaging yang resonates dengan pain points mereka
- Create case studies berdasarkan their success scenarios

---

**These personas are living documents.** Update them as we learn more from actual users during beta testing.

---

## ➡️ Continue Reading

**[Next: Scope →](SCOPE.md)**
