# libs/ — symbol / footprint / 3D sources

Two sources, gathered 2026-10-10 into this one place so the repo is self-contained:

**A. Original Tejas libraries** (recovered from the design-workstation backup
`D:/Backup/Open Source/KICAD Stuff/` — the `C:/Open Source/…` paths referenced
inside `hardware/Tejas.kicad_pcb`):

| Folder | Contents |
|---|---|
| `2472/` | `2472.kicad_sym` + 7 `.kicad_mod` (MODULE_2472/BNO055, MINI560 + MP1284 bucks, DPS 310, INA_260, MICS 5524) + 5 `.step` (+ `.dxf`) |
| `2652/` | `2652.kicad_sym` + `MODULE_2652.kicad_mod` (BME280) + 2 `.step` |
| `teensy_library-master/` | `Teensy41.kicad_mod` + 19 MB `Teensy_4.1_Assembly.STEP` (+ legacy `.lib/.dcm`) |
| `TEENSY_4.1/` | Alternate `TEENSY_4.1.kicad_sym` + `TEENSY41.kicad_mod` + `.step` |
| `XB24-ASI-001/` / `XB24CDMPIT-001/` | XBee `.kicad_sym` + `DIP-20.kicad_mod` (+ XBee `.step`) |
| `S8421-45R/` | Harwin coin-cell retainer `.kicad_sym` + `.kicad_mod` |
| `XT30UPB-M.*` | XT30 connector `.kicad_sym` + `.kicad_mod` + `.step` (top level) |
| `Sensors_Kicad_Lib_Footprint-main/` | `DHT11.kicad_mod`, `MICS5524.kicad_sym`, sensor footprint collection |

**B. Other libraries on this PC** (from `OneDrive/Documents/KiCad_Libraries/`,
not used by Tejas, kept for reference): `GY-521/`, `HC-12/`,
`KiCad_ESP32-C3-SuperMini-master/`, `MP1584-KiCad-Symbol-Footprint-main/`,
`ZC323200/`, `KiCad_msalamon-master/` (12 generic `.kicad_mod`).

## Notes

- Symbols are also **embedded** in `hardware/Tejas.kicad_sch` and footprints in
  `hardware/Tejas.kicad_pcb`, so the board opens with stock KiCad 9/10 alone.
  These sources are kept so footprints/symbols stay editable.
- The `.step` 3D paths in the `.kicad_pcb` are absolute (`C:/Open Source/…`);
  copy this `libs/` tree to that location (or remap `KICAD_USER_DIR`) to restore
  full 3D bodies in the editor.
- Do NOT delete the embedded footprints from the `.kicad_pcb`.
