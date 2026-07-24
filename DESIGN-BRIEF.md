# Claude Design prompt — OnKlooth Takeoff

Paste the block below into Claude (design/artifact mode, or with the Figma tools enabled to generate an actual
Figma file). It's written to produce a cohesive visual system + high-fidelity screens for the prototype in this
folder. Swap in a real screenshot of `index.html` if you want it to redesign against the current build.

---

**PROMPT ↓**

You are designing **OnKlooth Takeoff**, a mobile-first field web app for concrete superintendents. It is part of
the **OpenYap** family of construction field tools (single-page apps, dark theme, deployed to GitHub Pages). I have
a working functional prototype — I need you to give it a distinctive, production-grade visual design. Deliver a
**design system** (color, type, spacing, components) plus **high-fidelity mockups** of the key screens, in both a
light and dark variant, optimized for a phone held on a jobsite deck.

**Who uses it & where:** A concrete superintendent or field engineer, on a phone or tablet, outdoors, often with
gloves and in bright sun. Speed and legibility beat decoration. They start a *project*, run engineering
calculators throughout the pour cycle, and assemble a quantity *takeoff* to export.

**What it does (the screens to design):**
1. **Start / Welcome** — empty state that invites "Start a project"; lists existing projects. Establish the brand.
2. **New Project modal** — name, job number, location.
3. **Dashboard** — project header (name/job/location), stat tiles (saved runs, takeoff items), a grid of 4
   calculator entry tiles, a "recent runs" list, and a prominent "Build the takeoff →" action.
4. **Calculator screen (x4)** — a two-column layout (inputs left, live results right; stacks on mobile). Design:
   - Input fields with a **unit adornment** on the right (in, ft, psf, pcf, °F, psi, kW, lb).
   - **Segmented toggles** (element type, bar size, f'c, bar position).
   - A **result card** with a hero big-number (e.g. "951 psf"), a labeled read-out list below, and action
     buttons "Save run" / "Add to takeoff".
   - For **Reshore**: a per-level table with green **GOOD** / red **BAD** verdict pills and a summary callout
     ("stack OK — min 3 levels").
5. **Takeoff** — an editable spreadsheet-style table grouped by category (Concrete, Formwork, Reshore, Rebar,
   Pump, Other) with inline-edit cells (description, qty, unit, unit cost, total), a totals bar, and
   **Export PDF / XLSX** buttons. Also design its **printed PDF output** (a stamped, branded takeoff sheet).
6. **Sync + Alfred** — a top-bar project selector and a sync status chip (Synced / Local / Offline), plus a
   floating **Alfred** AI-assistant button and chat panel.

**Brand & tone:** Rugged-but-precise engineering software. Confident, not playful. The name "OnKlooth Takeoff"
should feel like a tool, not a consumer app. Suggest a wordmark/monogram (current placeholder is "OK" in a
blue→green gradient tile).

**Design language to start from (evolve it, don't just copy):**
- Dark obsidian base (`#0a1017`), panels around `#111b28`, hairline borders `#1f2f42`.
- Primary blue `#2f80ed`, with a **Webcor green** accent `#3fa535` for confirm/positive/quantities.
- Verdict colors: green good, red `#f87171` bad, amber `#fbbf24` warning.
- Type: **Space Grotesk** for display/numbers, **Inter** for body, **JetBrains Mono** for values/units/tables.
- Numbers are the product — treat monospace numeric read-outs and the hero big-number as first-class type.

**Hard constraints:** Must be buildable as a single self-contained `index.html` (no heavy assets — inline SVG,
system-loadable fonts). Must remain **legible in sunlight** (high contrast, large tap targets ≥44px,
glove-friendly). Must have a **print-clean** variant for the exported takeoff. Theme-aware (light + dark).

**Deliverables:**
1. A tokens sheet (color, type scale, spacing, radius, elevation) for both themes.
2. Component specs: input+unit, segmented control, result card, verdict pill, stat tile, takeoff row, sync chip,
   Alfred panel, primary/secondary/confirm buttons.
3. High-fidelity mockups of: Welcome, Dashboard, one Calculator screen (Reshore, with the verdict table),
   Takeoff, and the printed PDF takeoff sheet.
4. A short rationale for the key decisions (why these fonts, why the accent system, sunlight legibility).

Keep it a cohesive system — every screen should read as one product. Prioritize clarity and speed of data entry
over ornamentation.

---

**Tip:** if you have the Figma tools available, ask it to build the token library and components as a real Figma
file first, then assemble the screens from those components (that's the `figma-generate-library` +
`figma-generate-design` flow).
