# Fallout Terminal

Physical hardware build: Fallout-inspired Raspberry Pi desktop terminal with 7" display, RK61 bare-PCB mechanical keyboard, physical controls (LEDs, buttons, E-stop, potentiometers), ambient audio, and custom 3D-printed enclosure. **Not a software project** — most work is BOM tracking, dimension reconciliation, enclosure CAD, and eventually firmware/Pi-side scripts.

## Source of truth

1. [fallout_pi_terminal_master.md](fallout_pi_terminal_master.md) — single source of truth for design intent, confirmed decisions, outstanding gaps, BOM, and shopping list.
2. [DIMENSIONS.md](DIMENSIONS.md) — every component's ISO/DIN dimensions + panel cutout data; drives the enclosure redesign.
3. [Fallout_Terminal_Build_BOM.csv](Fallout_Terminal_Build_BOM.csv) — authoritative parts list (~30 lines). Each row has In-Hand status.
4. [CHANGELOG.md](CHANGELOG.md) — dated record of every BOM / master / dimension update. Append here every time those three files change.

## Sync invariant — CRITICAL

`BOM CSV` ↔ `fallout_pi_terminal_master.md` ↔ `DIMENSIONS.md` must stay in sync. When a part is received, substituted, or added:

1. Update the CSV row (In Hand, specs)
2. Update the master file's status table / purchased sections
3. Update DIMENSIONS.md if dimensions differ from prior spec
4. Append a CHANGELOG entry with today's date

Never edit one without the others. The CHANGELOG shows this pattern — every entry touches at least the CSV + master together.

## Key subfolders

- [Display Screen/](Display%20Screen/) — CTP-5710 touch panel datasheet + RTD2660H driver board drawings
- [Royal Kludge RK61/](Royal%20Kludge%20RK61/) — RK61 keyboard teardown, PCB photos, mounting-hole extraction (community KiCad/Gerber in `RK61-PCB/`)
- [Terminal File 1/](Terminal%20File%201/), [Terminal File 2/](Terminal%20File%202/), [Terminal File 3/](Terminal%20File%203/) — original + remixed STL references for the enclosure redesign
- [Lights/](Lights/), [Screws/](Screws/) — component reference photos + BOM sheets

## Pi-side software (future)

- [addon.py](addon.py) — BlenderMCP addon for Blender ↔ Claude Code integration; used when modeling the custom enclosure
- [.mcp.json](.mcp.json) — MCP server config (currently Blender)

Future Pi-side code (boot sequence, LED animations, audio hum, E-stop handler, etc.) will land in this repo under its own subfolder.

## Wiki Knowledge Base

This project pulls from the shared Baalam Obsidian vault at `C:\Users\baala\Dev\baalam-obsidian`, accessed via the `obsidian-vault` MCP server (tools prefixed `mcp__obsidian-vault__*`). The vault holds cross-project knowledge — most of it is SaaS/commerce-oriented and won't apply here, but these pages are relevant:

**Project page:**
- `Projects/Fallout-Terminal.md` — status, focus, blockers (currently a stub — worth filling in as the build progresses)

**For Pi-side software / AI integration work:**
- `Agents/Claude-Code-Setup.md` — how Claude Code is configured across Baalam
- `Agents/Ollama-Models.md` — local model options (if we ever run a small model on the Pi)
- `Systems/Tailscale-NUC.md` — relevant if the Pi joins the Baalam Tailscale mesh

**Read order when a question spans projects:** `wiki/hot.md` → `wiki/index.md` → specific page.

**Skip:** the entire `wiki/stacks/`, `wiki/concepts/`, WhatsApp/commerce/LATAM content — not relevant to this build.

## When to write back to the vault

After major decisions that affect the build (dimension changes, BOM substitutions, enclosure redesign milestones), offer to update `Projects/Fallout-Terminal.md` in the vault. Don't auto-commit — ask first.