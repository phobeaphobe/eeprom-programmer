# Arduino EEPROM programmer

## Notes

I will be having to adapt this code for use with my own (smaller) Arduino board.
Upon completion/review of the code, and the behavior of the Texas Instruments SN74HC595N shift registers,
I may add additional optimizations and add a pull request to the original repo.

## Circuit

This is a simple circuit for programming the 28C16, 28C64, 28C256, and similar parallel EEPROMs using an Arduino.
Since the Arduino doesn’t have enough pins to directly control all of the address, data, and control lines of the
EEPROM,
two 74HC595 shift registers are used for the 11 address lines (15 for the 28C256) and the output enable control line.

![Schematic of EEPROM programmer](https://raw.githubusercontent.com/phobeaphobe/eeprom-programmer/master/schematic.png)

## What’s here?

### 1. Basic programmer

The code in [`/eeprom-programmer`](/eeprom-programmer) is the basic programmer that programs a few bytes into the EEPROM
and dumps the contents.

### 2. 8-bit decimal display

The code in [`/multiplexed-display`](/multiplexed-display) is for programming an EEPROM to be used to decode 8-bit
values and drive a 4-digit 7-segment display.

### 3. 8-bit computer microcode

The code in [`/microcode-eeprom-programmer`](/microcode-eeprom-programmer) is for programming a pair of EEPROMs to serve
as an instruction decoder for an 8-bit breadboard computer.

### 4. 8-bit computer microcode with flags register

The code in [`/microcode-eeprom-with-flags`](/microcode-eeprom-with-flags) adds functionality for a flags register to
the microcode above to support conditional instructions.

## More information

This EEPROM programmer was designed as part of a larger project to build an 8-bit computer from scratch.

Copyright 2017 Ben Eater

This code and schematic are [MIT licensed](http://en.wikipedia.org/wiki/MIT_License).
