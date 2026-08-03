# DESIGN.md — VitVio / Vetro
# Source: vitvio.com + reference screenshots (Aug 2026)
# Format: DESIGN.md (compatible with DesignMD / Google Stitch)

## Brand

**Company:** VitVio  
**Product:** Vetro — 3D spatial context engine for operating rooms  
**Voice:** Precise, clinical, trustworthy — never cold. Operational efficiency framed as patient safety. Technical confidence without jargon.  
**Audience:** Surgeons, nurses, OR managers, hospital administrators  
**Context:** Safety-critical, high-stakes, real-time. Interfaces must be calm and unambiguous — no cognitive load, no surprises.

---

## Colors

```
color.brand.green       #0CF19E   rgb(12, 241, 158)    Primary accent — active, live, confirmed, CTA
color.brand.blue        #4495FA   rgb(68, 149, 250)    Gradient partner, timeline segments, info states
color.brand.black       #000F0A   rgb(0, 15, 10)       Primary dark background (near-black, green-tinted)
color.brand.gray        #F7F7F7   rgb(247, 247, 247)   Light surface — main content area in dashboard
color.brand.white       #FFFFFF   rgb(255, 255, 255)   Text on dark, card backgrounds

color.status.on-time    #0CF19E   Green chip — surgery running on schedule
color.status.delayed    #F59E0B   Amber chip — behind schedule, needs attention
color.status.ahead      #4495FA   Blue chip — ahead of schedule
color.status.inactive   #6B7280   Gray chip — out of work / no activity
color.status.warning    #FEF3C7   Amber banner background for inline alerts (⚠)

color.sidebar.bg        #0D0F0E   Dark sidebar navigation background
color.card.bg           #FFFFFF   Card / panel background on light surface
color.card.highlight    #FFFBEB   Amber-tinted card — requires attention
```

**Gradient (app icon / hero accents):**
```
background: linear-gradient(135deg, #4495FA 0%, #0CF19E 100%);
```

**Rule:** Green = live / active / confirmed. Never use green decoratively. Amber = attention needed. Blue = informational.

---

## Typography

```
font.primary     "Neue Haas Grotesk", "Haas Grotesk", system-ui, sans-serif
font.mono        "PP Supply Mono", "Supply Mono", ui-monospace, monospace

font.weight.regular   400
font.weight.medium    500
font.weight.bold      700
```

**Type scale:**
```
text.display      32–48px / bold    700   Neue Haas   Page titles, hero headlines
text.heading-1    24px     / bold    700   Neue Haas   Procedure names, section headers
text.heading-2    18–20px  / bold    700   Neue Haas   Card titles, OR names
text.label        13–14px  / medium  500   Neue Haas   Status labels, field names, nav items
text.body         14px     / regular 400   Neue Haas   Body copy, descriptions, patient details
text.caption      12px     / regular 400   Neue Haas   Timestamps, secondary info, legal
text.mono-lg      24–32px  / regular 400   PP Supply   Live countdown timers (shown in green)
text.mono-sm      13px     / regular 400   PP Supply   MRN codes, data values, technical IDs
```

**Rules:**
- PP Supply Mono in `#0CF19E` = "system output / live data" — use only for timers, codes, live counts
- Never use all-caps for headings (website uses sentence case throughout)
- Tight letter-spacing, compact line-height (1.2–1.4) — dense clinical information needs to scan fast

---

## Spacing

```
space.1    4px
space.2    8px
space.3    12px
space.4    16px
space.5    20px
space.6    24px
space.8    32px
space.10   40px
space.12   48px
space.16   64px
```

**Layout:**
- Sidebar width: 56–64px (icon-only navigation)
- Card padding: 16px
- Section padding: 24–32px
- Grid gap: 16px between OR columns

---

## Border Radius

```
radius.sm     6px    Chips, badges, status pills
radius.md     8px    Cards, panels, input fields
radius.lg     12px   Dashboard cards, modal panels
radius.xl     16px   Large containers, image blocks
radius.full   9999px Pill buttons, tag chips
```

---

## Shadows

```
shadow.card     0 1px 3px rgba(0,0,0,0.08), 0 1px 2px rgba(0,0,0,0.06)
shadow.panel    0 4px 16px rgba(0,0,0,0.12)
shadow.modal    0 20px 60px rgba(0,0,0,0.3)
```

---

## Icons

- **Style:** Line icons, ~1.5px stroke, rounded caps
- **Container:** Rounded square tile, `radius.lg`, dark background `#1C1F1E`
- **Size:** 20×20px icon inside 40×40px tile
- **Active state:** Full `#0CF19E` tile background, dark icon — no ambiguity
- **Set includes:** search, filters, bell, chat, gear, home, list/dashboard, checklist, add (+), clock
- **Rule:** Never use decorative icons. Every icon maps to a direct action or navigation destination.

---

## Components

### Status Badge / Chip
```
background: color.status.*
color: white (or dark on light chips)
padding: 2px 8px
border-radius: radius.full
font: text.label, font.weight.medium
```

### Alert Banner (inline, never modal)
```
background: color.status.warning (#FEF3C7)
border-left: 3px solid #F59E0B
padding: 12px 16px
border-radius: radius.md
icon: ⚠ amber
— includes action button ("Resolved") inline, right-aligned
```

### Phase Timeline Bar
```
Full-width horizontal bar, height: 10–12px
Segments color-coded:
  completed  → #0CF19E
  current    → #6366F1 (purple-blue)
  upcoming   → #93C5FD (light blue, with text label above)
  remaining  → #E5E7EB (light gray)
Current time marker: vertical line, 2px, dark, with timestamp label below
```

### Live Timer
```
font: text.mono-lg
color: #0CF19E
display: HH:MM:SS
label above in text.caption gray
```

### Event Timeline (sidebar)
```
Vertical list, dark background
Each row: timestamp (text.caption, gray) + event label (text.body, white)
Action buttons: "Now" (outlined, white) / "Earlier" (ghost)
Connector line between events: 1px dashed, #2D3130
```

### Navigation (sidebar)
```
width: 56px
background: #0D0F0E
icons: centered, 20px, white at 60% opacity
active icon: full #0CF19E tile
logo: top, 32px, white
bottom: user avatar or settings icon
```

### CTA Button (primary)
```
background: #0CF19E
color: #000F0A
padding: 10px 20px
border-radius: radius.md
font: text.label, font.weight.medium
hover: brightness(0.9)
```

### Time Chip (quick-select)
```
background: #F3F4F6
color: #111827
padding: 6px 12px
border-radius: radius.sm
font: text.caption
selected: background #0CF19E, color #000F0A
```

---

## Motion

```
duration.fast    150ms   Chip toggles, button states
duration.base    250ms   Panel transitions, card reveals
duration.slow    400ms   Page transitions, drawer open/close
easing.default   cubic-bezier(0.4, 0, 0.2, 1)   Standard ease-in-out
easing.enter     cubic-bezier(0, 0, 0.2, 1)      Decelerate (things coming in)
easing.exit      cubic-bezier(0.4, 0, 1, 1)      Accelerate (things going out)
```

**Rule:** No animation for its own sake. Motion only signals state change (status update, alert appearing, phase advancing). Zero bounce, zero spin loaders in a clinical context.

---

## Layout Patterns

### OR Mission Control (kanban)
- Dark left sidebar (56px) + light main area
- Top bar: breadcrumb left, date/time + status filters right
- Column per OR room, equal width, scrollable
- Cards stack vertically within each column with turnover rows between

### Single OR Detail
- Full-width phase timeline bar at top (below header)
- 2-column below: patient/procedure info left, next surgery preview right
- Inline alert banners above patient details when present

### Live OR View
- Dark left panel (~280px): vertical event timeline
- White right area: split into center (live data + time inputs) + far-right (issue tracker form)

---

## Anti-slop Rules (what NOT to do)

- No purple gradients, no neon blue, no generic sans-serif (Inter/Roboto) — use Neue Haas Grotesk
- No modal dialogs blocking the UI — alerts are always inline banners
- No loading spinners — use skeleton states or live data immediately
- No color-only status signals — always pair color with a text label
- No decorative illustrations or blob shapes — photography (OR context) or flat functional UI only
- Green is earned — only use `#0CF19E` for confirmed/active/live states, never decoration
- No card hover shadows that make the UI feel like a SaaS landing page — this is a clinical tool
