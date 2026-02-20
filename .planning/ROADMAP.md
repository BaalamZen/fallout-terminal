# Roadmap: Fallout Pi Terminal

**Created:** 2026-02-19
**Milestone:** v1.0 — Functional Terminal Build

## Overview

8-phase build sequence from component decisions through final finishing. Phases follow natural hardware build order — decisions and measurements before CAD, CAD before printing, printing before assembly, assembly before software.

## Phases

### Phase 1: Component Decisions & Procurement

**Goal:** Finalize all 10 outstanding decisions and purchase remaining components.

**Requirements:** PROC-01, PROC-02

**Deliverables:**
- Keyboard switch selection documented (model, quantity)
- Speaker selection documented (model, specs)
- USB Audio DAC selected and ordered
- Fan control method decided (PWM GPIO vs inline voltage)
- Power switch logic decided (soft shutdown vs hard cut)
- LED color assignments decided (3 colors, what they signal)
- Momentary button functions assigned
- E-stop exact position decided
- CAD tool selected
- All remaining components ordered

**Success criteria:** All 10 outstanding decisions resolved, documented in master file, remaining parts on order.

---

### Phase 2: RK61 Disassembly & Measurement

**Goal:** Disassemble RK61, measure bare PCB, and document dimensions for CAD.

**Requirements:** PROC-03

**Deliverables:**
- RK61 plastic case removed (4x M2 screws)
- Bare PCB dimensions measured (L x W x H with switches)
- Mounting hole positions documented
- USB-C port position and clearance documented
- Photos of bare PCB from all angles
- Dimension drawing or sketch for CAD reference

**Success criteria:** Complete dimension reference sufficient for CAD enclosure design.

---

### Phase 3: Enclosure CAD Design

**Goal:** Design complete enclosure in CAD accommodating all components.

**Requirements:** ENCL-01, ENCL-02, ENCL-03, ENCL-04, ENCL-05, ENCL-06

**Deliverables:**
- Multi-part enclosure model (printable on standard FDM printer)
- 7" display cutout with mounting features
- RK61 PCB cavity with mounting posts
- Panel-mount holes for all controls
- Internal mounting for: Pi 4B, SSD bracket, driver board, CTP board, amp board
- Fan mount with ventilation
- Cable routing channels
- Screw-together assembly (no glue)
- Exported STL files ready for slicing

**Success criteria:** Complete CAD model with all components fitting, exported as printable STLs.

**Dependencies:** Phase 2 (RK61 PCB dimensions required)

---

### Phase 4: 3D Printing & Test Fit

**Goal:** Print enclosure and verify all components physically fit.

**Requirements:** ENCL-07

**Deliverables:**
- All enclosure parts printed
- Dry-fit of every component (no wiring, just physical placement)
- Fit issues documented and CAD revisions made if needed
- Final printed parts ready for assembly

**Success criteria:** Every component drops into its designated position without interference.

**Dependencies:** Phase 3 (STL files required)

---

### Phase 5: Electrical Design & Wiring

**Goal:** Design and build the complete wiring harness.

**Requirements:** ELEC-01 through ELEC-07

**Deliverables:**
- Wiring diagram / schematic documented
- 5V rail: Pi USB-C PSU connection
- 12V rail: PSU → LEDs, accessories
- E-stop wiring (NC for power cut, NO for GPIO soft shutdown)
- GPIO connections: buttons, potentiometer, fan control
- LED wiring to 12V rail
- All connectors crimped/soldered with serviceable disconnects
- Wiring harness test (continuity, no shorts)

**Success criteria:** Complete wiring harness tested outside enclosure, all circuits functional.

**Dependencies:** Phase 1 (component decisions for wiring specs)

---

### Phase 6: Physical Assembly

**Goal:** Install all components into enclosure with full wiring.

**Requirements:** DISP-01 through DISP-04, KEYB-01 through KEYB-04, AUDI-01 through AUDI-04, COOL-01 through COOL-03

**Deliverables:**
- Display mounted (LCD panel + driver board + CTP board)
- HDMI connected to Pi, touch USB connected
- RK61 bare PCB mounted, USB-C power routed
- Bluetooth paired to Pi
- PAM8403 amp + speaker mounted and wired
- USB DAC connected
- Noctua fan + heatsinks installed
- All controls installed (knobs, LEDs, buttons, E-stop)
- SSD + bracket mounted
- Pi 4B mounted
- Complete functional test (power on, display works, keyboard types, audio plays, controls respond)

**Success criteria:** Terminal powers on, displays output, accepts keyboard input, plays audio, all controls functional.

**Dependencies:** Phase 4 (printed enclosure), Phase 5 (wiring harness)

---

### Phase 7: Software & UI

**Goal:** Configure Pi OS and build Fallout-style terminal interface.

**Requirements:** SOFT-01 through SOFT-06, AUDI-05

**Deliverables:**
- Raspberry Pi OS installed on USB SSD
- Auto-boot to Fallout terminal UI (no desktop)
- Green/amber CRT-style text rendering
- Boot animation (Fallout startup sequence)
- Ambient hum audio loop on startup
- System bleed/feedback sounds
- GPIO script for button inputs and LED control
- Fan speed control via potentiometer reading

**Success criteria:** Terminal boots to Fallout UI automatically, ambient audio plays, all physical controls are software-responsive.

**Dependencies:** Phase 6 (assembled hardware to develop against)

---

### Phase 8: Finishing & Weathering

**Goal:** Apply final aesthetic treatment to make it look like real Fallout equipment.

**Requirements:** FNSH-01 through FNSH-03

**Deliverables:**
- Enclosure painted/weathered (faux wear, industrial look)
- Control labels applied (engraved plates or printed decals)
- Internal cable management tidied
- Final beauty photos
- Project documentation complete

**Success criteria:** Terminal looks like it belongs in the Fallout universe — worn, industrial, purposeful.

**Dependencies:** Phase 7 (functional terminal to finish)

---

## Phase Summary

| Phase | Name | Requirements | Dependencies |
|-------|------|-------------|--------------|
| 1 | Component Decisions & Procurement | PROC-01, PROC-02 | None |
| 2 | RK61 Disassembly & Measurement | PROC-03 | None |
| 3 | Enclosure CAD Design | ENCL-01–06 | Phase 2 |
| 4 | 3D Printing & Test Fit | ENCL-07 | Phase 3 |
| 5 | Electrical Design & Wiring | ELEC-01–07 | Phase 1 |
| 6 | Physical Assembly | DISP, KEYB, AUDI, COOL | Phase 4, 5 |
| 7 | Software & UI | SOFT-01–06, AUDI-05 | Phase 6 |
| 8 | Finishing & Weathering | FNSH-01–03 | Phase 7 |

**Parallelizable:** Phases 1 and 2 can run in parallel. Phase 5 can start once Phase 1 completes (doesn't need Phase 4).

---
*Roadmap created: 2026-02-19*
*Last updated: 2026-02-19 after initial definition*
