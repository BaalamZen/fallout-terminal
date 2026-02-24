# Fallout Terminal Build — Dimension Tracker

All measurements in **mm** unless noted. Tolerances shown where available from datasheets.

**Status key:** CONFIRMED = from datasheet/drawing, ESTIMATED = from community/specs, NEEDS MEASUREMENT = must verify with calipers

---

## Parts Readiness Checklist

| Part | Confirmed Specs | Needs Measurement |
|------|:---------------:|:-----------------:|
| 7" Touch Panel (CTP-5710) | [x] | [ ] |
| Driver Board (RTD2660H) | [x] | [ ] HDMI cable depth |
| RK61 Keyboard (external) | [x] | [ ] |
| RK61 PCB (bare board) | [ ] | [x] mounting holes, USB-C offset, stack height |
| 16mm LED Power Button | [x] | [ ] |
| 8mm Indicator LEDs (x10) | [ ] | [x] body length behind panel |
| Mushroom E-Stop (22mm) | [ ] | [x] verify head height, body depth |
| WH148 Potentiometers (x3) | [ ] | [x] verify shaft length, terminal protrusion |
| Momentary Buttons (x4) | [ ] | [x] verify body depth, actuator height |
| Raspberry Pi 4B | [x] | [ ] |
| Dayton DS90-8 Speaker | [x] | [ ] verify magnet diameter |
| PAM8403 Amp Board | [x] | [ ] |
| SABRENT AU-MMSA DAC | [x] | [ ] |
| Noctua NF-A4x20 Fan | [x] | [ ] |
| 2.5" SSD | [x] | [ ] |
| 12V PSU / DC Jack | [ ] | [x] barrel jack size, panel connector |
| 3D Printed Enclosure | [ ] | [x] internal cavity dims from STL |

**Score:** 10/17 confirmed | 7/17 need measurement

---

## 1. Display — 7" Capacitive Touch Screen (EP-0084 / CTP-5710)

### Touch Panel (CTP-5710)

| Dimension | Value | Status |
|-----------|-------|--------|
| Sensor outer width | 164.4 ±0.2 | CONFIRMED (drawing) |
| Lens outer width | 164.2 ±0.1 | CONFIRMED (drawing) |
| Viewable area (VA) width | 155.0 ±0.2 | CONFIRMED (drawing) |
| Sensor outer height | 99.3 ±0.2 | CONFIRMED (drawing) |
| Lens outer height | 99.1 ±0.1 | CONFIRMED (drawing) |
| Viewable area (VA) height | 88.0 ±0.2 | CONFIRMED (drawing) |
| Left bezel (edge to VA) | 2.9 | CONFIRMED (drawing) |
| Top bezel (edge to VA) | 2.9 | CONFIRMED (drawing) |
| Right bezel (edge to VA) | 6.5 | CONFIRMED (drawing) |
| Bottom bezel (edge to VA) | ~7.3 + FPC tail | CONFIRMED (drawing) |
| FPC tail width | 15.5 ±0.1 | CONFIRMED (drawing) |
| FPC tail length | 40.0 ±0.3 | CONFIRMED (drawing) |
| Panel thickness | 13.3 ±0.5 (at FPC corner) | CONFIRMED (drawing) |

### Driver Board (RTD2660H)

| Dimension | Value | Status |
|-----------|-------|--------|
| Board width | 90.60 ±0.3 | CONFIRMED (drawing) |
| Board height | 65.60 ±0.3 | CONFIRMED (drawing) |
| Board thickness (PCB) | ~1.6 | ESTIMATED (standard) |
| LVDS connector offset from left | 34.75 ±0.3 | CONFIRMED (drawing) |
| Mounting holes | 4x R1.50 ±0.1 (3mm dia) | CONFIRMED (drawing) |
| Mounting hole spacing W | 77.25 ±0.2 | CONFIRMED (drawing) |
| Mounting hole spacing H | 59.80 ±0.2 | CONFIRMED (drawing) |
| Component clearance (tallest) | ~11.00 ±0.3 (right side) | CONFIRMED (drawing) |
| HDMI port depth from board edge | ~8.50 ±0.3 | CONFIRMED (drawing) |
| VGA (DB15) port depth | ~10.50 ±0.3 | CONFIRMED (drawing) |
| Max depth with connectors | ~15 (HDMI cable) | NEEDS MEASUREMENT |

**Cutout for screen opening:** Minimum ~155 x 88 mm (VA), recommend 164 x 99 mm (full lens) with bezel trim overlap.

---

## 2. Keyboard — Royal Kludge RK61

### External (with case + keycaps)

| Dimension | Value | Status |
|-----------|-------|--------|
| Length | 292 | CONFIRMED (RK spec) |
| Width | 102 | CONFIRMED (RK spec) |
| Height (with keycaps) | 39 | CONFIRMED (RK spec) |
| Weight | ~500-550 g | CONFIRMED (RK spec) |

### PCB (bare board)

| Dimension | Value | Status |
|-----------|-------|--------|
| PCB length | ~285 | ESTIMATED (standard 60%) |
| PCB width | ~94.6 | ESTIMATED (GH60 ref) |
| PCB thickness | ~1.6 | ESTIMATED (standard) |
| Mounting holes count | 4 (back panel screws) | CONFIRMED (iFixit) |
| Mounting screw size | M2 x 5mm Phillips | CONFIRMED (iFixit) |
| Mounting hole positions | — | NEEDS MEASUREMENT (see KiCad PCB file) |
| USB-C port offset from edge | — | NEEDS MEASUREMENT (varies by revision) |
| USB-C port height from PCB | — | NEEDS MEASUREMENT |
| Plate thickness | ~1.5 | ESTIMATED (standard) |
| Switch socket height (hot-swap) | ~3.5 above PCB | ESTIMATED |
| Keycap top to PCB bottom | — | NEEDS MEASUREMENT |
| Key spacing (center-to-center) | 19.05 (1u standard) | CONFIRMED (Cherry MX spec) |
| PCB revision / marking | 130-081802-016 US, 2024/11/25 | CONFIRMED (photo) |

**Note:** RK61 uses PROPRIETARY mounting holes — NOT compatible with GH60/Poker tray-mount. Use KiCad files from `Royal Kludge RK61/RK61-PCB/` repo or caliper measurements for exact positions.

**KiCad source:** `Royal Kludge RK61/RK61-PCB/RK61(KiCad)-PcbDoc`

---

## 3. Panel Controls

### 16mm LED Power Button

| Dimension | Value | Status |
|-----------|-------|--------|
| Panel cutout diameter | Φ16 | CONFIRMED (drawing) |
| Thread | M16x1 | CONFIRMED (drawing) |
| Thread length | 19 | CONFIRMED (drawing) |
| Body diameter | Φ18 | CONFIRMED (drawing) |
| Head protrusion above panel | 1.5 | CONFIRMED (drawing) |
| Bezel/ring thickness | 3 | CONFIRMED (drawing) |
| Body length behind bezel | 29.7 | CONFIRMED (drawing) |
| Terminal protrusion behind body | 5.6 | CONFIRMED (drawing) |
| **Total depth behind panel** | **~35.3** (29.7 + 5.6) | CONFIRMED (drawing) |
| Hex nut width (across flats) | 51.7 / 50.4 | CONFIRMED (drawing) |
| Voltage | 12V DC | CONFIRMED (drawing + listing) |
| Circuit | 1NO + 1NC + LED (C1) | CONFIRMED (drawing) |
| Locking current | 5A | CONFIRMED (listing) |
| Carrying current | 15-0.5A | CONFIRMED (listing) |

### 8mm LED Indicator Lights (x10)

| Dimension | Value | Status |
|-----------|-------|--------|
| Panel cutout diameter | 8 (Φ7.6 body) | CONFIRMED (photo) |
| Mounting hole diameter | 8 | CONFIRMED (photo) |
| Wire lead length | 230 (23 cm) | CONFIRMED (photo) |
| Body length behind panel | — | NEEDS MEASUREMENT |
| Voltage | 12V DC | CONFIRMED (BOM) |

### Red Mushroom Emergency Stop (22mm, LA38-11ZS type)

| Dimension | Value | Status |
|-----------|-------|--------|
| Panel cutout diameter | 22 | CONFIRMED (BOM spec) |
| Mushroom head diameter | 40 | CONFIRMED (product listing) |
| Head height above panel | ~20-25 | ESTIMATED (product listing) |
| Max panel thickness | 4-6 | CONFIRMED (product listing) |
| Contact block diameter | ~30 | ESTIMATED (product listing) |
| Total length (front to back) | 72 | CONFIRMED (product listing) |
| **Body depth behind panel** | **~50-55** | ESTIMATED (72 total - ~20 above) |
| Overall envelope | 41 x 30 x 77 | CONFIRMED (product listing) |
| Contact config | 1NO + 1NC, DPST, 10A/660V | CONFIRMED (BOM spec) |

### B10K WH148 Potentiometers (x3)

| Dimension | Value | Status |
|-----------|-------|--------|
| Shaft diameter | 6 (D-shaft) | CONFIRMED (BOM spec) |
| Shaft length | 15 (common variant; 13/20 also exist) | CONFIRMED (datasheet) |
| Bushing thread | M7 x 0.75 | CONFIRMED (datasheet) |
| Bushing length | ~10 | CONFIRMED (datasheet) |
| Panel mounting hole | 7.2 (for M7 bushing) | CONFIRMED (datasheet) |
| Body dimensions | ~24 x 17 x 16 (excl. shaft/terminals) | CONFIRMED (datasheet) |
| Terminal pin spacing | 5 (center-to-center, 3 pins) | CONFIRMED (datasheet) |
| Terminal pin protrusion | ~7-8 below body | ESTIMATED |
| **Total depth behind panel** | **~32** (24 body + 8 terminals) | ESTIMATED |

### Momentary Buttons (x4, RB-Spa-846 / SparkFun COM-11996)

| Dimension | Value | Status |
|-----------|-------|--------|
| Thread diameter | 6.75 | CONFIRMED (SparkFun listing) |
| Panel mounting hole | 7 | CONFIRMED (SparkFun listing) |
| Overall length (incl. solder lugs) | 27 | CONFIRMED (SparkFun listing) |
| Body diameter (behind panel) | ~8 | ESTIMATED |
| Body depth behind panel | ~15-18 | ESTIMATED |
| Actuator height above panel | ~3-5 | ESTIMATED |
| Actuator diameter (button face) | ~8-9 | ESTIMATED |
| Terminal type | Solder lugs (2 pins), SPST-NO | CONFIRMED |

---

## 4. Compute — Raspberry Pi 4 Model B

| Dimension | Value | Status |
|-----------|-------|--------|
| Board dimensions | 85.6 x 56.5 | CONFIRMED (RPi spec) |
| Mounting holes | 4x M2.5 | CONFIRMED (RPi spec) |
| Mounting hole pattern | 58 x 49 (center-to-center) | CONFIRMED (RPi spec) |
| Mounting hole diameter | 2.7 | CONFIRMED (RPi spec) |
| Board thickness (PCB) | 1.4 | CONFIRMED (RPi spec) |
| Max component height (top) | ~16.2 (USB ports) | CONFIRMED (RPi spec) |
| Max component height (bottom) | ~2.5 (SD card slot) | CONFIRMED (RPi spec) |
| USB-C power port offset | 11.2 from left edge | CONFIRMED (RPi spec) |
| Micro-HDMI ports offset | 26, 39.5 from left edge | CONFIRMED (RPi spec) |
| USB-A ports offset | right edge, stacked | CONFIRMED (RPi spec) |
| Ethernet port offset | right edge | CONFIRMED (RPi spec) |

### Mounting Hole Coordinates (from bottom-left corner)

| Hole | X | Y | Status |
|------|---|---|--------|
| Bottom-left | 3.5 | 3.5 | CONFIRMED (RPi mech drawing) |
| Bottom-right | 61.5 | 3.5 | CONFIRMED (RPi mech drawing) |
| Top-left | 3.5 | 52.5 | CONFIRMED (RPi mech drawing) |
| Top-right | 61.5 | 52.5 | CONFIRMED (RPi mech drawing) |

---

## 5. Audio

### Dayton Audio DS90-8 3" Full-Range Driver

| Dimension | Value | Status |
|-----------|-------|--------|
| Overall outer diameter | 92.3 | CONFIRMED (Dayton datasheet) |
| Baffle cutout diameter | 70 | CONFIRMED (Dayton datasheet) |
| Overall depth behind baffle | 44.6 | CONFIRMED (Dayton datasheet) |
| Bolt circle diameter | 83.1 | CONFIRMED (Parts Express) |
| Mounting holes | 4x (90 deg spacing on bolt circle) | CONFIRMED (datasheet) |
| Mounting screw size | ~M4 / #8 | ESTIMATED (standard for 3" drivers) |
| Voice coil diameter | 20.4 | CONFIRMED (datasheet) |
| Magnet diameter | ~45-50 | ESTIMATED (from 227g magnet weight) |
| **Total depth incl. terminals** | **~50** | ESTIMATED (44.6 + terminal lugs) |

### PAM8403 Amplifier Board

| Dimension | Value | Status |
|-----------|-------|--------|
| PCB length | 21 | CONFIRMED (Components101) |
| PCB width | 18 | CONFIRMED (Components101) |
| PCB thickness | ~1.6 | ESTIMATED (standard) |
| Max component height | ~6-8 (above PCB) | ESTIMATED |
| Total height with wiring | ~10 | ESTIMATED |
| Mounting holes | None (use adhesive/cradle) | CONFIRMED |

**Connectors:** Power (2-pin) + audio input (3-pin/3.5mm) on one edge, speaker output (4-pin) on opposite edge.

### SABRENT AU-MMSA USB Sound Adapter

| Dimension | Value | Status |
|-----------|-------|--------|
| Dongle body | ~38 x 23 x 10 | CONFIRMED (Amazon listing) |
| USB-A plug | 12.0 x 4.5 (standard USB-A) | CONFIRMED (USB spec) |
| USB-A plug depth | ~17 | CONFIRMED (USB spec) |
| Total protrusion from USB port | ~55 | ESTIMATED |
| Weight | ~27 g | CONFIRMED (Amazon listing) |
| Audio jacks | 2x 3.5mm TRS (green=out, pink=mic) | CONFIRMED |

---

## 6. Cooling — Noctua NF-A4x20 PWM

| Dimension | Value | Status |
|-----------|-------|--------|
| Fan dimensions | 40 x 40 x 20 | CONFIRMED (Noctua spec) |
| Mounting hole spacing | 32 x 32 (center-to-center) | CONFIRMED (Noctua spec) |
| Mounting screw | M3 (self-tapping included) | CONFIRMED (Noctua spec) |
| Mounting hole diameter | ~3.5-4 | CONFIRMED (standard 40mm) |
| Weight | ~11.3 g | CONFIRMED (Noctua spec) |
| Cable length | 20 cm (+ 30 cm extension incl.) | CONFIRMED (Noctua spec) |
| Connector | 4-pin PWM, 12V DC | CONFIRMED |
| Max current | 0.05A (0.6W) | CONFIRMED (Noctua spec) |
| Panel cutout | 38 (square or circle) | CONFIRMED |

**Airflow direction:** Air pulls from label/sticker side, pushes out struts side. Arrows molded on frame edge.

**Included:** LNA adapter, Y-cable, extension cable, OmniJoin set, 4x anti-vibration mounts, fan screws.

---

## 7. Storage — 2.5" SATA SSD (SFF-8201 Standard)

| Dimension | Value | Status |
|-----------|-------|--------|
| Width | 69.85 | CONFIRMED (SFF-8201) |
| Length | 100.45 | CONFIRMED (SFF-8201) |
| Height (7mm, most SSDs) | 7.0 | CONFIRMED (SFF-8201) |
| Height (9.5mm, older HDDs) | 9.5 | CONFIRMED (SFF-8201) |
| Mounting screw | M3 x 0.5, 3-5mm length | CONFIRMED (Intel spec) |
| Bottom mounting holes | 4x (see positions below) | CONFIRMED (SFF-8201) |
| Side mounting holes | 4x (2 per side) | CONFIRMED (SFF-8201) |
| SATA connector position | Centered on one short edge | CONFIRMED |
| Clearance for SATA cable | ~15 above connector edge | ESTIMATED |
| **Total depth with cable** | **~115-120** | ESTIMATED |

### Bottom Mounting Hole Positions (from connector-side, right edge)

| Hole | X | Y | Status |
|------|---|---|--------|
| 1 | 4.07 | 14.0 | ESTIMATED (SFF-8201 cross-ref) |
| 2 | 4.07 | 90.6 | ESTIMATED (SFF-8201 cross-ref) |
| 3 | 65.79 | 14.0 | ESTIMATED (SFF-8201 cross-ref) |
| 4 | 65.79 | 90.6 | ESTIMATED (SFF-8201 cross-ref) |

Side holes: ~76.60 mm apart along length, 3.0 mm from bottom surface.

---

## 8. Power

### 12V 5A PSU

| Dimension | Value | Status |
|-----------|-------|--------|
| Dimensions | — | NEEDS MEASUREMENT (varies by unit) |
| DC barrel jack size | 5.5 x 2.1 (likely) | NEEDS MEASUREMENT |
| Panel cutout for jack | ~12 (if panel-mount) | NEEDS MEASUREMENT |

**Note:** The PSU itself is external. Only the DC barrel jack or panel-mount connector needs enclosure integration.

---

## 9. Enclosure — 3D Printed Shell

### Reference Files Available

| Source | File | Notes |
|--------|------|-------|
| Terminal File 1 | `the-fallout-terminal.3mf` | Original MyMiniFactory model |
| Terminal File 2 | `body.stl`, `Body_for_Raspberry_Pi_4B.stl` | Thingiverse remix (michaave) — Pi 4B cutouts, 3.5" Adafruit screen |
| Terminal File 3 | 9x individual STLs | Body, front inserts (upper/lower), back insert, back vent, keyboard tray, knob, screen holder, screen trim |

### Key Enclosure Questions

| Question | Status |
|----------|--------|
| Internal cavity depth (front to back) | NEEDS MEASUREMENT (from STL) |
| Screen opening dimensions (current) | Designed for 3.5" Adafruit — MUST MODIFY for 7" |
| Keyboard tray dimensions (current) | Designed for generic — MUST MODIFY for RK61 PCB |
| Panel drill positions for controls | TO BE DESIGNED |
| Ventilation opening for 40mm fan | TO BE DESIGNED |
| Speaker grille opening | TO BE DESIGNED |
| Cable routing clearances | TO BE DESIGNED |

---

## Panel Cutout Summary (Quick Reference)

| Component | Hole Shape | Size | Qty |
|-----------|-----------|------|-----|
| DS90-8 Speaker | Circle | 70 cutout + 4x holes on 83.1 BCD | 1 |
| 16mm Power Button | Circle | Φ16 | 1 |
| E-Stop Mushroom | Circle | 22 | 1 |
| Indicator LEDs | Circle | 8 | up to 10 |
| WH148 Potentiometers | Circle | 7.2 | 3 |
| Momentary Buttons | Circle | 7 | 4 |
| Noctua Fan | Square/Circle | 38 + 4x M3 at 32 spacing | 1 |
| DC Barrel Jack | Circle | ~12 | 1 |
| SABRENT 3.5mm jacks (if external) | Circle | 6 (x2, ~12 apart) | optional |

---

## Behind-Panel Depth Summary (Critical for Wall Thickness)

| Component | Depth Behind Panel | Status |
|-----------|--------------------|--------|
| E-Stop Mushroom | ~50-55 | ESTIMATED |
| DS90-8 Speaker | ~50 (incl. terminals) | ESTIMATED |
| 16mm Power Button | ~35.3 | CONFIRMED |
| WH148 Potentiometers | ~32 | ESTIMATED |
| Momentary Buttons | ~15-18 | ESTIMATED |
| 8mm Indicator LEDs | — | NEEDS MEASUREMENT |

**Deepest component:** E-Stop at ~55 mm. Enclosure must accommodate this behind any panel where it mounts.

---

## Items Still Needing Physical Measurement

| # | Component | What to Measure |
|---|-----------|-----------------|
| 1 | RK61 PCB | Length, width, mounting hole positions, USB-C offset |
| 2 | RK61 PCB | Plate-to-PCB gap, total stack height with keycaps |
| 3 | 8mm indicator LEDs | Body length behind panel |
| 4 | 12V PSU | DC barrel jack size, panel-mount connector dims |
| 5 | Driver board + panel stack | Combined depth when assembled |
| 6 | STL enclosure files | Import to CAD and measure internal cavity |