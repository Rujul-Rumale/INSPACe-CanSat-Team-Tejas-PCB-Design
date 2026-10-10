# Tejas CanSat — Onboard Computer (OBC) PCB

**Author / Designer: Rujul Rumale <rujul.rumale@gmail.com>**
**Project: INSPACe CanSat — "Tejas"**
**Role claimed: PCB design (schematic + layout + Gerber release) and PFR PPT data-processing section**

This repository is the author's clean, attributable record of the **PCB contribution** to the
INSPACe CanSat team project. It was created on 2026-10-10 from the working project folder
to establish a verifiable, timestamped record of authorship.

> If you reuse this design you must retain this authorship notice and comply with the
> license in `LICENSE` (CERN-OHL-S-2.0).

![3D isometric render](docs/renders/3d-iso.png)

*Tejas OBC, ~102×102 mm: Teensy 4.1 + XBee + BNO055/BME688/DPS310/INA260/MICS5524 sensor suite,
dual buck regulators, servo/ESC headers, buzzer — "TEAM TEJAS" silkscreen.*

| Top | Bottom |
|---|---|
| ![3D top](docs/renders/3d-top.png) | ![3D bottom](docs/renders/3d-bottom.png) |

*Renders by KiCad 10 `pcb render` (high quality). Custom SnapEDA 3D bodies are absent
(their `.step` files use absolute `C:/Open Source/…` paths from the design workstation),
so modules render as footprints — geometry and Gerbers are unaffected.*

## Board at a glance

- **Size:** 101.9 × 101.9 mm, 1.6 mm stackup, 2-layer (`docs/board-stats.rpt`)
- **Parts:** 41 BOM lines (`docs/bom.csv`): Teensy 4.1, XBee, BNO055, BME280/BME688,
  MICS5524, DPS310, INA260, 2× buck (MINI560/MP1584), XT30, S8421-45R, servo/ESC headers
- **Copper:** 0.3 mm min track, 0.2 mm clearance, 38 vias, 199 pads

## Contents

| Path | What it is |
|---|---|
| `hardware/Tejas.kicad_sch` | Schematic, KiCad 9.0, rev 2, dated 3-10-25 in title block |
| `hardware/Tejas.kicad_pcb` | Board layout (2.48 MB) |
| `hardware/Tejas.kicad_pro` | KiCad project settings (pristine Oct 2025; KiCad 10 migrates it on open — don't commit that) |
| `manufacturing/gerber-V4/` | Final Gerber release plotted 2025-10-09 22:02 (12 files, incl. `Tejas-job.gbrjob`) — pixel-identical to V3, see verdict below |
| `manufacturing/gerber-V3/` | Previous Gerber release 2025-10-09 22:01, kept for history |
| `docs/renders/` | 3D PNGs (top/bottom/iso), 2D front/back SVGs, schematic PDF — all generated from `hardware/` |
| `docs/renders/gerber-compare/` | V3 vs V4 renders (top/bottom + side-by-side) — verdict: identical |
| `docs/bom.csv` | Bill of materials exported from schematic (41 lines) |
| `docs/board-stats.rpt` | Layer/component/drill statistics |
| `docs/Tejas.pdf` | Board plot / fab drawing export (2025-10-05) |
| `docs/Tejas_Sch.pdf` | Schematic PDF export (2026-02-14) |
| `libs/` | Original symbol/footprint/3D libraries Tejas uses (`2472/`, `2652/`, Teensy, XBee, …) — see `libs/README.md` |
| `history/` | 25 KiCad auto-backup zips `Tejas-2025-10-04_232753.zip` → `Tejas-2025-10-18_032732.zip` + earliest standalone schematic `early-Tejas-2025-10-03.kicad_sch` — day-by-day design evolution, strongest proof of iterative authorship |
| `PROVENANCE.md` | SHA-256 hashes, timeline, and authorship statement |
| `AUTHORS` | Contribution record |

Symbols are embedded in the schematic and footprints in the layout, so the board opens
with stock KiCad 9/10 libraries; `libs/` additionally preserves the original
`.kicad_sym` / `.kicad_mod` / `.step` sources. Open `hardware/Tejas.kicad_pro` in **KiCad 9.0+**.

## Gerber V3 vs V4 — verdict

**V4 is the final release, and it is functionally identical to V3.**
Every file differs only in its two plot-timestamp comments (`TF.CreationDate` +
`G04 Created by KiCad …`); pixel-diff of 400 DPI renders (Cu + silk + edge,
top and bottom) is exactly zero — see `docs/renders/gerber-compare/compare-top.png`
and `compare-bottom.png`. V4 was plotted ~90 s after V3 and matches the project's
configured plot path (`Tejas_Gerber_V4/`), so send V4 to fab.

Bonus authorship evidence visible in the bottom render: the silkscreen carries
`TEAM TEJAS`, a QR code, and the team block
`SHRUTHI / RUJUL / Y. SAGAR / G. SAGAR / THANUSRI / SRINIDHI / RAGUVEER / CHIDVILAS`.

## Authorship & scope

- **Mine:** full PCB (schematic capture, footprint assignment, layout/routing, DRC,
  Gerber generation V3/V4) plus the **PFR PPT data-processing slides/analysis**
  (slides live in the team deck `PFR_2024-ASI-CANSAT-046.pptx`, not duplicated here
  to keep this repo hardware-clean).
- **Not mine / not claimed:** flight software, GUI, MCP server, telemetry logs,
  team photos/videos. Those remain with their respective authors and are
  intentionally excluded from this repo.

## Verify

```bash
git log --format=fuller
sha256sum hardware/* docs/*.pdf   # compare with PROVENANCE.md
```

KiCad backups in `history/` carry filesystem timestamps from 2025-10-03 to 2025-10-18
predating this commit; Gerber plot paths (`C:/Users/rujul/Downloads/Tejas_Gerber_V4/`)
also match the author's workstation.

## License

Hardware: **CERN Open Hardware Licence Version 2 – Strongly Reciprocal (CERN-OHL-S-2.0)**.
See `LICENSE`. Documentation (this README, PROVENANCE) © 2025 Rujul Rumale, CC-BY-4.0.

SPDX: `SPDX-License-Identifier: CERN-OHL-S-2.0`
