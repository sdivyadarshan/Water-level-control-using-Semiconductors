# Design Decisions and Engineering Notes

## 1. Discrete semiconductor control
The project uses BC547 NPN transistors rather than a microcontroller. This keeps the implementation focused on semiconductor switching and makes BJT cut-off and saturation directly relevant to the operation.

## 2. Probe-based level detection
Three probes (common, MID and FULL) are used to detect water contact at selected heights. This is inexpensive and easy to demonstrate, but it depends on water conductivity and probe condition.

## 3. Relay-based pump switching
A 5 V relay module is used to switch the pump supply. The transistor sensing/control circuit does not need to carry the pump motor current directly. COM and NO are used for a normally-off load path, subject to verification against the module's markings and ratings.

## 4. Breadboard prototyping
The circuit was assembled on a breadboard without soldering. This supports quick changes during development, but loose contacts and shared supply-rail limitations can affect reliability.

## 5. Low-voltage DC operation
A 5 V DC pump was selected for the prototype. The supply must still be rated for the pump's operating and startup current.

## 6. No firmware
The implemented version is a transistor circuit, not an Arduino project. No sketch is included so that the repository accurately represents the actual build.

## Changes and troubleshooting
The circuit was iteratively adjusted during testing, including investigation of relay-module input polarity and transistor switching behaviour. The final verified node-by-node wiring and exact resistor values should be added from the physical working prototype rather than reconstructed from incomplete notes.
