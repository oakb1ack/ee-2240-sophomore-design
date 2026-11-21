# EE 2240 · ½ W Guitar Amplifier

A sophomore design project for a compact, battery-powered guitar amplifier inspired by the Noisy Cricket Mk II. This repository contains the circuit studies, PCB design, enclosure concept, and selected photos from development.

## The project

The amplifier is designed to run from a 9 V supply and drive an 8 Ω speaker. The guitar signal passes through a JFET input stage, volume and tone controls, and an LM386 power amplifier. Gain and grit controls provide additional ways to shape the sound. The team explored the circuit in Multisim and on the bench, then developed a PCB and an enclosure concept.

The amplifier has a **½ W output power target**. The files here do not establish measured output power.

| Area | What is here | Guide |
| --- | --- | --- |
| Circuit studies | Multisim models and saved results for the complete circuit and individual stages | [Simulations](src/simulations/README.md) |
| Board | KiCad schematic, board layout, and supplied Gerber archive | [PCB](src/pcb/README.md) |
| Enclosure | Parametric CAD source, STEP solids, and STL meshes | [CAD](src/cad/README.md) |
| Breadboarding and testing | Selected photos from the project journal | [Breadboarding](docs/photos/README.md#breadboarding) · [Photo record](docs/photos/README.md) |

## Design and testing status

- The [PCB project](src/pcb/README.md) contains the updated board design. KiCad checks report schematic and parity findings that need review, and the supplied Gerber archive has not been verified against the current layout. The journal photos do not identify the board revision or test conditions.
- The enclosure is a **fit-check concept**. Its dimensions, control openings, and mounting must be checked against the actual board and hardware before use.
- Saved simulations and oscilloscope photos document work in progress. They do not by themselves verify output power, distortion, or final board performance.

## Explore the files

Open the board project in KiCad 10, and open the `.ms14` models in a compatible version of NI Multisim. The enclosure's STEP and STL files can be inspected in CAD and mesh viewers; [its guide](src/cad/README.md#edit-and-regenerate) explains how to regenerate them with CadQuery.

```text
src/
├── cad/          Enclosure model and exports
├── pcb/          KiCad project and supplied Gerber archive
└── simulations/  Circuit models and saved results
docs/photos/      Selected journal images
```

To continue the project, test the assembled circuit with a known supply and load, and adapt the enclosure to the actual hardware. Record the test conditions alongside any measurements.
