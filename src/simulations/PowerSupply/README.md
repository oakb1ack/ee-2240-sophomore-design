# Multisim Simulation – Capacitor Discharge Delay Circuit

## Overview
This simulation shows how a capacitor can keep a circuit powered for a short time even after the main switch is turned off. The circuit uses a 9 V source, a switch, a 220 µF capacitor, and an LED with a 4.7 kΩ current-limiting resistor.

## Circuit Purpose
The purpose of this simulation is to observe the discharge behavior of the capacitor after the switch is opened. When the switch is closed, the capacitor charges close to 9 V. When the switch is opened, the battery is disconnected, but the capacitor still provides energy to the LED path.

Because of this, the LED does not turn off immediately. Instead, the capacitor voltage slowly decays until it reaches nearly 0 V, around a few millivolts, approximately 4 mV in the simulation.

## Components Used
- 9 V DC battery
- SPST switch
- 220 µF capacitor
- 4.7 kΩ resistor
- LED
- Oscilloscope
- Multimeter
- Ground reference

## How It Works
When the switch is closed, the capacitor charges from the 9 V battery. The LED turns on through the 4.7 kΩ resistor.

When the switch is opened, the battery is removed from the circuit, but the capacitor is still connected to the LED and resistor. The capacitor then discharges through the resistor and LED, which causes the voltage to decrease slowly instead of dropping instantly.

The approximate time constant is:

\[
\tau = RC
\]

\[
\tau = 4.7k\Omega \times 220\mu F \approx 1.03s
\]

This means the circuit takes several seconds to fully discharge.

## Simulation Result
The oscilloscope shows the capacitor voltage gradually falling after the switch is opened. The voltage eventually reaches close to 0 V, around 4 mV, which is small enough to consider the circuit fully discharged.

## Important Observation
This circuit does not turn off urgently because the capacitor continues to power the load after the switch is opened. For applications that require fast shutdown, this capacitor placement is not ideal.

## Possible Fixes
To make the circuit turn off faster:
- Add a bleeder resistor in parallel with the capacitor.
- Use a smaller capacitor value.
- Move the capacitor before the switch so it does not keep powering the load after shutdown.

## Conclusion
The simulation demonstrates that a large capacitor can delay shutdown by storing charge and slowly releasing it through the load. Even though the switch disconnects the battery, the capacitor keeps the LED path active until the voltage decays to nearly zero.