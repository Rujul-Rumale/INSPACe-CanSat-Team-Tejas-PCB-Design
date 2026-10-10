# Tejas CanSat — Onboard Computer (OBC) PCB

**Author / Designer: Rujul Rumale <rujul.rumale@gmail.com>**
**Project: INSPACe CanSat — "Tejas"**
**Role claimed: PCB design (schematic + layout + Gerber release) and PFR PPT data-processing section**

This repository is the author's clean, attributable record of the **PCB contribution** to the
INSPACe CanSat team project. It was created on 2026-10-10 from the working project folder
to establish a verifiable, timestamped record of authorship.

> If you reuse this design you must retain this authorship notice and comply with the
> license in `LICENSE` (CERN-OHL-S-2.0).

## Contents

| Path | What it is |
|---|---|
| `hardware/Tejas.kicad_sch` | Schematic, KiCad 9.0, rev 2, dated 3-10-25 in title block |
| `hardware/Tejas.kicad_pcb` | Board layout (2.48 MB) |
| `hardware/Tejas.kicad_pro` | KiCad project settings |
| `manufacturing/gerber-V4/` | Final Gerber release plotted 2025-10-09 22:02 (12 files, incl. `Tejas-job.gbrjob`) |
| `manufacturing/gerber-V3/` | Previous Gerber release 2025-10-09 22:01, kept for history |
| `docs/Tejas.pdf` | Board plot / fab drawing export (2025-10-05) |
| `docs/Tejas_Sch.pdf` | Schematic PDF export (2026-02-14) |
| `history/` | 25 KiCad auto-backup zips `Tejas-2025-10-04_232753.zip` → `Tejas-2025-10-18_032732.zip` — day-by-day design evolution, strongest proof of iterative authorship |
| `PROVENANCE.md` | SHA-256 hashes, timeline, and authorship statement |
| `AUTHORS` | Contribution record |

No custom symbol/footprint libraries are required: all symbols are embedded in
`Tejas.kicad_sch` (stock KiCad + SnapEDA imports, e.g. Adafruit 2472 / BNO055) and the
project uses stock KiCad footprints. Open `hardware/Tejas.kicad_pro` in **KiCad 9.0+**.

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
sha256sum hardware/* docs/*   # compare with PROVENANCE.md
```

KiCad backups in `history/` carry filesystem timestamps from 2025-10-04 to 2025-10-18
predating this commit; Gerber plot paths (`C:/Users/rujul/Downloads/Tejas_Gerber_V4/`)
also match the author's workstation.

## License

Hardware: **CERN Open Hardware Licence Version 2 – Strongly Reciprocal (CERN-OHL-S-2.0)**.
See `LICENSE`. Documentation (this README, PROVENANCE) © 2025 Rujul Rumale, CC-BY-4.0.

SPDX: `SPDX-License-Identifier: CERN-OHL-S-2.0`
