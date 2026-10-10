# Provenance — proof of authorship

**Designer:** Rujul Rumale <rujul.rumale@gmail.com>
**Artifact:** Tejas CanSat OBC PCB (INSPACe CanSat)
**Repo created:** 2026-10-10, curated from working folder `INSPACe_Can/tejas/`
**Source workstation path embedded in project:** `C:/Users/rujul/Downloads/Tejas_Gerber_V4/`
(`hardware/Tejas.kicad_pro`, `pcbnew.last_paths.plot`)

## SHA-256 (at time of curation)

| File | SHA-256 |
|---|---|
| `hardware/Tejas.kicad_pcb` | `34EB7ADCE4EB176BF5D209BD81BB5EEEB30C2339E8D29E24B8A98235EA0738BC` |
| `hardware/Tejas.kicad_pro` | `DBC62E33C33E39769E606A6D727C95B8F00AF4127BA4BDCD4596C21833E2D409` |
| `hardware/Tejas.kicad_sch` | `11DECA7BF7DDED36F694C0AE2E12FCA72740EB722455E79FDE70E15D2B176368` |
| `docs/Tejas.pdf` | `5ED2C2F5B795454C48E4ACE9A6849DAB436B2C551E78BEA5549AC84B3E83D411` |
| `docs/Tejas_Sch.pdf` | `716EFF7B3825487D1E6ABF25025DA3EF8526C9DDD39679D6CA9AD15F7A9C96B3` |

Verify any time with: `git hash-object hardware/Tejas.kicad_pcb` or `sha256sum`.

## Design timeline (from KiCad auto-backups + file dates)

- 2025-10-04 23:27 → first backup `Tejas-2025-10-04_232753.zip` (847,533 B)
- 2025-10-05 → 5 iterations (schematic capture phase)
- 2025-10-06 → 5 iterations incl. 2.1 MB layout `154121` (placement/routing)
- 2025-10-07 → schematic + layout refinement
- 2025-10-09 22:01/22:02 → Gerber releases V3 then V4 (final, 12 files each)
- 2025-10-11 → final PCB + project saves (`Tejas.kicad_pcb` 2025-10-11 14:02)
- 2026-02-14 → schematic PDF re-export for PFR deck

Full list of 25 zips is in `history/` with original timestamps preserved by this commit.

## Contribution statement

I, Rujul Rumale, designed the Tejas CanSat PCB end-to-end: schematic (KiCad 9.0,
rev 2), component selection/footprints (incl. SnapEDA Adafruit 2472 BNO055 import),
layout, DRC, and Gerber V3/V4 manufacturing release. I also authored the
data-processing portion of the PFR presentation. Flight software, GUI, MCP server,
and telemetry operations are the work of teammates and are NOT claimed here.

Signed: Rujul Rumale, 2026-10-10.
