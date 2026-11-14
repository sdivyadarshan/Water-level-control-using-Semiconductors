# Testing Checklist and Observations

## Pre-power checks

- [ ] Confirm BC547 part markings and verify C/B/E pinout from its datasheet.
- [ ] Check every transistor base has suitable current limiting.
- [ ] Verify resistor values against the final schematic.
- [ ] Confirm relay-module VCC, GND and IN labels.
- [ ] Determine whether relay IN is active-LOW or active-HIGH.
- [ ] Confirm COM/NO contact path and relay DC contact rating.
- [ ] Confirm pump voltage and current requirements.
- [ ] Check the 5 V supply can support the pump's startup current.
- [ ] Check for accidental shorts across breadboard rails.

## Functional tests

- [ ] Power the controller with the pump disconnected and verify the relay's default state.
- [ ] Test the relay control input independently to establish its active polarity.
- [ ] Test the MID probe condition and record relay state.
- [ ] Test the FULL probe condition and confirm pump shut-off behaviour.
- [ ] Repeat the fill-and-stop cycle at least five times.
- [ ] Observe whether the relay chatters when water just touches a probe.
- [ ] Test with the actual water source and record any conductivity-related variation.
- [ ] Check that the pump starts reliably and stops completely.
- [ ] Check wiring and component temperature during repeated operation.

## Observation record

| Test | Expected behaviour | Actual observation |
|---|---|---|
| Below start level | Pump remains in the designed idle state | To be recorded |
| MID/start condition | Pump start request | To be recorded |
| FULL condition | Pump stops | To be recorded |
| Falling water level | Controller returns to its start/wait behaviour | To be recorded |
| Repeated cycles | Consistent switching without chatter | To be recorded |

## Known validation status

The builder reported that the prototype worked after iterative troubleshooting. Numerical measurements, cycle counts, current measurements and a final verified schematic were not present in the project notes used to prepare this document. Complete the observation table with measured results before claiming quantified performance.

## Limitations

- Probe conductivity varies with water composition.
- Corrosion and deposits can change probe behaviour over time.
- Breadboard wiring is less robust than a finished PCB.
- A relay is a mechanical component and has finite switching life.
- The prototype should not be used as the sole protection against flooding or pump dry-running.
