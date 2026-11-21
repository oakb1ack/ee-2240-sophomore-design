# Noisy Cricket Mk II · Rev A

Editable KiCad 9 project for a 9 V guitar amplifier driving an 8 Ω load. Open `Noisy_Cricket_MkII.kicad_pro`. Keep `Cricket.pretty` and `fp-lib-table` beside the project so KiCad can find the local control footprints.

## Circuit and layout

- The circuit follows the beavis audio research Noisy Cricket Mk II build guide, rev 1.02. It retains the JFET source follower, LM386 inverting input, power indicator, volume, tone, adjustable gain, and grit switch. The guide swaps the gain and tone references in its parts list. This project uses its schematic designations, VR2 for 1 kΩ linear gain and VR3 for 100 kΩ linear tone.
- Q1 is the onsemi J113-D74Z in the lead-formed TO-92 package. Its three plated holes use 2.54 mm pitch. Pin 1 is drain, pin 2 source, and pin 3 gate. A straight-lead J113 would require lead forming to fit this land pattern.
- C9 is a 100 nF local bypass from U1 pin 6 to ground added alongside the guide’s C1 bulk capacitor. The specified U1 is LM386N-1/NOPB, as in the guide.
- The board keeps the guide’s 3.7 × 1.2 in outline (93.98 × 30.48 mm) and front control order. It uses two copper layers and four Ø3.2 mm mounting holes. J1–J3 are rear-facing screw terminals for off-board jack and power wiring. The leads, jacks, speaker, power source, enclosure, and hardware are separate from PCB assembly.

## Fabrication and assembly

| Item | Selection |
| --- | --- |
| PCB construction | Two-layer FR-4, 1.6 mm, 1 oz copper, routed rectangular outline |
| Process | Green solder mask, white silkscreen, lead-free HASL or ENIG |
| Design rules | 0.25 mm minimum track width, 0.20 mm net clearance, 0.40 mm copper-to-edge |
| Smallest used signal trace | 0.35 mm |
| Via | Ø0.70 mm pad, Ø0.30 mm finished drill |
| Drill outputs | Separate metric Excellon files for plated and non-plated holes |
| PCB assembly | 24 top-side through-hole parts |

Use `Manufacturing/Fabrication_Gerbers.zip` for bare board fabrication at either vendor. The archive contains both copper, both mask, both silk, outline, and drill files. The design uses through-hole assembly without a paste stencil.

For **PCBWay**, submit the Gerber archive with `Assembly_BOM.csv` and `Assembly_Drawing.pdf`. For **JLCPCB**, use the Gerber archive, `JLCPCB_BOM.csv`, and `JLCPCB_CPL.csv`. Give the assembler the assembly drawing and confirm the specific matched parts and orientations. The five front-panel controls have exact manufacturer part numbers and blank LCSC codes. Ask the assembler to quote sourcing or consignment for those controls. Parts availability, assembly acceptance, and lead times are confirmed at quote time.

The three pots use 2.5 mm pitch and the two switches use a different 2.54 mm lead pattern with two extra non-plated support holes. Match the specified variants. PCB-mounted switches and pots have different heights above the PCB. Use the actual parts or the manufacturers’ drawings to locate the enclosure holes.

## Verification and first article

The `Checks` folder contains the KiCad 9.0.2 ERC and DRC reports, including schematic parity. The netlist was also checked against the guide’s node connections and the J113 and LM386 datasheets. The PCB has not been built or bench-tested. With the first article, check the J113 source bias and verify output power before placing a full assembly order. Into an 8 Ω dummy load, 0.5 W corresponds to 2.00 V RMS. Record the onset of clipping and supply voltage with the measured power.

## References

- [onsemi J113 datasheet](https://www.onsemi.com/pdf/datasheet/mmbfj113-d.pdf) · [JLCPCB J113-D74Z listing](https://jlcpcb.com/partdetail/onsemi-J113D74Z/C900947)
- [TI LM386 datasheet](https://www.ti.com/lit/ds/symlink/lm386.pdf)
- [Taiwan Alpha RD901F-20 drawing](https://www.mouser.com/datasheet/3/140/1/RD901F.pdf) · [Dailywell 2A M6 drawing](https://www.mouser.com/catalog/specsheets/Dailywell_01132020_2A_Series.pdf)
- [JLCPCB fabrication capabilities](https://jlcpcb.com/capabilities/Capabilities) · [JLCPCB BOM and CPL requirements](https://jlcpcb.com/help/article/how-to-generate-bom-and-centroid-files-from-kicad-8)
- [PCBWay fabrication capabilities](https://www.pcbway.com/capabilities.html) · [PCBWay assembly file requirements](https://www.pcbway.com/helpcenter/pcb_assembly_ordering/What_files_are_requested_for_assembly_production_.html)
