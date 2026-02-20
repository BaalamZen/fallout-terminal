# Fallout Pi Terminal

## What This Is

A functional Fallout-inspired desktop terminal built around a Raspberry Pi 4B, featuring a 7" touchscreen display, RK61 mechanical keyboard (bare PCB, Bluetooth), physical controls (knobs, LEDs, buttons, E-stop), ambient audio system, and a custom 3D-printed industrial enclosure. Being built as a gift for Ian.

## Core Value

A tactile, fully-functional retro-futurist terminal that feels like real Fallout equipment — physical controls over touch, audible machine hum, visible hardware, and a compact mechanical keyboard.

## Requirements

### Validated

(None yet — build to validate)

### Active

- [ ] 7" display (EP-0084) mounted in custom enclosure, landscape, working touch
- [ ] RK61 bare PCB integrated, Bluetooth to Pi, always-on USB-C power
- [ ] Physical controls: 2 knobs, 3 LEDs, 2 buttons, 1 E-stop
- [ ] Dual power rails: 5V (Pi) + 12V (LEDs/accessories)
- [ ] Audio: ambient hum + system bleeps via PAM8403 amp + speaker
- [ ] SSD boot via USB 3.0 (no SD card)
- [ ] Noctua 40mm fan cooling with front-panel knob control
- [ ] Fallout-style terminal UI (green/amber text, boot animations)
- [ ] Custom 3D-printed enclosure redesigned for 7" screen + RK61

### Out of Scope

- Wi-Fi/network server functionality — this is a standalone terminal
- Multi-user OS — single-user terminal experience
- Pi 5 / NVMe — using existing Pi 4B and SATA SSD
- Battery power — wall-powered only (dual PSU)
- Full desktop environment — terminal UI focus

## Context

- Original STL files are from a Thingiverse remix (michaave, thing:3820304) designed for a 3.5" Adafruit TFT — they cannot be used as-is
- The 7" EP-0084 display kit includes a separate driver board (RTD2660H, 90.6x65.6mm) that needs internal mounting space
- RK61 bare PCB dimensions are unknown until disassembly (4x M2 screws, ~285x98mm with case)
- BOM v12 is the source of truth for purchased components
- Most components already purchased — see master file for full BOM
- 10 outstanding decisions remain (switches, speaker, DAC, fan control, power logic, LED assignments, button functions, E-stop position, CAD tool, PCB measurements)

## Constraints

- **Components:** Most already purchased — build around what's owned, don't redesign for different parts
- **Display Size:** 7" EP-0084 kit is fixed — enclosure must accommodate 164.4x99.3mm panel + driver board
- **Keyboard:** RK61 purchased — bare PCB installation is committed
- **Aesthetic:** Industrial Fallout look — visible screws, metal/bakelite textures, no glossy modern plastics
- **Power:** Dual-rail (5V + 12V) architecture is committed
- **Serviceability:** Must maintain disassembly access — no glue traps, screwed construction

## Key Decisions

| Decision | Rationale | Outcome |
|----------|-----------|---------|
| RK61 over GK64X | RK61 already purchased, Bluetooth 5.0, 60% layout fits | ✓ Good |
| 7" over 3.5" display | Much better usability for terminal UI | ✓ Good |
| Bare PCB keyboard install | Saves height, fits industrial aesthetic | — Pending |
| Bluetooth keyboard connection | Eliminates internal USB routing complexity | — Pending |
| Always-on USB-C for RK61 | Avoids battery management, keyboard always ready | — Pending |
| Dual power rails (5V+12V) | Clean separation, 12V LEDs don't share Pi rail | — Pending |
| USB SSD boot (no SD) | Faster, more reliable, better for Fallout OS | ✓ Good |
| USB Audio DAC required | Pi analog output too noisy for ambient hum | — Pending |

---
*Last updated: 2026-02-19 after initial project definition*
