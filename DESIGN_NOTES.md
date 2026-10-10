# Design notes

Background on how this board came together — revision history, the V3/V4 story,
and what's what in this repo.

## How it evolved

- **Oct 3** — first schematic draft (`history/early-Tejas-2025-10-03.kicad_sch`, 70 KB)
- **Oct 4–5** — schematic capture (10 backup snapshots)
- **Oct 6** — placement and routing (5 snapshots, incl. the 2.1 MB layout pass)
- **Oct 7** — schematic + layout refinement
- **Oct 9, 22:01/22:02** — Gerber releases V3 then V4 (see below)
- **Oct 11** — final board + project saves; plus a board-outline experiment (see below)
- **Oct 18** — last session touch; **Feb 2026** — schematic PDF re-export for our PFR deck

All 25 KiCad auto-backup snapshots are in `history/` with their original timestamps.

## V3 vs V4 Gerbers

V4 is the release we flew. V3 was plotted ~90 seconds earlier and the two are
functionally identical — every file differs only in its plot-timestamp comments,
and 400 DPI renders (copper + silk + edge, top and bottom) come out pixel-identical.
See `docs/renders/gerber-compare/compare-top.png` and `compare-bottom.png`.
V4 also matches the project's configured plot path, so it's the one to build from.

## The outline experiment (not flown)

After the V4 release I tried redrawing the board outline in the working file —
stepped/notched edges, mounting holes removed. We decided not to go with it, so
`hardware/Tejas.kicad_pcb` (Oct 11 state) differs from the V4 Gerbers in exactly
that: Edge.Cuts redraw + the 6 copper zones refilled against the new outline.
Everything else is untouched — same 34 footprints in the same places, same
351 tracks, 38 vias, same nets, same schematic. Don't fab from `hardware/`
without revisiting that decision.

## Renders in this repo

`docs/renders/` (made with KiCad 10): `3d-iso.png`, `3d-top.png`, `3d-bottom.png`
(raytraced), `pcb-front.svg` / `pcb-back.svg` (copper + silk + mask), `schematic.pdf`,
and the `gerber-compare/` V3-vs-V4 set. The custom module 3D bodies live at absolute
`C:/Open Source/…` paths from my old workstation, so the 3D views show footprints
where modules would be — copy `libs/` to that location to restore them in the editor.

## Related files (same backup, outside this repo)

- `D:/Backup/Open Source/KICAD Stuff/` — where the `libs/` sources were recovered from
- `D:/Backup/Users/Downloads/07_Archives/Archives/` — `Tejas.zip` (32 MB project
  archive), `Tejas_Gerber.zip`, `Tejas_Gerber_V4.zip`
- `D:/Backup/Users/Downloads/01_Documents/` — component selection notes, requirements,
  `Tejas_PCB.pdf`, `TEJAS_PCB_V2.pdf`

## Housekeeping notes

- Opening the project in KiCad 10 rewrites `.kicad_pro` (settings migration, no
  design effect) — `*.lck` and `.history/` are git-ignored for that reason, and
  `hardware/` pins the original Oct 2025 bytes.
- I work with `rujul.rumale@gmail.com` as my commit identity.
