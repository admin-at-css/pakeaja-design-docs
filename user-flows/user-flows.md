# User Flows

**Last Updated:** October 28, 2025
**Status:** Brainstorming Phase

---

## Overview

This document maps out key user journeys for both contractors (primary users) and project owners (client portal users). Each flow describes step-by-step interactions with the system.

---

## Contractor Flows

### Flow 1: Create New Project & Invite Client

**Actor:** Project Manager (Contractor)
**Goal:** Set up a new painting project and give client portal access

**Steps:**
1. PM logs into PakeAja dashboard
2. Clicks "Create New Project" button
3. Fills out project creation form:
   - Project name: "Grand Indonesia Mall Repainting"
   - Client company: "PT Grand Indonesia"
   - Contact person: "Budi Santoso"
   - Contact email: `budi@grandindonesia.com`
   - Location: "Jl. MH Thamrin, Jakarta"
   - Start date: March 1, 2025
   - Estimated end: May 15, 2025 (10 weeks)
   - Total budget: IDR 500,000,000
4. Clicks "Create Project"
5. System creates project, redirects to project dashboard
6. PM sees button "Invite Client to Portal"
7. Clicks "Invite Client"
8. Confirmation modal:
   - "Send portal invitation to budi@grandindonesia.com?"
   - Checkbox: "Client can comment on project"
   - Checkbox: "Client can approve change orders"
9. PM clicks "Send Invitation"
10. System:
    - Creates ProjectAccess record
    - Sends email to Budi with magic link
    - Shows success message: "Invitation sent to budi@grandindonesia.com"
11. PM proceeds to add materials and milestones

**Result:** Project created, client has portal access

---

### Flow 2: Add Materials to Project

**Actor:** Project Manager
**Goal:** Define materials needed and track their status

**Steps:**
1. PM navigates to project page
2. Clicks "Materials" tab
3. Sees empty material list, clicks "Add Material"
4. Modal opens with form:
   - Search/select from database OR add new
   - Name: "Nippon Weathershield White"
   - Category: Paint
   - Brand: Nippon
   - Quantity: 200 liters
   - Unit price: IDR 150,000/liter
   - Supplier: (dropdown) "PT Sumber Cat"
   - Expected delivery: March 5, 2025
5. Clicks "Save Material"
6. Material appears in list with status "Planned"
7. PM repeats for primer, putty, tools (5-10 materials total)
8. PM clicks "Order Materials" bulk action
9. System updates status to "Ordered", sets orderedDate to today
10. Email notification sent to supplier (optional feature)
11. Project owner sees material status update in portal: "5 materials ordered"

**Result:** Materials defined, status tracked, client can see progress

---

### Flow 3: Upload Progress Photos (Mobile-First)

**Actor:** Field Supervisor (on-site)
**Goal:** Document daily progress with photos

**Steps:**
1. Supervisor opens PakeAja on mobile phone (responsive web or PWA)
2. Navigates to project > "Add Progress Photo"
3. Camera opens (or file picker)
4. Takes photo of freshly painted lobby area
5. Form appears:
   - Photo preview (with edit/retake option)
   - Area: (dropdown) "Lobby"
   - Photo type: (dropdown) "Progress"
   - Caption: "Topcoat application - first coat"
   - Auto-captured: Geolocation, timestamp
6. Clicks "Upload Photo"
7. System:
   - Compresses image (client-side)
   - Uploads to cloud storage
   - Creates ProjectPhoto record
   - Updates lobby area progress: 50% → 60%
8. Success message: "Photo uploaded successfully"
9. Supervisor takes 5-10 more photos throughout the day
10. **Client Portal:** Project owner receives notification "3 new photos uploaded" and can view immediately

**Result:** Real-time progress documentation visible to client

---

### Flow 4: Mark Milestone as Complete

**Actor:** Project Manager
**Goal:** Update timeline when a phase is finished

**Steps:**
1. PM navigates to project > "Timeline" tab
2. Sees milestones:
   - ✅ Site Preparation (completed Mar 1)
   - 🔵 Primer Application (in progress)
   - ⚪ Topcoat Application (not started)
   - ⚪ Final QA (not started)
   - ⚪ Handover (not started)
3. "Primer Application" is done, clicks "Mark Complete"
4. Modal asks: "Actual completion date?" (defaults to today)
5. PM confirms: March 10, 2025
6. System:
   - Updates milestone status to "Completed"
   - Recalculates overall project progress: 40% → 55%
   - Checks if on schedule (planned: Mar 12, actual: Mar 10 = 2 days early!)
   - Sets next milestone "Topcoat Application" to "In Progress"
7. **Client Portal:** Project owner sees:
   - "✅ Primer Application completed (2 days ahead of schedule)"
   - Progress bar: 55%
   - Updated estimated completion: May 13 (2 days earlier than planned)

**Result:** Timeline updated, client sees progress

---

### Flow 5: Handle Material Delay (Status Update)

**Actor:** Project Manager
**Goal:** Communicate material delay to client transparently

**Scenario:** Supplier delays topcoat delivery by 5 days

**Steps:**
1. PM receives call from supplier: "Delay due to production issue"
2. PM logs into PakeAja
3. Navigates to project > "Materials" tab
4. Finds "Nippon Weathershield Topcoat" (status: In Transit)
5. Clicks "Update Status"
6. Changes:
   - Status: "In Transit" → "Delayed"
   - Expected delivery: March 15 → March 20
   - Reason: "Supplier production delay - material quality issue"
7. Clicks "Save & Notify Client"
8. System:
   - Updates material record
   - Recalculates project timeline (5-day delay in topcoat phase)
   - Updates estimated completion: May 13 → May 18
   - **Sends notification to project owner**
9. **Client Portal:** Project owner receives:
   - Email: "Material delay on Grand Indonesia Mall project"
   - Portal shows:
     * Red alert banner: "Material delay: +5 days"
     * Material status: "Delayed - Production issue at supplier"
     * New completion date: May 18
     * Explanation visible
10. Project owner can comment: "Please keep me updated on new delivery date"

**Result:** Transparent communication, client isn't surprised, trust maintained

---

### Flow 6: Generate & Send Invoice

**Actor:** Project Manager / Accountant
**Goal:** Bill client for milestone payment

**Steps:**
1. PM/Accountant navigates to project > "Invoices" tab
2. Clicks "Create Invoice"
3. Form:
   - Invoice type: "Milestone 1 - Primer Complete"
   - Amount: IDR 150,000,000 (30% of total)
   - Due date: March 25, 2025
   - Tax (PPN 11%): Auto-calculated = IDR 16,500,000
   - Total: IDR 166,500,000
   - Payment terms: "Bank transfer to BCA 123-456-789"
4. Clicks "Generate Invoice"
5. System:
   - Creates Invoice record
   - Generates PDF with company logo
   - Status: "Draft"
6. PM reviews PDF preview, clicks "Send to Client"
7. System:
   - Updates status: "Sent"
   - Emails invoice to project owner
   - Makes invoice visible in Client Portal
8. **Client Portal:** Project owner can:
   - View invoice
   - Download PDF
   - See payment instructions
   - Mark as "Paid" (updates status)

**Result:** Professional invoicing, transparent billing

---

### Flow 7: Complete Project & Issue Warranty

**Actor:** Project Manager
**Goal:** Close project and activate warranty

**Steps:**
1. All work is complete, final QA passed
2. PM navigates to project > "Completion" tab
3. Clicks "Mark Project as Complete"
4. Checklist appears:
   - ✅ All milestones completed
   - ✅ Final QA passed
   - ✅ All invoices sent
   - ⚠️ Client approval pending
   - ⚪ BAST certificate generated
5. PM clicks "Generate BAST"
6. System generates digital BAST certificate (PDF):
   - Project details
   - Completion date: May 16, 2025
   - Sign-off sections
7. PM clicks "Request Client Sign-Off"
8. **Client Portal:** Project owner receives notification:
   - "Project complete - Please review and sign off"
   - Can view BAST, add comments
   - Digital signature field (or checkbox: "I approve completion")
9. Project owner signs off
10. System:
    - Updates project status: "Completed" → "Closed"
    - Activates warranty (12 months starting May 16)
    - Sends warranty certificate to project owner
11. **Client Portal:** Project owner can now:
    - Download signed BAST
    - View warranty details
    - Submit warranty claims (if needed)

**Result:** Professional project closure, warranty tracking begins

---

## Project Owner (Client Portal) Flows

### Flow 8: First-Time Portal Login

**Actor:** Project Owner (Budi - Shopping Mall Manager)
**Goal:** Access project portal for the first time

**Steps:**
1. Budi receives email: "You're invited to track your Grand Indonesia Mall Repainting project"
2. Email contains:
   - Brief explanation of what the portal is
   - Magic link button: "View Your Project"
3. Budi clicks link (from phone or desktop)
4. Redirected to PakeAja portal login page
5. System detects magic link token:
   - Auto-creates User account (role: PROJECT_OWNER)
   - Auto-logs in Budi
   - Creates session
6. Welcome modal appears:
   - "Welcome to your project portal!"
   - Quick tour highlights (skip or take tour)
7. Budi clicks "Show me around"
8. Guided tour (tooltips):
   - "This is your project dashboard"
   - "Here you can see material status"
   - "Photos are updated daily by the contractor"
   - "Track budget and timeline here"
9. Tour ends, Budi sees full dashboard
10. Budi bookmarks page, sets notification preferences

**Result:** Project owner onboarded, understands portal value

---

### Flow 9: Check Project Status (Daily Routine)

**Actor:** Project Owner
**Goal:** Quick daily check on project health

**Steps:**
1. Budi opens PakeAja portal on phone (morning coffee routine)
2. Dashboard shows at-a-glance:
   - 🟢 Overall status: "On Track"
   - Progress: 58% complete
   - Timeline: "Week 4 of 10 weeks"
   - Next milestone: "Topcoat Application - starts today"
   - Latest update: "3 new photos uploaded 2 hours ago"
3. Budi taps "View Photos"
4. Photo gallery loads (newest first):
   - Sees freshly primed walls in Floor 2
   - Swipes through 3 photos
   - Before/after comparison slider
5. Satisfied, Budi taps "Materials" tab
6. Sees:
   - ✅ Primer: Fully used
   - 🚚 Topcoat: Delivered yesterday
   - ✅ Putty: Fully used
   - 🟢 All materials on schedule
7. Budi taps "Budget" tab:
   - Total: IDR 500M
   - Spent: IDR 280M (56%)
   - Remaining: IDR 220M
   - Status: "On track" (58% done, 56% spent = efficient)
8. Budi closes app, confident everything is fine
9. **Total time:** 2 minutes (vs 15 min phone call to contractor)

**Result:** Project owner informed, no contractor interruption needed

---

### Flow 10: Commenting on an Issue

**Actor:** Project Owner
**Goal:** Request clarification on a specific area

**Steps:**
1. Budi notices in a photo: Floor 3 walls look uneven
2. In photo gallery, taps on the photo
3. Photo expands, shows:
   - Location: Floor 3 - East Wing
   - Date: March 12, 2025
   - Comments: None yet
4. Budi taps "Add Comment"
5. Text box appears: "The finish looks uneven in this area. Can this be corrected?"
6. Budi submits comment
7. System:
   - Saves comment
   - Notifies project manager (email + in-app)
   - Shows comment on photo
8. Next day, PM responds:
   - "Good catch! This is the first coat of primer. Second coat will be applied today, which will smooth it out. Final topcoat will be perfectly even."
   - Uploads new photo showing second coat
9. Budi sees response, satisfied
10. Taps "Resolved" (optional)

**Result:** Two-way communication, issue clarified quickly

---

### Flow 11: Approving a Change Order

**Actor:** Project Owner
**Goal:** Approve additional scope (and cost)

**Scenario:** Client requests additional area to be painted

**Steps:**
1. Budi calls PM: "Can you also paint the back office area? We forgot to include it."
2. PM: "Sure, let me send you a change order through the portal."
3. PM creates change order in system:
   - Title: "Add Back Office Area (50 sqm)"
   - Description: "Paint back office walls - 1 coat primer, 2 coats topcoat"
   - Cost impact: +IDR 25,000,000
   - Time impact: +3 days
4. PM submits change order
5. **Client Portal:** Budi receives notification
6. Budi opens portal, sees:
   - 🔔 Alert: "Change Order #CO-001 pending your approval"
   - Details clearly shown:
     * Scope: Add 50 sqm back office
     * Cost: +IDR 25M
     * Timeline: +3 days (new completion: May 21)
     * Updated total budget: IDR 525M
7. Budi reviews, clicks "Approve"
8. Confirmation modal: "By approving, you agree to additional cost and timeline"
9. Budi confirms
10. System:
    - Updates project budget: 500M → 525M
    - Extends timeline: May 18 → May 21
    - Notifies PM: "Change order approved"
11. PM proceeds with additional work

**Result:** Formal approval process, documented, no email back-and-forth

---

### Flow 12: Downloading Project Report

**Actor:** Project Owner
**Goal:** Get PDF report for management presentation

**Steps:**
1. Budi's CEO asks: "How's the mall repainting going?"
2. Budi needs a professional report to show in board meeting
3. Opens portal, clicks "Export Report"
4. Modal appears:
   - Report type: "Progress Report" (default)
   - Date range: "Last 30 days"
   - Include:
     * ✅ Progress photos
     * ✅ Budget summary
     * ✅ Timeline
     * ✅ Material status
     * ⬜ Detailed costs (optional - Budi unchecks this for high-level report)
5. Clicks "Generate PDF"
6. System:
   - Compiles data
   - Generates branded PDF report (2-3 pages)
   - Downloads to Budi's device
7. Budi opens PDF:
   - Cover page: "Grand Indonesia Mall Repainting - Progress Report"
   - Page 1: Overall status, progress chart, timeline
   - Page 2: Photo highlights (before/during/after)
   - Page 3: Budget summary, next milestones
8. Budi emails PDF to CEO
9. CEO responds: "Looks great, thanks for keeping me updated!"

**Result:** Professional reporting capability, project owner looks good to their boss

---

### Flow 13: Submitting Warranty Claim

**Actor:** Project Owner
**Goal:** Report paint peeling issue 8 months after completion

**Scenario:** Paint starts peeling in one area due to water leak (covered under warranty)

**Steps:**
1. Budi notices paint peeling in Floor 2 bathroom area
2. Remembers: "We have a 12-month warranty!"
3. Opens PakeAja portal (project now shows "Completed" status)
4. Clicks "Warranty" tab
5. Sees:
   - Warranty period: May 16, 2025 - May 16, 2026
   - Coverage: "Peeling, cracking, fading due to material defect or application error"
   - Status: 8 months remaining
6. Clicks "Submit Warranty Claim"
7. Form appears:
   - Affected area: "Floor 2 - Bathroom hallway"
   - Issue type: "Peeling"
   - Description: "Paint peeling near ceiling, approximately 2 sqm affected"
   - Upload photos: (takes 2 photos with phone)
8. Submits claim
9. System:
   - Creates WarrantyClaim record
   - Notifies contractor
   - Status: "Submitted"
10. Next day, PM reviews claim:
    - Sees photos, recognizes water leak caused it
    - Updates status: "Approved - Will repair next week"
    - Schedules repair: January 15
11. **Client Portal:** Budi sees update:
    - Status: "Approved"
    - Scheduled repair: Jan 15
    - Estimated completion: Same day
12. Jan 15: Contractor repairs area, uploads "after" photos
13. PM marks claim: "Resolved"
14. Budi confirms: "Looks good, thank you!"

**Result:** Professional warranty management, builds long-term trust

---

## Edge Cases & Error Flows

### Flow 14: Client Never Clicks Invitation Link

**Problem:** Project owner doesn't respond to portal invitation

**Steps:**
1. PM sends invitation to client
2. 3 days pass, no login activity
3. System shows PM: "Invitation sent, not yet accepted"
4. PM clicks "Resend Invitation"
5. System sends reminder email with same magic link
6. If still no response after 7 days:
   - PM can call client: "Did you receive the portal invitation?"
   - Option to send SMS with link
   - Option to set up account in-person

**Result:** Contractor can follow up, multiple contact methods

---

### Flow 15: Photo Upload Fails (Poor Internet)

**Problem:** Field supervisor uploads photo from site, but internet is slow/unstable

**Steps:**
1. Supervisor takes photo, clicks "Upload"
2. Upload starts but fails (timeout/disconnection)
3. System shows: "Upload failed. Retrying..."
4. Auto-retry mechanism (3 attempts)
5. If still fails:
   - "Save to Queue" - photo saved locally (browser storage or PWA)
   - Uploads automatically when connection restored
6. Success notification when upload completes

**Result:** Reliable uploads even with poor connectivity

---

### Flow 16: Budget Overrun Alert

**Problem:** Project is going over budget

**Steps:**
1. System monitors spending vs budget
2. When spent amount reaches 80% of budget:
   - Alert to PM: "⚠️ Budget at 80% - Project only 65% complete"
3. PM investigates (more material waste? Scope creep?)
4. PM can:
   - Option A: Request change order from client (increase budget)
   - Option B: Optimize remaining work to stay within budget
5. If Option A:
   - PM creates change order explaining overrun
   - Client sees in portal, can approve/reject
6. **Client Portal:** Project owner sees:
   - Budget status: "⚠️ Trending over budget"
   - Clear explanation of why
   - Option to approve additional funding

**Result:** Proactive budget management, no surprises

---

## Flow Summary

| Flow # | Actor | Purpose | Complexity | Priority |
|--------|-------|---------|------------|----------|
| 1 | Contractor | Create project & invite client | Medium | MVP ✅ |
| 2 | Contractor | Add materials | Medium | MVP ✅ |
| 3 | Contractor | Upload progress photos | Low | MVP ✅ |
| 4 | Contractor | Mark milestone complete | Low | MVP ✅ |
| 5 | Contractor | Handle material delay | Medium | MVP ✅ |
| 6 | Contractor | Generate invoice | Medium | MVP ✅ |
| 7 | Contractor | Complete project & warranty | High | Phase 2 |
| 8 | Project Owner | First-time login | Low | MVP ✅ |
| 9 | Project Owner | Check project status | Low | MVP ✅ |
| 10 | Project Owner | Comment on issue | Low | Phase 2 |
| 11 | Project Owner | Approve change order | Medium | Phase 2 |
| 12 | Project Owner | Download report | Medium | Phase 2 |
| 13 | Project Owner | Submit warranty claim | Medium | Phase 3 |
| 14 | Edge Case | Invitation not accepted | Low | MVP ✅ |
| 15 | Edge Case | Upload failure | Medium | MVP ✅ |
| 16 | Edge Case | Budget overrun | Medium | Phase 2 |

---

## Next Steps

1. [ ] Review flows with your input - Any missing scenarios?
2. [ ] Create wireframes/mockups for each screen in these flows
3. [ ] Write detailed API endpoints to support these flows
4. [ ] Implement MVP flows first (marked ✅ above)
5. [ ] User testing with real contractors and project owners

---

## Notes

- **Mobile-first:** Flows 3, 9 optimized for mobile (field workers, project owners on-the-go)
- **Notifications:** Key touchpoints where email/SMS/push notifications should be sent
- **Offline support:** Flow 15 shows importance of queue mechanism for unreliable connectivity
- **Two-way communication:** Flows 5, 10, 11 demonstrate transparency building trust

---
