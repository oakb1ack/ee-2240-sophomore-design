# EE 2240 Amplifier PCB

KiCad schematic and PCB layout for the EE 2240 sophomore design amplifier project. The circuit uses a 9 V supply, an N-channel JFET preamplifier, and an LM386 audio amplifier, with volume, tone, and gain controls.

The overall project targets a 1 W amplifier. Output power and audio performance have not been verified by this documentation.

## Project files

| File | Purpose |
| --- | --- |
| [SophomoreProjPCBdesign.kicad_pro](SophomoreProjPCBdesign.kicad_pro) | KiCad project and design settings |
| [SophomoreProjPCBdesign.kicad_sch](SophomoreProjPCBdesign.kicad_sch) | Circuit schematic |
| [SophomoreProjPCBdesign.kicad_pcb](SophomoreProjPCBdesign.kicad_pcb) | Component placement, copper routing, and board outline |
| `SophomoreProjPCBdesign.kicad_prl` | Local KiCad editor preferences |

## Opening the design

The PCB file was saved with **KiCad 10.0**. Use KiCad 10.0 or a compatible newer version.

1. Open `SophomoreProjPCBdesign.kicad_pro` in the KiCad project manager.
2. Open the schematic editor to inspect the circuit and component values.
3. Open the PCB editor to inspect placement, routing, and the ground zone.
4. Use the 3D Viewer to review component orientation and mechanical clearance. Model availability depends on the installed KiCad libraries.

The assigned footprints use standard KiCad libraries. Most components are through-hole; U1 uses an SOIC-8 surface-mount footprint.

## Circuit and controls

| Reference | Component or function |
| --- | --- |
| Q1 | N-channel JFET preamp; schematic uses the generic `NJFET` symbol |
| U1 | LM386 audio amplifier, SOIC-8 |
| RV1 | Volume control, 10 kΩ |
| RV2 | Tone control, 1 kΩ |
| RV3 | Gain control, 100 kΩ |
| SW2 | External SPST power switch connection |
| D1 | Power indicator LED, 5 mm |

### External connections

The following assignments are taken from the current PCB pad nets. Pin numbers refer to footprint pads; confirm their physical orientation in KiCad before wiring.

| Connector | Function | Pin 1 | Pin 2 |
| --- | --- | --- | --- |
| J1 | Audio output | Output through C7 | Ground |
| J2 | Audio input | Q1 gate/input signal | Ground |
| J3 | DC power input | +9 V | Ground |
| SW2 | Power switch | +9 V input | Switched circuit supply |

J1 and J2 use two-pin, 2.54 mm headers for wiring external audio connectors, despite their `AudioJack2` schematic values. SW2 also uses a two-pin header for an external switch.

## Component values

These values describe the current design; this table is not a purchasing BOM with manufacturer part numbers.

| References | Value |
| --- | --- |
| R1 | 4.7 kΩ |
| R2 | 1 MΩ |
| R3 | 3.3 kΩ |
| R7 | 10 Ω |
| C1, C7 | 220 µF, polarized |
| C2, C8 | 47 nF |
| C3, C4 | 100 nF |

Check voltage ratings, resistor power ratings, and physical dimensions before ordering. Select a specific JFET for Q1 and verify its pinout against the assigned TO-92 inline footprint. Confirm the LM386 variant matches the SOIC-8 footprint and intended supply and load.

## Board layout

- Two copper layers: front and back.
- Configured board thickness: 1.6 mm, with an FR4 core.
- Rectangular Edge.Cuts outline: approximately **90.31 × 46.79 mm**.
- Routed tracks and a ground copper zone are present.
- Potentiometers use Alpha RD901F-40-00D single vertical footprints.

The enclosure files are documented in [../cad/README.md](../cad/README.md). Check enclosure fit against this PCB's actual outline, component heights, and control positions; the enclosure notes reference different provisional PCB dimensions.

## Before fabrication and assembly

This README records the source files; it does not establish that the board has passed electrical checks, fabrication checks, or bench testing.

1. Run the schematic Electrical Rules Checker (ERC) and review all findings.
2. Verify the PCB matches the schematic, refill copper zones, and run the PCB Design Rules Checker (DRC), including unconnected-item checks.
3. Check connector orientation, JFET pinout, LM386 pin 1, LED polarity, and electrolytic capacitor polarity.
4. Confirm footprint dimensions and enclosure clearances against the actual parts.
5. Export Gerber layers and drill files from the PCB editor, then inspect them in a Gerber viewer before ordering boards.
6. Before first power-up, check for supply-to-ground shorts. Use a current-limited 9 V supply and verify operating conditions before testing audio output with the intended load.

Fabrication exports, a manufacturer-specific BOM, and test results are not included in this directory.
