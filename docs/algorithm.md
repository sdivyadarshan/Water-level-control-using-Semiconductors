# Operating Algorithm and Control Logic

## Intended sequence

1. Monitor the water-contact condition at the common, MID and FULL probes.
2. When the water reaches the configured low/start level, the transistor control circuit changes state to request pumping.
3. The relay module switches its contacts and supplies power to the pump.
4. As the tank fills and water reaches the FULL probe, the full-level control condition requests pump shut-off.
5. The relay releases and disconnects the pump through the normally-open contact path.
6. The system waits for the water level to fall before the next start condition.

## Logic implementation

Unlike a software controller, this prototype does not execute a loop or run an Arduino sketch. Its response is determined continuously by:
- electrical conductivity between the probes;
- transistor base bias and switching thresholds;
- the interconnection of the two BC547 stages;
- the relay module's input polarity and internal driver circuit.

## Important implementation qualification

The intended functional behaviour is low-level start and full-level stop. The exact transistor-level truth table, including whether the circuit has a true hold/latch state between MID and FULL, must be derived from the final verified schematic. It is not safe to infer that truth table from the component list alone.

For a complete engineering record, add a truth table with measured relay state for:
- water below MID;
- water touching MID only;
- water touching FULL;
- falling water after the FULL condition;
- probe disconnected / open-circuit condition.

Record actual observations rather than assuming ideal behaviour.
