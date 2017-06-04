# Witty ESP8266

This ESP8266 based module consists of two PCB's. A bottom and top one. 
Witty ESP-12F WiFi module, ESP8266

## Introduction

### Hardware bug

When powering the Witty for the first time, the RGB should show some color(s). Mine did not. After loading the sketch that shows random colors, the RGB LED didn't work either. So mine was part of a batch where the RGB LED was soldered wrong. This can be fixed by unsoldering the LED and soldering it after rotating it 180 degrees.

Of course, the LED can also be removed, to free up pins.

### Workshop friendly. 

Pre-soldered, so that it is friendly for workshops. The top PCB has male pins, so when attaching other components, you probably use female-female dupont wires. Please test your PCB before you start a workshop to know if you have the hardware bug.

### Breadboard unfriendly.

Unfortunately it covers rows a-j on a breadboard, so you need two breadboards next to each other, or use jumper wires underneath the PCB.

### Credits

 * [The Jedi Blog](https://blog.the-jedi.co.uk/2016/01/02/wifi-witty-esp12f-board/)
 * [Aditya Tannu Blog](http://adityatannu.com/blog/post/2016/01/31/ESP8266-Witty-Cloud-Board-Demo.html) 
 * [Arduino IDE Board](https://github.com/esp8266/Arduino)


## Programming the board 

### Arduino IDE 1.8.2

No additional driver was needed on Win10 with the Arduino IDE 1.8.2.

### Board Manager

 * In the Arduino IDE Preferences, add an additional board manager URL 'http://arduino.esp8266.com/stable/package_esp8266com_index.json'.

 * Navigate to the Board Manager and install the 'esp8266 by ESP8266 Community'.
 * Select board NodeMCU 1.0
 * Select COM port

### Code

The code is from the Jedi blog, and it uses the LDR, the RGB and the button, that are specific for this Witty module. It does not use generic ESP8266 functions. 

### Upload

Using the NodeMCU 1.0 board, there is no need to use the flash or reset buttons on the shield. Just upload.



## Hardware


### Bottom PCB (programmer)

 * USB for power + data
 * Reset button
 * Flash button

Note: When selecting NodeMCU 1.0 as target in the Arduino IDE, there was no need to use the Flash or Reset button.

Witty pinout (6 ESP pins not exposed)

    REST         |       TXD
    ADC    LDR   |       RXD
    CH_PD        |       GPIO05
    GPIO16       | BTN   GPIO04
    GPIO14       |       GPIO00
    GPIO12 RGB-G |       GPIO02
    GPIO13 RGB-B | RGB-R GPIO15
    VCC          |       GND
                USB


## Top PCB (ESP8266)

 * User button
 * USB for power (no data probably)
 * LDR (light sensitive resistor)
 * RGB LED (hardware bug: might be mounted 180' wrong)

 * Unused ESP GPIO pins
 

