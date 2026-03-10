# 10 — PowerPoint Build Guide

> Rubric: 20 marks total — User & Task Analysis (5), HCI Principles (5), Prototyping & Layout (5), Individual Presentation (5)

---

## Slide Order & Content

---

### Slide 1 — Title Slide

**Content:**
- Title: **USIU Lost & Found — HCI Progress Presentation**
- Subtitle: SFT4010VA
- Team member names
- Date

**Design:** Clean, minimal. One screenshot of the homepage in the background at low opacity.

---

### Slide 2 — Problem Statement

**Heading:** The Problem

**Bullets (max 4):**
- Students lose items on campus with no central reporting system
- Security staff have no digital tool to manage claims
- No way to match a found item to the person who lost it
- Result: items go unclaimed, finders have no safe handover process

**Screenshot:** Homepage item feed (full width, right side of slide)

---

### Slide 3 — Solution Overview

**Heading:** Our Solution

**Bullets:**
- A searchable digital board for lost and found items
- Separate flows for reporters, finders, and admin
- Admin oversight to prevent false claims
- Real-time status tracking per item

**Screenshot:** Item card showing Lost/Found badge, status badge, Claim/Found button

---

## SECTION 1 — User & Task Analysis (5 marks)

---

### Slide 4 — Personas

**Heading:** Who Are the Users?

**Layout:** Three columns, one per persona

| Amara (Reporter) | Daniel (Finder) | Grace (Admin) |
|---|---|---|
| 20, CS student | 22, Business student | 45, Security staff |
| High tech comfort | Medium tech comfort | Low-medium tech comfort |
| Goal: report & recover | Goal: hand in safely | Goal: verify & resolve |
| Constraint: stressed, narrow focus | Constraint: needs clear next steps | Constraint: reduced STM, possible colour blindness |

**Presenter note:** Link each constraint to Chapter 1 — stress narrows thinking (Norman emotion theory), STM = 7±2 chunks, 8% males colour-blind.

---

### Slide 5 — HTA: Report a Lost Item

**Heading:** Hierarchical Task Analysis — Report Lost Item

**Diagram (draw as a numbered tree):**

```
0. Report a lost item
  1. Open the app
  2. Sign in
     2.1 Enter email + password
     2.2 Submit login
  3. Open Report Item form
  4. Fill in details
     4.1 Title *        4.5 Date *
     4.2 Category *     4.6 Description
     4.3 Type (Lost)    4.7 Upload image
     4.4 Location *     4.8 Contact info
  5. Submit → receive toast confirmation
  6. Monitor status on feed
```

**Plan note at bottom:** Steps 4.1–4.5 required; 4.6–4.8 optional but improve match rate

**Presenter note:** "Breaking the task into 6 top-level steps and 8 sub-steps revealed that step 4 was too complex — this led us to group fields visually into two sections."

---

### Slide 6 — HTA: Claim / Found Flows

**Heading:** HTA — Claim a Found Item / Report Finding a Lost Item

**Two side-by-side mini trees:**

**Claim (Found item):**
```
0. Claim a found item
  1. Browse / search feed
  2. Open item details
  3. Click "Claim"
  4. Fill claim form
     (name, contact, proof of ownership)
  5. Submit → await admin
```

**Found (Lost item):**
```
0. Report finding a lost item
  1. Browse feed
  2. Click "Found" on matching item
  3. Fill found form
     (name, contact, where found)
  4. Submit → admin contacts reporter
```

---

### Slide 7 — Scenarios

**Heading:** Use Scenarios

**Scenario A (left):**
> Amara leaves the library and realises her student ID is gone. She opens the app, taps Report Item, fills the form in under 2 minutes, and sees a green toast: "Report submitted." She heads to class knowing the system will notify her if someone finds it.

**Scenario B (right):**
> Daniel finds a wallet near the cafeteria. He opens the app, selects Found, uploads a photo, and submits. The owner later finds the listing, clicks "Claim", and describes the wallet contents as proof of ownership.

**Design implication (bottom):** Both flows must complete in under 2 minutes — STM decay begins at ~200ms, negative affect narrows focus.

---

## SECTION 2 — HCI Principles Application (5 marks)

---

### Slide 8 — Norman's Model

**Heading:** Norman's Action Cycle (Chapter 3)

**Diagram:** Two-column layout
- Left: Gulf of Execution → Gulf of Evaluation cycle diagram (draw simply: Goal → Plan → Execute → Perceive → Evaluate)
- Right: App example for each stage

| Stage | In our app |
|---|---|
| Form goal | User wants to report a lost item |
| Plan | Sees "Report Item" button — maps clearly to goal |
| Execute | Fills form, clicks Submit |
| Perceive | Green toast appears immediately |
| Evaluate | Toast confirms submission — Gulf of Evaluation closed |

---

### Slide 9 — Norman's 7 Principles in the App

**Heading:** Norman's Principles — Applied

**Layout:** Two bullets per principle, one screenshot callout

| Principle | Applied |
|---|---|
| 1. Knowledge in the world | Category dropdown lists all options — no recall required |
| 2. Simplify tasks | Report is one modal, not a multi-page wizard |
| 3. Make things visible | Status badge always visible on card — no need to open details |
| 4. Get mappings right | "Lost" / "Found" toggle maps naturally to two mutually exclusive choices |
| 5. Exploit constraints | Date picker blocks future dates; claim requires login |
| 6. Design for error | Confirmation dialog before destructive admin actions |
| 7. Standardise | Submit bottom-right, Cancel top-right X — platform convention |

**Screenshot callout:** Arrow pointing to status badge on ItemCard

---

### Slide 10 — Shneiderman's 8 Golden Rules

**Heading:** Shneiderman's Golden Rules — Applied (Chapter 7)

**Pick the 4 most visible — table format:**

| Rule | Applied in App |
|---|---|
| 1. Consistency | All modals: same header / form / button layout |
| 3. Informative feedback | Toast after every form submission and admin action |
| 4. Closure | Modal closes + feed updates + toast = complete task signal |
| 8. Reduce STM load | Active filter chips shown above results; max 7 fields per group |

**Screenshot:** Toast notification after submitting a report

---

### Slide 11 — Human Constraints (Chapter 1)

**Heading:** Designing for Human Limits

**Table:**

| Constraint | Design Decision |
|---|---|
| STM = 7±2 chunks | Form fields split into two groups (What / Where) |
| Colour blindness (8% males) | Status badges use icon + text, never colour alone |
| Negative affect narrows thinking | Calm, reassuring copy — no alarming error messages |
| Reaction time ~200ms | All feedback within one animation frame |
| Fitts' Law | Primary CTA buttons large and near the user's last action |

---

## SECTION 3 — Prototyping & Layout (5 marks)

---

### Slide 12 — Navigation Structure

**Heading:** Navigation Map

**Diagram (draw as flowchart):**

```
Not logged in → Homepage (browse only) → Sign In Modal
                                               ↓
Logged in (Student) → Homepage → Report Item Modal
                              → Item Details Modal → Claim/Found Modal
                              → Notification Bell

Logged in (Admin) → Homepage → Admin Dashboard
                                → View Claim → Approve Claim → matched
                                → Match Found → matched → Mark Resolved
```

**Presenter note:** "Flat hierarchy — max 2 levels deep. Every action is reachable in 2 clicks."

---

### Slide 13 — Screen: Homepage Feed

**Heading:** Screen Design — Homepage

**Full screenshot of the homepage with annotations:**
- Arrow 1 → Search bar: "Query interface — structured search, not free text (Ch3)"
- Arrow 2 → Filter chips: "Active filters visible — reduces STM load (Ch1, Rule 8)"
- Arrow 3 → Item card image: "Image at top — most identifying feature first (grouping principle Ch5)"
- Arrow 4 → Status badge: "Icon + colour — never colour alone (Ch1 colour blindness)"
- Arrow 5 → "Report Item" button: "Always visible — bridges Gulf of Execution (Norman Principle 3)"

---

### Slide 14 — Screen: Report Item Modal

**Heading:** Screen Design — Report Item Form

**Screenshot of ReportItemModal with annotations:**
- Arrow 1 → "What is the item?" section header: "Field grouping — reduces perceived complexity (Ch5)"
- Arrow 2 → "Where and when?" section: "Logical separation — user processes one chunk at a time (STM, Ch1)"
- Arrow 3 → Date picker: "Constraint: future dates disabled — prevents slip errors (Norman Principle 5)"
- Arrow 4 → Submit button (bottom right): "Platform convention — WIMP standard (Ch3)"

---

### Slide 15 — Screen: Claim / Found Modal

**Heading:** Screen Design — Claim & Found Modal

**Two screenshots side by side (or one with callouts):**

**Found item → Claim modal:**
- Title: "Claim: [item name]"
- Label: "Proof of ownership" — only owner would know

**Lost item → Found modal:**
- Title: "Found: [item name]"
- Label: "Where did you find it?" — different question for a different role

**Annotation:** "Same component, context-aware text — consistency (Rule 1) without misleading the user"

---

### Slide 16 — Screen: Admin Dashboard

**Heading:** Screen Design — Admin Dashboard

**Screenshot of AdminDashboard with annotations:**
- Arrow 1 → Default filter "Pending": "Shows only actionable items — reduces STM load, supports admin's goal (Ch1)"
- Arrow 2 → Claim count badge: "At-a-glance status — visible without opening the item (Norman Principle 3)"
- Arrow 3 → "Approve Claim" → matched flow: "Two-step resolution: matched → resolved prevents premature closure (Rule 4)"
- Arrow 4 → Confirm AlertDialog: "Confirmation before irreversible action — error prevention (Norman Principle 6, Rule 5)"

---

### Slide 17 — Evaluation & Next Steps

**Heading:** Evaluation

**Left column — Applied:**
- Informal heuristic walkthrough during development
- Renamed "Verify" → "Approve Report" after identifying Gulf of Execution
- Added confirmation dialog after identifying risk of accidental resolve

**Right column — Planned:**
- Cognitive walkthrough (Chapter 9) — expert steps through each HTA task
- Think-aloud protocol with 3–5 USIU students
- Nielsen's 10 Heuristics checklist against each screen

---

### Slide 18 — Summary

**Heading:** Summary

**Three columns matching rubric:**

| User & Task Analysis | HCI Principles | Prototyping & Layout |
|---|---|---|
| 3 personas mapped to Ch1 constraints | Norman's 7 principles applied per screen | Flat 2-level navigation |
| HTA for 3 core tasks | Shneiderman's Rules 1, 3, 4, 8 demonstrated | Grouped form layout (What / Where) |
| 3 scenarios with design implications | Human limits (STM, colour, affect) addressed | WIMP elements documented |

**Final line:** "Every design decision traces back to course theory — this is not just a working app, it is an HCI-informed one."

---

## Slide Design Rules (apply to all slides)

- Max 5 bullet points per slide
- Every slide with text should have a screenshot or diagram
- Font: sans-serif, body min 20pt, heading min 28pt
- Colour: white background, dark text — never reverse-text on dark background for body copy
- Annotate screenshots with numbered arrows, not inline text
- Slide numbers bottom-right on every slide

---

## Checklist Before Presenting

- [ ] All screenshots taken from the live deployed app (Vercel URL)
- [ ] HTA diagram drawn cleanly (PowerPoint SmartArt or manual shapes)
- [ ] Every principle named with its source: "Norman Principle 3", "Shneiderman Rule 8", "Chapter 1"
- [ ] Modal screenshots show both lost and found variants
- [ ] Admin dashboard screenshot shows the full claim workflow
- [ ] Practised once end-to-end — cut to 10–12 minutes
- [ ] Prepared answers for Q&A (see [4-presentation-guide.md](4-presentation-guide.md) Section 4.4)
