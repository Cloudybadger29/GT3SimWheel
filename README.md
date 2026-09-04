# Custom GT3 Sim Racing Steering Wheel

An engineering portfolio showcasing an end-to-end mechatronics design: custom CAD mechanical assembly, 3D printable modular enclosures and ergonomic grips, CNC-machined structural faceplate, integrated magnetic dual-paddle shifters with microswitches, and a custom diode-matrix carrier PCB designed for manual through-hole soldering.

---

## Project Overview

This project is a competition-grade **GT3 Sim Racing Wheel** engineered for PC sim racing platforms (iRacing, Assetto Corsa Competizione, rFactor 2).

The project is currently in the **detailed engineering and design verification phase**:
- **Mechanical Design (CAD)**: Conceptualized and surfaced initially in **Autodesk Fusion**, then transitioned to **Dassault Systèmes SolidWorks** for assembly modeling and to follow industry standards.
- **Manufacturing Strategy (Planned)**: Hybrid build pairing a rigid CNC-milled structural front plate with 3D-printed modular grips, rear electronics housing, and structural spacer components.
- **Electronics & ECAD (In Progress)**: Custom carrier backplane currently being laid out in **KiCad EDA** around an ATmega32U4 controller, integrating anti-ghosting switching diodes and through-hole solder pads planned for manual assembly.
- **Shifter Subassembly**: Dual-action magnetic paddle units driven by high-reliability Omron microswitches.

*Note: All components are currently modeled and verified in CAD/ECAD. Physical fabrication and component procurement will begin upon finalization and sign-off of the PCB layout.*

---

## Media & Renders

| Isometric Assembly | Exploded CAD View |
| :---: | :---: |
| <img src="docs/images/wheel_front_iso.jpg" alt="Front Isometric View" width="420"/> | <img src="docs/images/wheel_exploded.jpg" alt="Exploded CAD Assembly" width="420"/> |

| Rear & Paddle Assembly | Custom PCB Carrier (KiCad 3D) |
| :---: | :---: |
| <img src="docs/images/wheel_rear_paddles.jpg" alt="Rear View with Shifters" width="420"/> | <img src="docs/images/pcb_3d_render.png" alt="KiCad PCB 3D Render" width="420"/> |

---

## Key Engineering Specifications

### 1. Mechanical Architecture & Manufacturing
- **CNC Structural Faceplate**: A rigid custom CNC-machined front plate designed to withstand high force-feedback torque loads from direct-drive wheelbases without chassis deflection.
- **Additive Manufacturing (3D Printing)**: All secondary enclosures, grip bodies, and mounting spacers are engineered for 3D printing.
- **Two-Piece Modular Grips**: Split-shell ergonomic hand grips contour to standard racing gloves and bolt securely through the faceplate using countersunk M5 hardware.
- **Standard Hub Pattern**: Integrated 70mm / 50.8mm bolt pattern allowing direct fitment to standard sim racing quick-release hubs.

### 2. Dual-Paddle Magnetic Shifters
- **Actuation**: Integrated 8×3mm neodymium magnets deliver crisp, tactile snap-action return.
- **Sensors**: Sourced **Omron D2FC-F-7N** microswitches rated for high-cycle reliability and responsive shift registration.
- **Dual-Paddle Geometry**: Upper and lower paddles allow independent assignment (gear up/down plus secondary functions such as DRS, pit limiter, or clutch bite point).

### 3. PCB & Electrical Architecture (In Design)
- **ECAD Tool**: Schematic capture and board layout in **KiCad EDA**.
- **Microcontroller**: Arduino Pro Micro footprint (ATmega32U4, 5V/16MHz) for native USB HID gamepad capabilities.
- **Assembly Plan**: Through-hole layout designed for precision hand soldering, featuring clearly labeled reference silk screens for components and leaded DO-35 diodes.
- **Ghosting-Free Diode Matrix**: Fast-switching 1N4148 diodes isolate each switch input to prevent crosstalk during simultaneous multi-button presses.
- **Inputs Supported**:
  - 10x PBS-33B momentary pushbuttons
  - 4x Omron D2FC-F-7N paddle microswitches
  - 2x KY-040 rotary encoders (for in-race TC, ABS, or brake-bias trim)
- **Central Pass-Through**: Custom clearance holes routed into the PCB matching the 70mm PCD wheelbase bolt circle.

---

## Exploded Assembly Breakdown

The mechanical stack consists of:
1. **Front Split Grips**: Ergonomically shaped front halves fastened with countersunk M5 bolts.
2. **Faceplate Controls**: 10x PBS-33B pushbuttons and 2x KY-040 rotary encoder shafts.
3. **CNC Front Faceplate**: Central load-bearing chassis with countersunk and clearance bores.
4. **Rear Split Grips**: Rear grip shells with internal captive nut pockets.
5. **Back Housing & Spacer**: Houses the custom KiCad PCB and internal wiring harness.
6. **Dual Paddle Units**: Dual magnetic microswitch shifters bolted to the rear plate using M2.5/M2 hardware.

---

## Planned Bill of Materials (BOM)

### Fasteners & Hardware

| Category | Type | Specification | Length | Qty | Target Application |
| :--- | :--- | :---: | :---: | :---: | :--- |
| **Screw** | Countersunk | M5 | 35mm | 10 | Main grip retention / faceplate clamp |
| **Screw** | Countersunk | M5 | TBD | 6 | Quick-release / hub mounting |
| **Screw** | Socket Head / Regular | M5 | 22mm | 8 | Main enclosure assembly |
| **Screw** | Socket Head / Regular | M3 | 50mm | 2 | Paddle shifter pivots |
| **Screw** | Socket Head / Regular | M2.5 | 12mm | 8 | Shifter bracket mounts |
| **Screw** | Socket Head / Regular | M2.5 | 10mm | 8 | Shifter brackets |
| **Screw** | Socket Head / Regular | M2 | 10mm | 8 | Omron microswitch mounts |
| **Nut** | Standard Hex / Lock | M5 | — | 24 | M5 screw fastening |
| **Nut** | Standard Hex / Lock | M3 | — | 2 | M3 screw fastening |
| **Nut** | Standard Hex / Lock | M2.5 | — | 16 | M2.5 screw fastening |
| **Nut** | Standard Hex / Lock | M2 | — | 8 | M2 microswitch retention |

### Electronics, Switches & Custom Parts

| Component | Part / Spec | Qty | Notes / Sourcing |
| :--- | :---: | :---: | :--- |
| **Structural Faceplate** | Custom CNC'd front plate | 1 | CNC milled (Aluminum / Carbon Fiber) |
| **Enclosures & Grips** | 3D Printed Components | — | Additive manufacturing (PETG / PLA) |
| **Custom Carrier PCB** | KiCad 2-layer custom board | 1 | In design; planned for manual hand-soldering |
| **Microcontroller** | Arduino Pro Micro (ATmega32U4) | 1 | 5V / 16MHz native USB HID |
| **Tactile Buttons** | PBS-33B Momentary Switches | 10 | Faceplate controls |
| **Shifter Switches** | Omron D2FC-F-7N Microswitches | 4 | Paddle shifter actuation |
| **Rotary Encoders** | KY-040 Encoders | 2 | Real-time ABS / TC / Brake Bias tuning |
| **Magnets** | N52 Neodymium Discs | 4 | 8×3mm magnetic snap return for shifters |
| **Switching Diodes** | 1N4148 DO-35 | 14+ | Matrix anti-ghosting |

---

## Engineering Status & Next Steps

- [x] Mechanical 3D CAD modeling & assembly (Fusion ➔ SolidWorks for industry-standard workflow)
- [ ] Complete routing, silkscreen, and design rule checks (DRC) on the KiCad PCB
- [ ] Order custom PCB prototype batch and procure BOM components
- [ ] 3D print grip shells, rear electronics housing, and internal spacers
- [ ] CNC machine the structural faceplate
- [ ] Hand-solder PCB components (Pro Micro, diodes, wiring headers)
- [ ] Develop and test USB HID gamepad firmware for ATmega32U4
- [ ] Assembly, calibration, and on-track testing in sim racing titles

---

## Tools & Environments Used

- **Mechanical CAD**: Autodesk Fusion (initial concepting & surfacing) ➔ Dassault Systèmes SolidWorks (assembly & industry standards)
- **ECAD / PCB Layout**: KiCad EDA

---

## Author & Contact

- **Designer & Builder**: [Zeeshan Ahmed]((https://github.com/Cloudybadger29))
- **Project Repository**: [GitHub Repo Link](https://github.com/Cloudybadger29/GT3SimWheel)
- **Double Paddle Shifter Designer**:[Joshua van der Voort](https://www.printables.com/@JoshuavanderV_932900)
