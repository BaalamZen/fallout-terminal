# Fallout-Style Raspberry Pi Terminal — MASTER FILE

> Single source of truth for the Fallout terminal build. This file consolidates **design intent, confirmed decisions, outstanding gaps, BOM, and shopping list**.
> Updated to match BOM v12 + confirmed layout decisions.

---

## 1. Project Overview

**Goal:** Build a functional Fallout-inspired desktop terminal using a Raspberry Pi 4B, with a 7" landscape display, physical controls, ambient audio, and a compact mechanical keyboard — all housed in a rugged, industrial enclosure with visible hardware.

**Design Keywords:** Fallout, retro-futurist, industrial, worn metal, tactile controls, visible screws, equipment-not-a-toy.

**Design Principles:**
- Compact but chunky — feels like equipment, not a toy
- Physical controls over touch (tactile > touch)
- Audible ambient hum — machine should feel "alive"
- Fully functional keyboard (not decorative)
- Visible screws and metal hardware are intentional, not hidden

---

## 2. Core Architecture (CONFIRMED)

### Compute
- **Raspberry Pi:** 4B 4GB (owned)
- **Why:** USB 3.0 for SSD boot, mature OS support, GPIO access
- **Boot Medium:** USB SSD (no SD)

### Display
- **Kit:** EP-0084 7" Capacitive Touch Screen DIY Kit
- **Resolution:** 1024x600
- **Inputs:** HDMI / VGA / AV
- **Touch:** 10-point capacitive
- **Power:** 5V@2A / 9V@1.5A / 12V@1A
- **Includes:** LCD panel + driver board + CTP board + OSD keypad
- **Orientation:** Landscape
- **Mounting:** Slightly recessed, visible screws (intentional aesthetic)

### Display Dimensions (from datasheet)
- Outer (Sensor OD): 164.4mm x 99.3mm
- Lens OD: 164.2mm x 99.1mm
- Viewable area: 155.0mm x 88.0mm
- Panel thickness: ~2.9mm
- Ribbon cable: 40mm long, 15.5mm wide (30-pin)
- Driver board (RTD2660H): 90.6mm x 65.6mm

---

## 3. Enclosure & 3D Files (NEEDS REDESIGN)

The original STL files were designed for a 3.5" Adafruit screen and a decorative keyboard. With the 7" display and RK61 bare PCB, the enclosure **requires a full redesign** in CAD.

### Reference STL Files (from original project)
- `body.stl`
- `screen-holder.stl`
- `screen-trim.stl`
- `front-insert-upper-v2.stl`
- `front-insert-lower.stl`
- `back-insert-v2.stl`
- `back-vent.stl`
- `keyboard.stl`

### Redesign Requirements
- 7" display cutout (~164.4mm x 99.3mm)
- RK61 bare PCB cavity (~285mm x 98mm, depth TBD after disassembly)
- Internal volume for: Pi 4B, SSD + bracket, driver board, CTP board, amp board, fan
- Panel-mount holes for: 3x 8mm LEDs, 2x momentary buttons, 1x potentiometer, 1x amp knob, E-stop
- Rear/side ventilation for Noctua fan
- Maintain disassembly access (no glue traps)

---

## 4. Storage System (CONFIRMED)

### SSD
- **Type:** 2.5" SATA SSD
- **Capacity:** 250GB
- **Model:** WD Blue SATA SSD (purchased)

### SSD Mount
- **Item:** Aluminum 2.5" SSD mounting brackets (purchased)
- **Fastening:** M3 screws
- **Aesthetic:** Industrial Fallout look + passive cooling

### USB-SATA Adapter
- **Type:** USB 3.0 to SATA III
- **Features:** UASP support
- **Power:** Bus-powered (2.5" only)

**Explicitly NOT using:** NVMe, Pi 5 PCIe hats, external enclosures.

---

## 5. Keyboard System (CONFIRMED)

### Keyboard
- **Model:** Royal Kludge RK61 (purchased)
- **Layout:** 60% (61 keys)
- **Connection to Pi:** Bluetooth 5.0
- **Internal power:** Always-on via short internal USB-C cable (charges battery, eliminates battery management)
- **Installation:** Bare PCB only (plastic case removed), keycaps + switches remain mounted
- **Hot-swap:** Yes (3-pin / 5-pin MX switches)

### External Dimensions (with case)
- 289-292mm x 100-103mm x 39mm

### Disassembly
- 4x M2 screws on back panel
- Remove plastic top/bottom case, retain PCB + plate + switches + keycaps
- Bare PCB dimensions: TBD (measure after disassembly)

---

## 6. Keyboard Switches (OPEN DECISION)

**Requirements:**
- MX-style
- 5-pin preferred
- RGB compatible

**Options Discussed:**
- Gateron Green Apple (tactile, heavier)
- Gateron Cream Silent (linear, quiet)

**Recommendation:** Linear or light tactile to avoid competing with ambient audio.

**Status:** Outstanding - finalize exact switch SKU.

---

## 7. Audio System (PARTIALLY CONFIRMED)

### Purpose
- Ambient Fallout-style hum
- System bleeps and feedback

### Components
- **Amplifier:** PAM8403 stereo 5V 3Wx2 (purchased)
- **Volume Control:** PAM8403 onboard potentiometer, exposed as bottom-right knob on front panel
- **Speaker:** Mini 8ohm 3W (NOT YET PURCHASED - spec TBD)
- **Audio Source:** USB audio DAC (REQUIRED — Pi analog output is too noisy for ambient/hum audio)

### Placement
- Speaker behind front vent or grille
- Amp board mounted internally

---

## 8. Cooling System (CONFIRMED)

- **Fan:** Noctua 40x40x20mm PWM (owned)
- **Purpose:** Case airflow across Pi + power boards
- **Control:** Front-panel potentiometer (top-right knob)

**Outstanding:** Choose PWM (GPIO) vs inline voltage controller.

---

## 9. Front Panel Layout (CONFIRMED)

```
╔═══════════════════════╗
║                       ║  ◎ Potentiometer (top knob)
║     7" DISPLAY        ║
║     (EP-0084)         ║  ◎ PAM8403 volume (bottom knob)
║                       ║
╚═══════════════════════╝
    ○  ○  ○
    3x LEDs (horizontal)

┌───────────────────────────┐  [BTN1]
│     RK61 bare PCB         │  [BTN2]
│     (Bluetooth to Pi)     │
└───────────────────────────┘
```

### Controls Detail

| Control | Type | Mount | Position |
|---|---|---|---|
| Knob (top-right) | B10K linear potentiometer, 6mm shaft | Panel-mount | Right of screen, top |
| Knob (bottom-right) | PAM8403 onboard volume | Panel-mount | Right of screen, bottom |
| LED x3 | 12V 8mm metal indicators | 8mm panel holes | Horizontal, under screen |
| Button x2 | Momentary push button, panel-mount | Panel-mount | Right of keyboard, 3D printed caps |
| E-stop | Red mushroom 22mm, latching, 1NO+1NC | 22mm panel hole | Left side or top-left rear (TBD) |

### Aesthetic Rules
- Industrial
- Metal / Bakelite style
- No glossy modern plastics

---

## 10. Power System (CONFIRMED)

### Dual Rail
- **5V rail:** Raspberry Pi 15W USB-C PSU (5.1V 3A) - dedicated to Pi
- **12V rail:** 12V 5A PSU - LEDs, accessories

### Thermal
- **Passive:** Adhesive aluminum heatsink set on Pi chips
- **Active:** Noctua 40mm PWM fan

### Power Switch
- **E-stop (mushroom):** Master kill / dramatic control (latching, twist-release)
- **Soft shutdown:** TBD — momentary switch + GPIO or E-stop wired to relay
- **Recommended approach:** Soft-shutdown script + momentary switch (prevents SSD corruption from hard power cuts)

**Outstanding:** Finalize soft vs hard cut implementation.

---

## 11. Software (HIGH-LEVEL)

- Raspberry Pi OS (Lite or minimal desktop)
- Terminal UI focus (Fallout-style green/amber text interface)
- Fallout-style static screen / boot animations

### Audio Software
- Looping ambient hum (machine "alive" background)
- Randomized system bleeps and feedback sounds
- Volume controlled physically via front-panel knob (not software)

---

## 12. OUTSTANDING DECISIONS

1. Keyboard switch model (MX, exact SKU)
2. Fan control method (PWM GPIO vs inline voltage)
3. Power switch logic (soft shutdown via GPIO vs hard cut)
4. Speaker selection (size, impedance, mounting)
5. USB audio DAC model selection (required, not optional)
6. LED indicator assignments (which 3 colors, what they signal)
7. Momentary button functions (Enter/Execute? Power/Mode?)
8. E-stop exact position (left side vs top-left rear)
9. Enclosure redesign (CAD tool, who models it)
10. Bare RK61 PCB measurements (after disassembly)

---

## 13. BILL OF MATERIALS (BOM v12)

### Core
- Raspberry Pi 4B 4GB (owned)
- 7" Capacitive Touch Screen Kit EP-0084 (purchased)
- Raspberry Pi 15W USB-C PSU (purchased)

### Storage
- WD Blue 2.5" SATA SSD 250GB (purchased)
- Aluminum 2.5" SSD mounting brackets (purchased)
- USB 3.0 to SATA III adapter, UASP (purchased)

### Keyboard
- Royal Kludge RK61 60% mechanical keyboard (purchased)
- Short internal USB-C cable for always-on power (needed)
- MX switches (TBD)
- Keycaps (TBD or stock RK61)

### Audio
- PAM8403 5V 3Wx2 stereo amplifier board (purchased)
- Speaker 8ohm 3W mini (NOT YET PURCHASED)

### Cooling
- Noctua 40x40x20mm PWM fan (owned)
- Adhesive aluminum heatsink set (purchased)

### Power
- 12V 5A power supply (purchased)

### Controls & Indicators
- B10K linear potentiometers x3 pack (purchased, using 1)
- 12V 8mm LED panel indicators x10 pack (purchased, using 3)
- Red mushroom E-stop 22mm, 1NO+1NC (purchased)
- Momentary push buttons x4 pack (purchased, using 2)

### Enclosure
- Custom 3D printed Fallout terminal enclosure (to be redesigned)

---

## 14. SHOPPING LIST (ACTIONABLE)

**Already Purchased / Owned**
- Raspberry Pi 4B 4GB
- 7" EP-0084 touch screen kit
- Pi 15W USB-C PSU
- WD Blue 250GB SSD
- Aluminum SSD mounting brackets
- USB 3.0 to SATA adapter
- Royal Kludge RK61 keyboard
- PAM8403 amplifier board
- B10K potentiometers (3-pack)
- 12V 8mm LED indicators (10-pack)
- Red mushroom E-stop (22mm)
- Momentary push buttons (4-pack)
- 12V 5A PSU
- Noctua 40mm fan
- Pi heatsink set

**To Buy (High Priority)**
- Speaker (mini, 8ohm 3W or similar - spec TBD)
- Short USB-C cable (internal, for RK61 power)
- MX switch set (if replacing stock RK61 switches)

**To Buy (Build Phase)**
- Assorted M3 screws + standoffs
- Wiring (Dupont, JST connectors)
- Heat shrink / wire management

**Optional / Finish**
- Label plates
- Faux wear / weathering materials
- Sleeved internal wiring
- USB audio DAC (required — Pi analog is too noisy)

---

## 15. BUILD NOTES

- Preserve SSD airflow alignment with rear vent
- Keep USB cable routing serviceable
- Ground audio amp cleanly (separate from digital ground if possible)
- Maintain disassembly access (no glue traps)
- RK61 PCB needs Bluetooth pairing to Pi on first setup
- 12V LEDs wire directly to 12V rail (no resistor needed, built-in)
- E-stop NC contact can cut main power; NO contact can trigger GPIO for soft shutdown
- Model USB cable routing in CAD before final assembly — tight enclosure means routing matters
- Labels on controls optional but recommended (engraved or printed plates)

---

## 16. PROJECT STATUS SUMMARY

| Subsystem | Status |
|---|---|
| Enclosure / STL | Needs redesign for 7" + RK61 |
| Raspberry Pi | Owned |
| Display (7" EP-0084) | Purchased |
| SSD + Mount | Purchased |
| Keyboard (RK61) | Purchased |
| Switches | Open — finalize SKU |
| Audio amp (PAM8403) | Purchased |
| Speaker | NOT YET PURCHASED |
| USB Audio DAC | NOT YET PURCHASED |
| Cooling (Noctua fan) | Owned |
| Power (12V + 5V PSUs) | Purchased |
| Controls (LEDs, buttons, pots, E-stop) | Purchased |
| Wiring / connectors | Not yet purchased |
| Software | Not started |

---

**Project Status:** BOM largely purchased. Outstanding work: speaker selection, USB DAC purchase, switch selection, enclosure redesign (major), wiring design, and software.
