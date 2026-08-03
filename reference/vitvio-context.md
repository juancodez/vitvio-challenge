# VitVio — Context for AI-Native Product Design Challenge

## Who I am
I'm Juani, a product designer (~8 months into product design after a path through gastronomy, graphic design, web design, and UX). I'm interviewing for a part-time contractor role at VitVio. This file is context for you (Claude Code) so you can help me scope, design, and build fast during a live 90-minute challenge without me having to re-explain everything from scratch.

## The company: VitVio
VitVio is a healthtech startup building **Vetro**, a 3D spatial context engine for operating rooms. It uses ambient sensing (cameras/sensors in the OR), markerless calibration, and point cloud/occlusion handling to understand what's happening in a surgery in real time. Key capabilities:
- Auto-generated operative notes (op-notes) — a legal medical record
- Auto-detection of surgical phases (e.g., incision, closing)
- A "Mission Control" dashboard for hospital/OR staff to monitor what's happening

VitVio is privacy-first, backed by LDV Capital, has been building Vetro for ~2 years, and recently opened public access (July 2026). They won 2nd place in the Nebius AI Discovery Awards (Digital Health category) and work with Royal Orthopaedic Hospital Birmingham.

**Founders / key people:**
- Thomas Knox — CEO (ex-AiFi)
- Aleks Pajewski — Co-Founder & CPO (ex-AiFi, Forbes 30 Under 30, LSE, based in Warsaw) — this is who I'm interviewing with
- Maks Kozarzewski — COO
- Peter Rennert, PhD — CTO
- Grzegorz Jacenków — Chief Scientist (ex-Amazon)

## The role
**Part-time Product Designer, contract through January**, hybrid in Warsaw preferred or fully remote (European time zones). ~20 hours/week, occasional 2–3 day hospital travel (Europe/UK) during which hours may increase. Laptop provided. Hours reassessed in December; possible (not guaranteed) team expansion.

Core requirement: **design with AI at the core of the process** — using tools like Claude, Cursor, v0, Bolt, Replit to build *working, testable interfaces*, not static mockups. The role explicitly calls out designing for "the hard parts of AI UX": uncertainty, trust, transparency, error/failure, confidence indicators, graceful failure, and human oversight in safety-critical situations. This is squarely about translating complex, uncertain sensor/AI data into interfaces that clinicians can trust and act on quickly, under pressure.

## Where things stand
I already had a 15-minute screening call with Aleks (went well, passed to next round). Talked through: why VitVio (my father is a surgeon, this is personal), my AI-native workflow (Perplexity for research, Granola for transcription, Claude for synthesis, Notion/Notebook for docs, Claude Code for prototyping — referencing Klaro, a tax platform for Spanish-speaking freelancers in Germany I built solo end-to-end), and an example of handling disagreement constructively (deferring to user research evidence over my own instinct on a feature).

## The upcoming challenge (Tuesday)
Aleks explicitly confirmed by email that this is a **live, 90-minute "vibecoding challenge"**, not a take-home and not a traditional whiteboard/sketch exercise (that was a separate, superseded generic email). Format:
1. **We scope a problem together live** (Aleks gives context, no clinical background needed going in)
2. **I build a real prototype live**, screen-shared, using an AI-assisted design/dev tool
3. **I walk through what I built** — what it is, why I made the choices I made, what I'd do next with more time

I plan to use **Claude Code** as my primary tool (fastest for me to narrate reasoning while building interactive flows), with Lovable and Figma Make open only as backups if something breaks.

## My framework for the session
**Phase 1 — Scoping (~10–15 min):** Ask one question at a time, don't rush, cover:
- WHO is affected by this problem
- WHAT they need to know / what's missing
- WHY it matters — what's the urgency or risk
- WHAT exists today as a workaround

**Phase 2 — Building (~50–60 min):** Build live in Claude Code. Keep moving, narrate each decision with a one-sentence "why" as I go, don't go silent while working.

**Phase 3 — Presenting (~5–10 min):** Three beats:
1. The problem as I understood it
2. What I built and why
3. What I'd do next with more time

## Practice scenarios already rehearsed (for pattern reference, not to reuse verbatim)
- **Delay notifications:** OR schedule delays don't reach downstream teams (next patient's team, cleaning crews, families) until a manual check. Solution direction: severity-based status badges (on time / minor delay / needs attention) rather than blanket notifications, to avoid alert fatigue — kept clearly separate from surgery-phase-status indicators.
- **Phase-detection uncertainty:** Vetro's auto-phase-detection sometimes loses confidence (camera blocked, poor lighting) and silently guesses, risking wrong info in the legal op-note. Solution direction: real-time uncertainty alert when confidence drops + a voice-based manual fallback for the nurse + AI reconciliation once tracking resumes. This scenario maps almost directly to the job description's emphasis on trust/uncertainty/graceful failure/human oversight.

## What I want from you (Claude Code) during the session
- Help me move fast once a problem is scoped — build a real, interactive, shippable-looking slice (not just static screens)
- Prioritize clarity and one strong idea over breadth — no half-finished parallel explorations
- Keep interfaces legible for a clinical, high-stakes context: calm, low-friction, clear about system confidence/uncertainty where relevant
- Help me surface a clean three-beat presentation of what got built at the end

---

## VitVio Design System (extracted from reference screenshots)

### Logo
- **Logomark:** Geometric shape — a 3D-perspective diamond/rhombus with an internal left-pointing arrow/play symbol. Reads as a spatial "frame" or viewport — referencing 3D depth and the OR camera context.
- **Wordmark:** "VitVio" in Neue Haas Grotesk, medium weight, sentence case (not all-caps). Tight tracking, no embellishment.
- **Dark version:** White logomark + wordmark on near-black `#000F0A` background — used on website, dashboard header, marketing.
- **App icon version:** Logomark in dark/black on a green-to-blue gradient (`#0CF19E` → `#4495FA`) inside a rounded square — used as mobile/product icon.

### Color Palette
| Name | HEX | RGB | Usage |
|------|-----|-----|-------|
| Green (primary accent) | `#0CF19E` | 12, 241, 158 | CTAs, active states, highlights, teal accent, icon active bg, mono text |
| Blue (gradient partner) | `#4495FA` | 68, 149, 250 | Gradient with green on app icon, timeline segments |
| Black (dark bg) | `#000F0A` | 0, 15, 10 | Primary dark background — near-black with a subtle green tint |
| Gray (light surface) | `#F7F7F7` | 247, 247, 247 | Main content area background in dashboard (light mode) |
| White | `#FFFFFF` | 255, 255, 255 | Body text on dark, card backgrounds |

**Status colors seen in dashboard:**
- On time: green chip
- Delayed: orange/amber chip
- Ahead of time: blue chip
- Out of work / inactive: gray chip
- Warning/alert: amber `⚠` banner (soft yellow background)

### Typography
- **Primary — Neue Haas Grotesk:** All UI text — headings, labels, body, navigation, patient data. Clean, geometric grotesque. Used in white on dark and dark on light surfaces.
- **Secondary — PP Supply Mono:** Monospace, displayed in `#0CF19E` green. Used for: live countdown timers, MRN codes, technical data values, timestamps. Signals "system output / live data" vs human-authored content.
- **Type scale pattern:** Large bold headings (procedure names, section titles) → medium labels (stage, category) → small regular body (times, details). Tight line-height throughout.

### Icon System
- **Container:** Rounded square tiles (~10px radius), dark background `#1a1a1a`–`#222`
- **Style:** Line icons, thin 1.5px stroke, white — search, filter sliders, bell, chat bubble, gear/settings, home, list, checklist, clock
- **Active state:** Full `#0CF19E` green tile background with dark icon — high contrast, no ambiguity about what's selected
- **Feel:** Minimal, functional, clinical — no decorative icons

### Dashboard UI Patterns

#### OR Mission Control (main overview)
- Multi-column kanban layout — one column per operating room (OR 1 → OR 5)
- Dark left sidebar: icon-only navigation with VitVio logomark at top, green active icon
- Light main content area (`#F7F7F7`) with white cards per procedure
- Each card: procedure name (bold), MRN (small gray), start/end times, duration, colored status chip
- **Yellow/amber card highlight** = attention required (e.g. patient ready, turnover needed)
- Turnover rows between procedures with duration label
- Top bar: date, time (CET), global status filter chips (On time / Delayed / Ahead of time / Out of work)
- Info `ⓘ` icon on cards for drill-down

#### Preparation Dashboard (single-OR detail)
- Breadcrumb navigation at top
- **Phase timeline bar** — full-width horizontal bar, color-coded segments:
  - Green = completed phase
  - Purple/blue = current phase
  - Light blue = upcoming named phase ("Event name in 20min", "Skin close")
  - White/empty = remaining unscheduled time
  - Current time marker (vertical line with timestamp)
- Estimated vs actual start/end times side-by-side
- **Alert banner:** amber background, `⚠ Missing item` label + "Resolved" green badge — inline, not modal
- Patient details grid: MRN in teal (clickable), Name, DoB, Ward, Duration — countdown in teal bold ("00:59 left")
- "Next surgery" preview row with orange dot status

#### Live OR View (event timeline + issue tracker)
- **Left panel (dark):** Vertical event timeline — chronological list of surgical workflow events (Team Brief → Patient in Theatre). Each event: timestamp + label + "Now" / "Earlier" toggle buttons (letting staff confirm or backdate)
- **Right panel (white):** Live data — countdown timer in PP Supply Mono teal, time estimates, quick-select time chips (05min … 45min) for "Time Left" and "Schedule Turnover" manual inputs
- **Issue Tracker column (far right):** Simple form — Issue Title, Description, Time Left Estimate, Submit CTA in green — lightweight structured escalation
- "Debug menu" button top-right (internal/dev tooling)

### Sitemap — Control Dashboard Structure
```
Control Dashboard
├── Patient Preparation
│   ├── Viewing Patient Data
│   └── Confirmation of preparation
├── Surgery Execution
│   ├── Start of operation
│   ├── Monitoring tools and stages
│   └── End of operation
├── Post-Operative
│   ├── Record recovery time
│   └── Performance Analysis
├── Analytics & Reporting
│   ├── View performance reports
│   └── Optimization of the schedule
└── User Management
    ├── Assigning roles and access
    └── Setting up notifications
```
Sitemap node style: pill/rounded rectangles on white. Active/primary nodes have a green dot prefix.

### Marketing / Website Patterns
- Dark backgrounds with OR photography and 3D spatial renders (purple-tinted for the Vetro 3D engine view)
- Headline style: large, white, sentence case, Neue Haas Grotesk — e.g. "Every focal point lands on one calm screen."
- Feature presentation: 2-column comparison (competitors vs Vetro) with bullet-point differentiators
- Role targeting: Surgeons / Nurses / OR Managers — photo grid with role labels
- Op-note UI: dark panel, teal "Sync'd with EHR" button, timestamped event log in clean mono

### Social / Brand Templates
- Two modes: **light** (white bg, green accent frame on photo) and **dark** (near-black bg, green corner/border accents)
- Wordmark always present, logomark used as small avatar
- No gradients in social — flat green `#0CF19E` used as accent color only

### Design Language Summary (use this when building the prototype)
- **Dark-first:** Default UI is dark (`#000F0A` base) with light content panels where data density is high
- **Green = live / active / confirmed.** Anything the system is doing right now or confirming gets `#0CF19E`.
- **Mono = data.** Whenever showing a live number (timer, code, count), use PP Supply Mono in green.
- **No modal interruptions** — alerts are inline banners, not blocking overlays. Clinicians can't stop what they're doing.
- **Status is never ambiguous** — every card, row, and phase has an explicit labeled state. Never rely on color alone.
- **Calm, not cold** — typography is clean but not sterile; the UI is confident, not clinical-minimalist for its own sake.
