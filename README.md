# JBD Dragonfly Kitchen — Production OS

Internal production tracker for the JBD Dragonfly Kitchen, NY 2026 Drop 1 / Series 1.

## What it does

- **Production runs** — log strain, batch ID, incoming flower weight, units produced. Auto-deducts packaging components (jars, lids, labels, cones, tubes, cases, inserts, barcodes) per recipe.
- **Samples / testing** — track flower or finished units sent for lab testing, press, retailer drops, internal QC, marketing, waste/loss.
- **Inventory** — full component table seeded from the DragonFly Kitchen Inventory Excel; editable qty, status, supplier in place. Live remaining + health bar per SKU.
- **Strains** — Drop 1 lineup pre-loaded (7 strains). Add custom strains for future drops.
- **Reports** — CSV export per dataset, JSON full-backup, print snapshot, by-strain totals.

## Data persistence

All data lives in browser `localStorage` for now (per-device). Use **Export JSON** in the header to back up; **Import** to restore or sync between devices.

For multi-user/team sync, plan to wire to the JBD Glass backend (Postgres on Railway) — current version is single-device.

## Recipe (auto-deduction)

Each finished **Jar (7g)** consumes:
- 1 × `7g Child-Resistant Jar`
- 1 × `7g Jar Lid`
- 1 × `7g Jar Label` (matching strain type — Indica/Sativa/Hybrid)
- per 25 units: 1 × outer case, 1 × insert card, 1 × barcode label

Each finished **Pre-Roll (1g)** consumes:
- 1 × `Child-Resistant Pre-Roll Tube`
- 1 × `Pre-Roll Tube Lid`
- 1 × `Pre-Roll Tube Label` (matching strain type)
- 1 × `Pre-Roll Cone — 1g, Custom Branded` (matching colorway)
- per 50 units: 1 × outer case, 1 × insert card, 1 × barcode label

## Deploy

Static GH Pages site. CNAME set for `dfly.cannacrypted.com`.
