# Requirements: Fallout Pi Terminal

**Defined:** 2026-02-19
**Core Value:** A tactile, fully-functional retro-futurist terminal that feels like real Fallout equipment.

## v1 Requirements

Requirements for initial build. Each maps to roadmap phases.

### Decisions & Procurement

- [ ] **PROC-01**: All outstanding component decisions finalized (switches, speaker, DAC, LED assignments, button functions, E-stop position)
- [ ] **PROC-02**: Remaining components purchased (speaker, USB-C cable, USB DAC, wiring supplies)
- [ ] **PROC-03**: RK61 disassembled and bare PCB dimensions measured and documented

### Enclosure

- [ ] **ENCL-01**: CAD model designed for 7" display cutout (164.4x99.3mm)
- [ ] **ENCL-02**: CAD model includes RK61 bare PCB cavity (dimensions from PROC-03)
- [ ] **ENCL-03**: Panel-mount holes for all controls (3x 8mm LEDs, 2x buttons, 1x pot, 1x amp knob, 1x 22mm E-stop)
- [ ] **ENCL-04**: Internal volume accommodates Pi 4B, SSD + bracket, driver board, CTP board, amp board, fan, wiring
- [ ] **ENCL-05**: Rear/side ventilation for Noctua 40mm fan
- [ ] **ENCL-06**: Disassembly access maintained (screw construction, no glue)
- [ ] **ENCL-07**: Enclosure 3D printed and all components test-fit

### Electrical

- [ ] **ELEC-01**: 5V rail powers Pi via USB-C PSU
- [ ] **ELEC-02**: 12V rail powers LEDs and accessories via 12V 5A PSU
- [ ] **ELEC-03**: E-stop wired as master power control (NC contact cuts power, NO triggers GPIO soft shutdown)
- [ ] **ELEC-04**: 3x 12V 8mm LEDs wired to 12V rail and functional
- [ ] **ELEC-05**: 2x momentary buttons wired to GPIO and functional
- [ ] **ELEC-06**: B10K potentiometer wired for fan speed control
- [ ] **ELEC-07**: All wiring routed cleanly with serviceable connectors

### Display

- [ ] **DISP-01**: 7" EP-0084 LCD panel mounted in enclosure, landscape orientation
- [ ] **DISP-02**: RTD2660H driver board mounted internally with HDMI to Pi
- [ ] **DISP-03**: Capacitive touch panel connected and working with Pi
- [ ] **DISP-04**: Display powered from appropriate rail (5V/9V/12V)

### Keyboard

- [ ] **KEYB-01**: RK61 bare PCB mounted in enclosure cavity
- [ ] **KEYB-02**: Bluetooth paired to Pi 4B and typing works
- [ ] **KEYB-03**: Always-on USB-C power cable routed internally
- [ ] **KEYB-04**: Keycaps and switches installed on bare PCB

### Audio

- [ ] **AUDI-01**: PAM8403 amp board mounted internally
- [ ] **AUDI-02**: Speaker mounted behind front vent/grille
- [ ] **AUDI-03**: USB DAC connected to Pi as audio output
- [ ] **AUDI-04**: Volume controlled via front-panel knob (PAM8403 onboard pot)
- [ ] **AUDI-05**: Ambient hum audio plays on boot

### Cooling

- [ ] **COOL-01**: Noctua 40mm fan mounted for case airflow
- [ ] **COOL-02**: Adhesive heatsinks applied to Pi chips
- [ ] **COOL-03**: Fan speed controllable via front-panel potentiometer

### Software

- [ ] **SOFT-01**: Pi boots from USB SSD (no SD card)
- [ ] **SOFT-02**: Fallout-style terminal UI loads on boot (green/amber text)
- [ ] **SOFT-03**: Boot animation plays Fallout-style startup sequence
- [ ] **SOFT-04**: Ambient audio loops continuously in background
- [ ] **SOFT-05**: System bleeps/feedback sounds on key events
- [ ] **SOFT-06**: GPIO script handles button inputs and LED status

### Finishing

- [ ] **FNSH-01**: Enclosure has Fallout-appropriate weathering/finish
- [ ] **FNSH-02**: Control labels applied (engraved or printed plates)
- [ ] **FNSH-03**: Internal cable management complete

## v2 Requirements

Deferred to future iterations. Tracked but not in current build.

### Enhancements

- **ENH-01**: Network terminal mode (SSH client with retro UI)
- **ENH-02**: Custom Fallout-themed boot splash (video)
- **ENH-03**: LED indicators driven dynamically by system state (CPU temp, network, disk)
- **ENH-04**: RGB keyboard lighting synced with terminal theme
- **ENH-05**: Sound effects library expansion (typing clicks, error buzzes)

## Out of Scope

| Feature | Reason |
|---------|--------|
| Battery power | Wall-powered only, dual PSU architecture committed |
| Wi-Fi server | Standalone terminal, not a network appliance |
| Pi 5 / NVMe | Using existing Pi 4B and SATA SSD |
| Full desktop environment | Terminal UI focus is core to Fallout aesthetic |
| Wireless audio | Physical amp + speaker, no Bluetooth audio |
| Custom PCB | Using off-the-shelf boards, no custom electronics |

## Traceability

| Requirement | Phase | Status |
|-------------|-------|--------|
| PROC-01 | Phase 1 | Pending |
| PROC-02 | Phase 1 | Pending |
| PROC-03 | Phase 2 | Pending |
| ENCL-01 | Phase 3 | Pending |
| ENCL-02 | Phase 3 | Pending |
| ENCL-03 | Phase 3 | Pending |
| ENCL-04 | Phase 3 | Pending |
| ENCL-05 | Phase 3 | Pending |
| ENCL-06 | Phase 3 | Pending |
| ENCL-07 | Phase 4 | Pending |
| ELEC-01 | Phase 5 | Pending |
| ELEC-02 | Phase 5 | Pending |
| ELEC-03 | Phase 5 | Pending |
| ELEC-04 | Phase 5 | Pending |
| ELEC-05 | Phase 5 | Pending |
| ELEC-06 | Phase 5 | Pending |
| ELEC-07 | Phase 5 | Pending |
| DISP-01 | Phase 6 | Pending |
| DISP-02 | Phase 6 | Pending |
| DISP-03 | Phase 6 | Pending |
| DISP-04 | Phase 6 | Pending |
| KEYB-01 | Phase 6 | Pending |
| KEYB-02 | Phase 6 | Pending |
| KEYB-03 | Phase 6 | Pending |
| KEYB-04 | Phase 6 | Pending |
| AUDI-01 | Phase 6 | Pending |
| AUDI-02 | Phase 6 | Pending |
| AUDI-03 | Phase 6 | Pending |
| AUDI-04 | Phase 6 | Pending |
| AUDI-05 | Phase 7 | Pending |
| COOL-01 | Phase 6 | Pending |
| COOL-02 | Phase 6 | Pending |
| COOL-03 | Phase 6 | Pending |
| SOFT-01 | Phase 7 | Pending |
| SOFT-02 | Phase 7 | Pending |
| SOFT-03 | Phase 7 | Pending |
| SOFT-04 | Phase 7 | Pending |
| SOFT-05 | Phase 7 | Pending |
| SOFT-06 | Phase 7 | Pending |
| FNSH-01 | Phase 8 | Pending |
| FNSH-02 | Phase 8 | Pending |
| FNSH-03 | Phase 8 | Pending |

**Coverage:**
- v1 requirements: 38 total
- Mapped to phases: 38
- Unmapped: 0 ✓

---
*Requirements defined: 2026-02-19*
*Last updated: 2026-02-19 after initial definition*
