# Components and Hardware

## Bill of materials

| Component | Quantity / detail | Function |
|---|---:|---|
| BC547 NPN transistor | 2 | Semiconductor switching stages |
| 5 V relay module | 1 | Switches the pump supply |
| 5 V DC mini water pump | 1 | Pumps water |
| Water probes | 3 (common, MID, FULL) | Detect water-level contact |
| Resistors | As used in the tested circuit | Limit/base-bias and input conditioning |
| Breadboard | 1 | Solderless prototyping |
| Jumper wires | As required | Interconnections |
| 5 V DC supply | 1, current-rated for the load | Powers control and pump as appropriate |

The exact resistor values and final transistor connections should be transcribed from the working physical build. Do not infer missing values from this table.

## Component notes

### BC547
The BC547 is an NPN bipolar junction transistor. In this project, the transistor stages act as electronic switches. A small base current controls a larger collector-emitter current. The transistor can be driven toward cut-off (OFF) or saturation (ON), depending on the circuit bias.

Confirm the collector, base and emitter leads using the datasheet for the exact part/manufacturer before wiring. Do not rely on an unverified package orientation.

### Relay module
The relay module provides a low-voltage control input and isolated switch contacts. The module may use an active-LOW or active-HIGH input; verify its polarity on the actual board before connecting the transistor control stage.

For a normally-off pump arrangement, the pump supply is routed through COM and NO. The relay contact ratings must be suitable for the pump's DC voltage and current.

### Water probes
The prototype uses a common probe and two level probes labelled MID and FULL. Conductivity between immersed probes acts as the sensing signal. Probe readings depend on water quality, spacing, oxidation and contamination.

## Power requirements

The pump supply must support the pump's rated current and startup current. Do not assume a laptop USB port or a small USB adapter is adequate. Keep the pump current within the relay contact and wiring ratings. This prototype is intended for low-voltage DC only.
