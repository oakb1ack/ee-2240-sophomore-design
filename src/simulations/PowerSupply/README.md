# Power supply simulation

[Simulation guide](../README.md) · [Project overview](../../../README.md)

The [Multisim model](powerstage.ms14) explores a 9 V supply, switch, capacitor, and LED path. Open it in a version of NI Multisim that supports `.ms14` files to inspect the circuit and probe connections.

The [saved results](Results/) include switch-open and switch-closed oscilloscope exports. In the saved traces, connected Channel A is approximately 4.09 mV for the open case and 9 V for the closed case. These are separate saved cases; they do not by themselves show the voltage decay after opening the switch. Confirm the probe location, initial conditions, and switch operation in the model before drawing conclusions about discharge time.

To study shutdown, start with the capacitor charged, open the switch during the simulation, and record the voltage over time along with the circuit and instrument settings. A simple RC time constant is only an approximation when the discharge path includes an LED.
