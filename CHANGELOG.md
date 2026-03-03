# Changelog

## 2026-03-03

### Changed
- **Fallout_Terminal_Build_BOM.csv** — Marked all 10 Accu fastener items as received (In Hand: Yes): M3 screws (6/8/10/12mm), M3 washers, M3 hex nuts, M3 nylon lock nuts, M2.5 screws (6/8mm), M2.5 hex spacers
- **fallout_pi_terminal_master.md** — Moved fasteners from "To Buy" to "Already Purchased"; added fasteners row to status table; marked PAM8403 amp as received; moved USB-C cable from "To Buy" to "Already Purchased"
- **Fallout_Terminal_Build_BOM.csv** — Added short USB-C to USB-C cable as new BOM line (In Hand: Yes); marked PAM8403 XF0172 as received with updated specs; updated 16mm power button (Adafruit green latching, in hand, role: system armed switch); updated LED indicators (5 colors: green/white/blue/amber/red, assignments TBD); BOM now 30 parts
- **fallout_pi_terminal_master.md** — Confirmed power switch logic (16mm latching = armed, BTN1 = soft shutdown, E-stop = emergency); updated front panel to 5 LEDs + power button; resolved outstanding decisions #3/#4/#5; LED color assignments left open

## 2026-02-24

### Added
- **Screws/BOM-screws.pdf** — Fastener BOM with images: M3 socket caps (6/8/10/12mm), M2.5 socket caps (6/8mm), M2.5 hex spacers, M3 washers, hex nuts, nylon lock nuts (all Accu)
- **Lights/Indicator Lights/** — LED rocker switch / illuminated power switch reference page

### Changed
- **Fallout_Terminal_Build_BOM.csv** — Added 10 fastener line items from screws BOM (M3 & M2.5 screws, washers, nuts, spacers); master BOM now 29 parts
- **DIMENSIONS.md** — Added Section 10 (Fasteners) with full ISO/DIN dimensions for all 10 fastener items + hex key reference table; updated parts readiness checklist to 12/19 confirmed

## 2026-02-23

### Added
- **DIMENSIONS.md** — Full dimension tracker for all BOM components with parts readiness checklist, panel cutout summary, and behind-panel depth reference
- **Display Screen/** — CTP-5710 touch panel datasheet, RTD2660H driver board outline drawing, screen dimension PDFs
- **Lights/Indicator Lights/** — 8mm LED indicator reference photos (mounting hole diameter, lead length, product photo)
- **Lights/On Button/** — 16mm metal LED push button technical drawing with full dimensions + product listing
- **Royal Kludge RK61/** — User manual pages, PCB teardown photos (layout, chips, markings, profile), RK61.pdf, ROYAL-KLUDGE-RK61 manual PDF, rk61-report.md research notes
- **Royal Kludge RK61/RK61-PCB/** — Cloned community PCB repo (KiCad + Gerber files + firmware hex) for mounting hole extraction
- **Terminal File 1/** — Original Fallout terminal 3D model (.3mf + PDF)
- **Terminal File 2/** — Thingiverse remix by michaave (Pi 4B compatible, STLs + images + README)
- **Terminal File 3/** — 9 individual STL parts (body, front inserts, back vent, keyboard tray, knob, screen holder, screen trim)
- **addon.py** — BlenderMCP addon for Blender-to-Claude integration (3D modeling assist)
- **.mcp.json** — MCP server config (Blender)

### Changed
- **Fallout_Terminal_Build_BOM.csv** — Renamed from `_v12`, added 16mm Metal LED Push Button Switch (power on/off) as new BOM line