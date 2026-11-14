# Source / Firmware

This project is implemented using discrete components (BC547 NPN transistors, water probes and a relay module). It does not contain an Arduino, ESP32 or other programmable controller.

Therefore, **no Arduino sketch or firmware is required for the current hardware version**. The switching behaviour is implemented by the transistor circuit itself.

If a microcontroller-based version is developed later, place its source in this directory and document the board, pin mapping, libraries and firmware version separately. Do not mix a future firmware implementation with the present transistor-only prototype.
