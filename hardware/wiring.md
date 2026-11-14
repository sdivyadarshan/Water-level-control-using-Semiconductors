# Wiring and Connection Documentation

## Functional connections

The tested prototype contains these functional blocks:

| Block | Elements | Purpose |
|---|---|---|
| Level sensing | Common, MID and FULL probes | Detect water contact at the selected levels |
| Semiconductor control | Two BC547 NPN transistors and bias resistors | Convert probe conditions into switching control |
| Relay interface | 5 V relay module (VCC, GND, IN) | Controls the pump power path |
| Load | 5 V DC pump through relay COM/NO contacts | Moves water into the tank |
| Supply | Low-voltage 5 V DC source(s) | Powers control and pump |

## Relay contact labels

The relay screw-terminal labels on the module correspond to:

- 常开 — NO (normally open)
- 公共端 — COM (common)
- 常闭 — NC (normally closed)

For a pump that should be off while the relay is de-energized, the switched pump supply is normally routed through COM and NO. Confirm the module's printed labels and contact ratings.

## Control-side pins

The relay module control header is labelled VCC, GND and IN. Use the module's own documentation to confirm its input polarity and required supply. Many relay modules are active-LOW, but this must be tested rather than assumed.

The controller and relay module must share a reference ground when the transistor stage drives the module input, unless the actual interface design provides isolation.

## Final-build wiring record

The project was brought to working operation during breadboard troubleshooting. However, the conversation record does not provide a reliable final pin-by-pin wiring map or a verified schematic. To avoid publishing an incorrect circuit, this document records the functional connections only.

**Before using this file as a build guide:** add a clear, top-down photograph of the working breadboard and a hand-checked schematic. Record for each BC547 its verified C, B and E connections, each resistor value, relay input polarity, supply rails and pump contact path.

## Important precautions

- Disconnect power before changing breadboard wiring.
- Never connect mains voltage to the breadboard.
- Do not drive a BC547 base directly from a probe without a current-limiting resistor.
- Confirm transistor pinout from the exact part datasheet.
- Check that the pump supply and relay contacts are rated for the pump's current.
- If the relay is a module, it may already include a flyback diode and driver circuitry; inspect the board before adding components externally.
