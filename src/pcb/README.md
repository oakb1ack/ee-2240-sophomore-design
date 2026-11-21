# PCB

[Project overview](../../README.md) · [Simulations](../simulations/README.md) · [CAD](../cad/README.md)

This directory contains the updated amplifier PCB project. Open [pcb.kicad_pro](kicad/pcb.kicad_pro) in KiCad to edit the schematic and board layout.

The supplied [Gerber archive](kicad/Gerber-Files.zip) predates the current board file; its correspondence to the current design has not been verified. Generate and review fabrication files from the current board before manufacturing.

KiCad 10.0.8 checks found no unconnected pads or other board DRC violations, four extra footprint warnings in schematic parity, and two schematic ERC errors plus two library symbol mismatch warnings. Review these findings before fabrication.
