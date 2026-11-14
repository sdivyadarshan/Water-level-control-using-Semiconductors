# System Architecture

## Block-level architecture

```text
Water in tank
    |
    v
Common / MID / FULL probes
    |
    v
BC547 transistor switching stages
    |
    v
5 V relay module control input
    |
    v
Relay contacts (COM / NO)
    |
    v
5 V DC water pump
```

## Block responsibilities

1. **Sensing:** Conductive probes detect whether water has reached the selected level.
2. **Signal conditioning and switching:** BC547 transistor stages respond to probe conditions and provide the control signal required by the relay module.
3. **Actuation:** The relay contacts connect or disconnect the pump's low-voltage supply.
4. **Power:** A suitable DC source supplies the control circuit and the pump. The pump supply must be rated for its load current.

## Semiconductor principle

A BJT can operate as a switch:
- **Cut-off:** base drive is insufficient; collector-emitter current is approximately off.
- **Saturation:** sufficient base drive allows the transistor to conduct strongly.

The exact logic polarity at the relay input depends on the relay module design. Confirm whether the input is active-LOW or active-HIGH on the actual board.

## Scope

This repository documents the discrete-transistor prototype. It is not a microcontroller architecture and has no firmware execution path.
