# LPM3 front-end #

The LPM3 is a device to measure light pollution on sea turtle nesting beaches. This repository focuses on the development of the front-end of the device, which can be used separately by any programmable device with an I²C and a SPI interface, such as an arduino, raspberry pi, or a suitable USB adapter.

The LPM3 front-end consists of a high sensitivity photometer and a regular sensitivity single-chip lux meter, an accelerometer, and a magnetometer all laid out on a single printed circuit board.

## Ultra-low dark current photodiode

The core of the LPM3 front-end is Hamamatsu's S1133, an ultra-low dark current visible light photodiode. A transimpedance amplifier with a 1GOhm feedback resistor gives a theoretical output of 1V per 0.164 lux. With a 12-bit ADC and a 2.5V reference, we can get a sensitivity of 0.0001 lux. The LPM3 is equipped with a 16-bit ADC, giving an absurd theoretical sensitivity of 0.00000625lux. Imperfections in the circuits and component manufacturing are expected to 

## Generic lux meter

The high sensitivity photodiode circuit is unable to measure any illuminance higher than 0.41lux. For this reason, and to serve as a crude source of self-calubration reference, the OPT3001 single-chip lux meter by Texas Instruments was incorporated in the LPM3 font-end. This lux meter is capable of measurements from 0.01 lux all the way up to daylight. This should cover all foreseeable light pollution conditions from pitch black all the way to in front of spotlights that are sometimes used to safeguard beach equipment.

## Accelerometer

All light pollution measurements should be taken at a horizontal plane, which is where hatchlings and sea turtles scan to perceive ambient light. An embedded accelerometer can either ensure this condition or be used to include device orientation in the dataset.

## Magnetometer

A magnetometer is the only way to know what direction a specific light pollution measurement was taken from.

## License
The LPM3 depository integrates hardware design, firmware source code, desktop software, and supporting documentation. These are licensed as follows:
- Hardware design files are licensed under the CERN Open Hardware License,
- Software source code files are licensed under the GNU GPL v3 license,
- Documentation files are licensed under the GNU Free Documentation License,
- Videos are licensed under Creative Commons Attribution-ShareAlike 4.0 International.
