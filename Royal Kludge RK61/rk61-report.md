There doesn’t appear to be an official, public mechanical drawing pack for the RK61 (no factory DXF/STEP with hole coordinates), but you can get most of what you want from a mix of Royal Kludge specs, a community PCB repo, and several 3D models/cases built around the original board.[web:4][web:7][web:8][web:3][web:6][web:15][web:23]

Below is what’s actually available and how to use it to recover dimensions, mounting holes, and 3D geometry.

---

## Main technical resources

| Purpose | Resource | What you get | Format / notes |
| --- | --- | --- | --- |
| Exterior dimensions | RK61 official product pages | Overall keyboard dimensions and weight | 292 × 102 × 39 mm, ~0.5 kg.[web:4][web:7][web:10][web:13] |
| PCB / hole layout | 0xYuzko/RK61‑PCB GitHub repo | Full PCB layout and Gerber set for the RK61 PCB | Protel/Altium‑origin PCB converted to KiCad; Gerbers for CAM and mechanical extraction.[web:8] |
| Replacement base (drop‑in) | “RK61 Keyboard base” – Printables | STL for a complete replacement bottom base designed around a real RK61 | Base geometry and mounting features that match the stock board.[web:3] |
| Alternative case | “Rk61 case” – Printables | Another user‑created RK61 case model | STL case with RK61 fitment.[web:6] |
| Back case | “RK61 Keyboard Back case” – Thingiverse | Slimmer replacement back shell for RK61 | STL back case shaped for original PCB/plate.[web:15] |
| Full visual 3D model | “RK61 60 Wireless Mechanical Keyboard” – CGTrader | High‑poly exterior model of the entire keyboard | OBJ/FBX/BLEND for rendering/visual design (not guaranteed to be engineering‑grade).[web:23] |
| Physical reference for screws | RK61 teardown / mod videos | Visual confirmation of screw count, locations, and stack‑up | Disassembly and mod guides on YouTube.[web:2][web:18] |

---

## Official overall dimensions

Royal Kludge’s own store pages list the RK61 as having dimensions of 292 × 102 × 39 mm and a weight of about 0.5 kg.[web:4][web:7][web:10][web:13]  
Some variants/pages also show the same dimensions in inches (about 11.4 × 4 × 1.5 in), which lines up with the metric spec.[web:1][web:4]

For external enclosure or desk‑cutout design, you can usually treat the footprint as roughly 292 × 102 mm, plus whatever clearance you want around the shell.

---

## PCB layout and (implicit) schematics

The most useful “technical” artifact is the community RK61 PCB repo:

- Repo: **0xYuzko/RK61‑PCB** on GitHub.[web:8]  
- Contents include:
  - Gerber files for the PCB.
  - A converted KiCad PCB file originating from the original Protel/Altium design.[web:8]

What this gives you:

- **Exact PCB outline and mounting holes**  
  Import the Gerbers into a CAM tool (e.g., KiCad, Altium, EasyEDA, or a viewer like gerbv) and you can read off board dimensions and drill coordinates directly (mounting bosses, screw holes, USB cut‑out, etc.).[web:8]

- **Electrical net layout / de‑facto schematic**  
  While the repo is described as “PCB and gerber files” and does not advertise a complete hand‑drawn schematic, you can infer the switch matrix, LED routing, and MCU pinout from the PCB nets and pads; the main IC is identified as an HFD1101KBA, apparently a Sonix SN32F248B‑class clone.[web:8]

If you need exact hole positions for a mount or tray, this PCB file is your best source: align your mechanical reference to the PCB outline and measure the drill locations in your EDA/CAD package.

---

## Community 3D models and how to use them

Several people have modeled replacement cases/bases specifically around a physical RK61, which effectively encodes the keyboard’s mechanical envelope and screw locations:

- **“RK61 Keyboard base” – Printables**  
  A user rebuilt the base after damaging the original and published the STL as a direct replacement.[web:3]  
  - Because it’s a drop‑in replacement, the interior bosses and screw posts should align with the stock RK61 PCB and top shell.
  - You can import the STL into Fusion 360, SolidWorks, FreeCAD, etc., re‑fit primitive geometry, and then pull precise dimensions for wall thickness, screw diameters, and internal clearances.

- **“Rk61 case” – Printables**  
  Another STL case simply labeled as an RK61 case.[web:6]  
  - Similarly, this model is intended to fit the RK61, so the interior volume and mounting interface encode the keyboard’s outer size and mounting features.

- **“RK61 Keyboard Back case” – Thingiverse**  
  A slimmer back case profile for an RK61, again meant to replace the factory back shell.[web:15]  
  - This is useful if you want a slightly different external profile but still compatible with stock mounting points.

- **CGTrader model**  
  The “RK61 60 Wireless Mechanical Keyboard” model on CGTrader provides exterior‑only geometry (OBJ/FBX/BLEND) useful for renders, ergonomic mockups, or collision checks with other objects.[web:23]  
  - Treat it as visually accurate but not necessarily dimensionally certified unless you verify against physical measurements or the PCB.

Between the PCB file and at least one of these base/case STLs, you can reconstruct a fully parametric model of the keyboard with mounting holes and shell geometry.

---

## Mounting hole positions and practical approach

Since Royal Kludge doesn’t publish a dedicated mechanical drawing with hole coordinates, the usual workflow to get production‑grade data is:

1. **Use the PCB file for hole data**  
   - Open the KiCad PCB from the RK61‑PCB repo.[web:8]  
   - Set the board origin to a convenient corner of the outline.
   - Read off drill diameters and (x, y) for each mounting hole and USB cut‑out from the PCB editor or drill report.

2. **Use a community base STL to validate stack‑up**  
   - Import “RK61 Keyboard base” (or similar) STL and overlay it with your reconstructed PCB outline in CAD to check that standoffs and walls line up where you expect.[web:3][web:6][web:15]

3. **Cross‑check visually with teardown videos**  
   - Disassembly/teardown videos show screw count and approximate locations in the plastic shell and how the PCB and plate sit inside it.[web:2][web:18]  
   - That’s useful sanity checking when you’re translating 2D PCB data into a 3D mount or chassis.

4. **If needed, reverse‑engineer from a physical board**  
   - For a truly tight tolerance design (e.g., CNC aluminum case), most builders still take caliper measurements from an actual RK61 and compare them with the CAD extracted from PCB/STL to adjust for any model inaccuracies.[web:22]

---

## Schematics availability

- I was not able to find an official Royal Kludge schematic PDF for the RK61 exposed publicly; only generic marketing specs are listed on RK’s own product pages.[web:4][web:7][web:10][web:13]
- The GitHub repo gives you PCB and firmware hex files (including a default firmware image), plus identification of the MCU family, which is usually enough for reverse‑engineering the matrix and controller if you need to do firmware or hardware mods.[web:8]

If you tell me which CAD/EDA stack you’re using (KiCad, Fusion, SolidWorks, etc.) and what exactly you’re designing (tray, full custom case, mounting bracket, etc.), I can outline concrete import/export steps to get from these files to clean parametric models with all the mounting holes you need.
