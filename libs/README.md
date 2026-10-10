# libs/ — all footprint / symbol / 3D files found on this PC

Gathered 2026-10-10 from `C:/Users/rujul/OneDrive/Documents/KiCad_Libraries/`
into this one place so the repo is self-contained.

## What is here (27 library files + docs)

| Folder | Contents |
|---|---|
| `GY-521/` | `GY-521.kicad_sym`, `MODULE_GY-521.kicad_mod`, `GY-521.step` (MPU6050 module) |
| `HC-12/` | `HC-12.kicad_sym`, `MA05-1.kicad_mod`, `HC-12.step` (SI4463 RF module) |
| `KiCad_ESP32-C3-SuperMini-master/` | `ESP32-C3-SuperMini.kicad_sym`, `ESP32-C3-SuperMini.pretty/*.kicad_mod`, `ESP32-C3-SuperMini.stp` |
| `MP1584-KiCad-Symbol-Footprint-main/` | `MP1584module.kicad_sym`, `MP1584module.kicad_mod` (buck module used on Tejas 3D ref `MP1584 Regulador.step`) |
| `ZC323200/` | `ZC323200.kicad_sym`, `XCVR_ZC323200.kicad_mod` |
| `KiCad_msalamon-master/` | `msalamon.pretty/` — 12 generic `.kicad_mod` (tact switch, battery, DS3231, HC-05 adapter, Nucleo, SOP8, USB_AB…) |

## Important: what Tejas actually uses vs what is here

Tejas's schematic symbols (`2472:`, `2652:`, `teensy:`, `XB24-*:`, `XT30UPB-M:`,
`BUCK_5A:`, `DPS310:`, `INA260:` …) are **embedded** in `hardware/Tejas.kicad_sch`
(`lib_symbols` section) and its footprints are **embedded** in
`hardware/Tejas.kicad_pcb` — so the board opens and plots Gerbers with stock
KiCad 9/10 libraries only. Proof: `manufacturing/gerber-V4/` was generated from it.

The **source** `.pretty` folders for those SnapEDA footprints lived on the
original design workstation under `C:/Open Source/…` (see 3D refs
`C:/Open Source/2472/2472.step`, `C:/Open Source/2652/2652.step`,
`C:/Open Source/teensy_library-master/…` in `Tejas.kicad_pcb`) and are **not**
on this PC — KiCad backup zips only store the 4 project files, never libs.
To make the repo 100% editable-footprint-complete, copy from the original PC:

- `C:/Open Source/2472/` (MODULE_2472, MINI560, DPS 310, INA_260, MP1284, MICS 5524…)
- `C:/Open Source/2652/` (MODULE_2652)
- `C:/Open Source/teensy_library-master/` (Teensy41)
- `C:/Open Source/` XBee `XB24-ASI-001 / XB24CDMPIT-001` + `XT30UPB-M` `.pretty` folders
- `C:/Open Source/2472/*.STEP` 3D models (7 refs, all `C:/Open Source/…` absolute paths)

Drop them under `libs/` preserving `<name>.pretty/` layout and commit — KiCad
will resolve them once added to the footprint library table. Until then, do NOT
delete the embedded footprints from the `.kicad_pcb`.
