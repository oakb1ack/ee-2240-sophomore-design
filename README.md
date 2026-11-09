# EE 2240 · 1 W Audio Amplifier

A sophomore design project exploring a compact, 9 V audio amplifier inspired by the Noisy Cricket. This repository brings together circuit simulations, a KiCad PCB, and a parametric enclosure.

**Design target:** 1 W output. The repository does not yet establish measured output power, audio performance, or a verified enclosure fit.

[CAD & enclosure](src/cad/README.md) · [Circuit simulations](src/simulations/README.md) · [PCB & wiring](src/pcb/README.md)

## How the project fits together

The circuit takes an audio input through a JFET input stage, volume and tone controls, and an LM386 power amplifier to the speaker output. A switched 9 V supply powers the circuit and an indicator LED. Simulations explore individual stages; the PCB implements the circuit; the enclosure provides a starting point for packaging it.

![Provisional enclosure front and rear panel layout](src/cad/panel_layout.png)

*Enclosure concept: front controls and rear connections. Hole positions and hardware fit are provisional; the Grit cutout has no corresponding switch in the current PCB.*

## Repository map

```text
.
├── README.md                       Project overview and navigation
└── src/
    ├── cad/                        Enclosure source, solids, and print meshes
    │   ├── model.py                Parametric CadQuery model
    │   ├── *.step / *.stl          CAD exchange and printable parts
    │   └── README.md               Dimensions, assembly, and fit checks
    ├── simulations/                Multisim circuits and saved results
    │   ├── NoisyCricket/           Complete-circuit study
    │   ├── PreampStage/            Input-stage study
    │   ├── ToneVolumeControl/      Control sweeps
    │   ├── PowerSupply/            Power-switch study
    │   ├── PowerampBypass/         Filter-on / filter-off comparison
    │   ├── deprecatedBuild/        Earlier circuit experiments
    │   └── README.md               Model and result guide
    └── pcb/                        KiCad project, schematic, and layout
        ├── SophomoreProjPCBdesign.kicad_pro
        ├── SophomoreProjPCBdesign.kicad_sch
        ├── SophomoreProjPCBdesign.kicad_pcb
        └── README.md               Circuit, connections, and board details
```

## Start here

| Task | Tool / files | Guide |
| --- | --- | --- |
| Understand circuit behavior | Multisim 14-format `.ms14` models and saved results | [Simulations](src/simulations/README.md) |
| Inspect the schematic or board | KiCad 10.0 or a compatible newer version | [PCB](src/pcb/README.md) |
| Review enclosure geometry | STEP-capable CAD viewer or STL viewer | [CAD](src/cad/README.md) |
| Change enclosure dimensions | Python with CadQuery; edit `model.py` | [Regeneration](src/cad/README.md#edit-and-regenerate) |

Start with the subsystem guide before editing its source files. Keep simulation settings with any new results, regenerate CAD exports after model changes, and update documentation images when the corresponding design changes.

## Current integration work

- Verify circuit behavior and output power with the intended supply and speaker load.
- Review electrical and layout checks before producing fabrication files.
- Reconcile the enclosure with the PCB outline, control spacing, and actual component heights. The enclosure has no PCB standoffs yet.

See the subsystem guides for specific assumptions and the files needed to continue each task.
