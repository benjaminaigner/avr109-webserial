# avr109-webserial

Inspired by https://github.com/noopkat/avrgirl-arduino

## Background

For our assistive device [FABI](https://github.com/asterics/fabi) & [FLipMouse](https://github.com/asterics/flipmouse) we currently develop a WebSerial based [GUI](https://github.com/asterics/Addon-Bluetooth-WebGUI) to adjust the settings.

One main missing feature was the update process for the included Arduino Micro and TeensyLC.

This project aims to be a proof-of-concept for WebSerial based Arduino Micro updates.

Initially, I wanted to extend the [AVRGirl project](https://github.com/noopkat/avrgirl-arduino), but this project is node.js based. We just need plain JS to be supported in the browser.

## Caveats

Because this is a simple proof of concept, some features are still missing or implemented just for Arduino Micro:
* Fixed page size of 128Bytes
* No verification of the flashed content (as it is done by avrdude in Arduino)
* Just one USB PID/VID pair is used, there are probably more!
* The WebSerial feature of Chromium does NOT allow to open 2 ports with 1 user interaction. But the Arduino Micro running and its bootloader use 2 different PID/VIDs, so 2 user interactions are required (extra "Reset" button)

## How to use

1. Select the corresponding .hex file
2. Press "Reset" and select Arduino Micro device
3. Press "Upload" and select the Arduino Bootloader device

Note: if there is no available device once "Upload" is pressed, try to press "Reset" again and immediately press "Upload" again.

Note: if there is no Arduino shown at all, please open an issue and tell me your PID/VID combination.

# Acknowledgements

@noopcat for [avrgirl-arduino](https://github.com/noopkat/avrgirl-arduino) which provided the HTML code.

@bminer for [intel-hex.js](https://github.com/bminer/intel-hex.js) which provided the Intel HEX file parser

and of course: stackoverflow :-)


