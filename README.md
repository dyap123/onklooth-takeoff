# OnKlooth Takeoff

A concrete superintendent's field toolkit — start a project, run the calculators (they save + sync),
and roll everything up into an exportable takeoff. Built from the Drive Excel calculator library.

**Live (once deployed):** `https://dyap123.github.io/onklooth-takeoff/`

## What it does

- **Projects** — create a project; every calc run and takeoff item saves to it and syncs across devices
  (shared OpenYap Firebase RTDB, namespace `onklooth-takeoff`) with localStorage as the instant-save tier.
  Works fully offline; syncs when back online.
- **Calculators** (formulas verified cell-for-cell against the source spreadsheets):
  - **Reshore / Backshore** — multi-level construction-load capacity, ACI 209 strength gain, per-level
    GOOD/BAD stack verdict + minimum reshore levels needed.
  - **Formwork Pressure** — ACI 347 lateral form pressure (column & wall pour-rate bands), full-liquid head,
    load per tie.
  - **Concrete Pump** — Putzmeister bar-pressure method → required pressure, achievable output, line washout.
  - **Rebar + Crane** — ACI 318-14 Class B lap / development lengths (Grade 60) and crane outrigger reactions
    + pad bearing check.
- **Takeoff** — calc runs push quantity line items (concrete, formwork, reshore, rebar, pump); edit, add manual
  rows, apply unit costs, and export to **PDF** or **XLSX**.
- **Alfred** — optional AI advisor (MiniMax) that explains results and cites ACI/ASCE. Degrades gracefully
  with no key or no connection.

## Run it

It's a single self-contained `index.html` — just open it, or serve the folder:

```bash
open index.html            # or:
python3 -m http.server 8080 && open http://localhost:8080
```

No build step. React is compiled in-browser via Babel-standalone; export/sync libs load from CDN.

## Deploy (GitHub Pages)

```bash
git init && git add -A && git commit -m "OnKlooth Takeoff prototype"
gh repo create dyap123/onklooth-takeoff --public --source=. --push
# then enable Pages → deploy from main branch root
```

`.nojekyll` is already present. Add a tile to `openyap-launcher/src/data/apps.js`.

## Status: prototype

Working end-to-end flow. Not yet: production Firebase security rules, member (stud/wale) design in Formwork,
`.xls`-only calculators (BEAMANAL, PT losses), and a polished visual pass (see `DESIGN-BRIEF.md`).
