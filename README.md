# Transistor-Based Automatic Water Level Controller

A low-cost automatic water-level control prototype built with discrete semiconductor switching. The system uses water-level probes, BC547 NPN transistors and a 5 V relay module to control a 5 V DC water pump.

> **Implementation note:** This is a hardware-only transistor circuit. It does not use an Arduino, ESP32 or other programmable microcontroller, so there is no Arduino sketch or firmware in this repository.

## Project overview

The controller is intended to start water pumping when the water level reaches the low-level condition and stop the pump when the tank reaches the full-level condition. Conductive probes provide the level-sensing input; transistor stages provide the switching logic; and a relay module switches the pump supply.

The project demonstrates:
- BJT operation as an electronic switch (cut-off and saturation regions)
- Probe-based liquid-level detection
- Relay-based control of a DC load
- A practical application of semiconductor devices in water management

## Hardware used

- BC547 NPN transistors (2)
- 5 V relay module
- 5 V DC mini water pump
- Water-level probes (common, MID and FULL)
- Resistors for transistor biasing / input conditioning
- Breadboard and jumper wires
- 5 V DC supply

See [hardware/components.md](hardware/components.md) and [hardware/wiring.md](hardware/wiring.md) for the component list and wiring notes.

## Operating concept

1. The common probe and level probes form the water-contact sensing arrangement.
2. When the water reaches the configured start level, the transistor switching stage changes the relay input state.
3. The relay energizes and connects its COM and NO contacts, powering the pump.
4. When water reaches the FULL probe, the full-level control condition disables pumping.
5. The pump remains off until the water level falls and the start condition is reached again, according to the implemented circuit behaviour.

The actual relay module input polarity and the final transistor interconnections must be checked against the physical module and the tested build. See [docs/algorithm.md](docs/algorithm.md).

## Repository structure

```text
.
├── README.md
├── .gitignore
├── src/
│   └── README.md
├── hardware/
│   ├── components.md
│   └── wiring.md
├── docs/
│   ├── algorithm.md
│   ├── architecture.md
│   ├── design-decisions.md
│   └── testing.md
└── media/
    └── README.md
```

## Demonstration

**Demo video:** Not yet linked. Add the video URL in [media/README.md](media/README.md), then replace this line with the public video link.

**Project photographs:** Add clear photographs of the complete breadboard, probe arrangement and relay/pump connections in the `media/` directory.

## Safety and practical notes

- Use a low-voltage DC pump and an appropriately rated isolated DC supply.
- Do not connect mains voltage to the breadboard or this prototype.
- Check the pump's rated voltage and current before selecting its supply. A USB port may not be able to supply the pump's startup or running current.
- Keep the controller ground and relay-module ground common where required by the tested circuit.
- Verify the BC547 pinout from the exact manufacturer's datasheet; package pin order should not be assumed universally.
- Use a suitable base resistor for each transistor input. Do not connect a probe directly to a transistor base without current limiting.
- Water conductivity varies with mineral content, probe spacing and contamination. Treat this as an educational prototype, not a certified tank-safety controller.

## Contributions and AI-use disclosure

### Student contribution
- Project idea and selection of a real-world water-level control application.
- Physical breadboard assembly and component integration.
- Probe placement, pump/relay integration and hands-on testing.
- Observing and reporting circuit behaviour during troubleshooting.

### AI-assisted work
- Assistance with circuit troubleshooting and interpreting relay-module behaviour.
- Assistance organizing the project documentation, repository structure and technical explanations.
- No claim is made that AI generated or tested the physical hardware.

The physical implementation and test observations belong to the student. AI assistance is disclosed to distinguish support provided during development from hands-on work.

## Status

A working prototype was reported after iterative breadboard troubleshooting. The final wiring should be documented from a photograph of the working build before treating this repository as a definitive construction guide.

## License

No license file is included yet. Unless a license is added by the repository owner, the repository remains subject to the default copyright terms.
