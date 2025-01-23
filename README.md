## MP153 Brainboard

This is a small PCB with an STM32MP153 microprocessor, 512MB DDR3 RAM, and a stereo codec.
It's designed for running high-end audio projects.

The processor is a dual-core Cortex-A7 at 800MHz with a 240MHz Cortex-M4 co-processor. The RAM runs up to 533MHz.
The processor supports NEON instructions, so it can be very fast for audio applications.

The brainboard is meant to plug into a larger board that has all the controls and jacks. The pinout
is similar to the Daisy Submodule, though care should be taken to confirm this before plugging into an
untested project.

Look at the schematic, under "CONNECTORS". The four 2x5 pin 0.1" headers in
that section (JA1, JB1, JC1, JD1) are the connections to your control board. 

The bare minimum connection would be to apply +12V, GND, and -12V to the appropriate pins on header JA1.
The audio inputs and outputs are on header JB1, and should be in the range of +/- 10V.

Pots or other analog inputs in the range of 0V-3.3V can be input into any ADC-IN pin (most are on JC1).
Other peripherals are available: SPI, SDMMC, UART, I2C.


The debug header is J2 and you can select SWD or JTAG. I've had better luck with JTAG, so this is the default,
but if you need to use SWD then cut the solder jumper JP1 and blob it to the NRST side.

There's an on-board USB jack, and the USB signals are on pins, so you can have a USB High Speed jack on your panel or main board (Thanks Manu!).
Don't use both at once.

For firmware, look at https://github.com/4ms/mp1-brainboard-demo and also at https://github.com/4ms/stm32mp1-baremetal
