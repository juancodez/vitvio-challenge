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
