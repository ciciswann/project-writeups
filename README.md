# Hardware Projects
Write-ups for hardware projects I've completed or am currently working on. 

![original](https://user-images.githubusercontent.com/17733481/146074542-fb7cf1b4-03c9-49d3-95a5-fd3a1cfece4f.gif)

All project images and videos were taken by me unless stated otherwise.

## Projects


- [Album Art Display on 64x64 LED RGB Matrix w/ Raspberry Pi 4 🎶](#album-art-display)
- [Gingham Through Hole Keyboard](#gingham-through-hole-keyboard)
- [6502 Microprocessor Breadboard Computer](#6502-breadboard-computer) (WIP)
- [Macro Keyboard w/ OLED Display](#macro-keyboard-with-oled) (WIP)


## Album Art Display
Credit for this project idea goes to a user on [r/raspberry-pi](https://www.reddit.com/r/raspberry_pi/comments/ombwwg/my_64x64_rgb_led_matrix_album_art_display_pi_3b/). It's a pretty good beginner project to start learning more about IoT and networking, as well as learning how to make minor modifications that require soldering. 

### Preview

https://user-images.githubusercontent.com/17733481/146075286-3e12e833-f6dc-4c50-86b2-f484d3a61001.mov

### Hardware Components

- Raspberry Pi 3b or 4 (with Raspberry Pi OS)
- 64x64 LED RGB Matrix (Adafruit)
- RGB Matrix Bonnet (Adafruit)
- 5V 10A Power Supply

Soldering is required for the Bonnet to work with 64x64 Matrix. I use a Hakko FX888D-23BY digital soldering iron.

### Hardware Overview

The hardware portion of this project is fairly plug and play, with the exception of some minor soldering on the bonnet to enable [PWM](https://learn.sparkfun.com/tutorials/pulse-width-modulation/all) and get the bonnet working with the 64x64 matrix. Make sure to read all of the [documentation for setup of the bonnet and matrix](https://learn.adafruit.com/adafruit-rgb-matrix-bonnet-for-raspberry-pi/). 

### Software Reqs 
The following need to be installed on your pi:
- [Shairport-sync-mqtt-display](https://github.com/idcrook/shairport-sync-mqtt-display)(Python-flaschen-taschen)
- Shairport-sync (instructions for installation can be followed in the documentation mentioned below)
- MQTT Broker (I used [Mosquitto](https://mosquitto.org/download/))
- [Flaschen-Taschen](https://github.com/hzeller/flaschen-taschen.git)

### Software Overview

The [documentation written by idcrook](https://github.com/idcrook/shairport-sync-mqtt-display/wiki) needs to be followed very carefully (also, follow the python-flaschen-taschen instructions for this specific project). When configuring shairport-sync make sure to include `--with-mqtt-client --with-pipe --with-airplay-2`. Before configuring shairport-sync, make sure the MQTT Broker has already been installed. 

At the end you should have shairplay-sync and the MQTT broker running as services. You should also have the python-flaschen-taschen app.py running (`python3 app.py`) from inside the shairport-sync-mqtt-display directory and the Flaschen-Taschen server running (`sudo ./ft-server --led-gpio-mapping=adafruit-hat-pwm --led-slowdown-gpio=2 --led-rows=64 --led-cols=64 --led-show-refresh --led-brightness=50`). 

## Gingham Through Hole Keyboard
I love the look of through hole keyboards and this Gingham keyboard is no exception. There's just something really cool about hardware that uses its electronic components as part of its overall design. Overall, this was a fun build that involved quite a bit of soldering with 64-1N4148 diodes and 28 other components (not including switches).

![image](https://user-images.githubusercontent.com/17733481/147046329-ed06e2de-c081-42a1-944b-5b47bde3c2f6.png)

### Hardware Components
- Gingham Keyboard PCB & Components (NovelKeys)
- Durock stabilizers
- Durock 67G Linear Switches (Smokey Teal)
- Kuro Shiro Japanese Keycaps (Hiragana)
- Mill-max 0305 sockets (this converts the PCB to hot swappable, so you can switch out switches) 

Soldering Iron, flux, and solder for (you guessed it) soldering. Stabilizers and switches lubed with Krytox 205G0 Lubricant (this lube is only really recommended for linear switches, or tactile if you use a very light hand).

### Hardware Overview 

There's a lot of components that need to be soldered onto the PCB, so the build did take a few hours. Like with most builds, I started with the smallest components first and finished with the switches. The pins on the USB-C connector are very small so they required flux and a [drag-soldering technique](https://hackaday.com/tag/drag-soldering/) to get the connector affixed to the board. 

### Software Reqs
- [VIA](https://github.com/the-via/releases/releases/tag/v1.3.1)

### Software Overview

I installed VIA and before soldering on switches (or Mill-max sockets), hooked up the keyboard to my PC for the keyboard test. To test, all I did was touch each switch placement (with two pads) on the PCB with a pair of metal tweezers (essentially completing the circuit) to get each key to register. 

## 6502 Breadboard Computer

*Work in Progress Build* 


This specific build was inspired by one of my favorite youtubers (Ben Eater). This has probably been one of my most challenging projects to date because I started at a baseline of knowing absolutely nothing about electrical schematics or electricity in general. I would like to make another variation of this project on a printed circuit board (PCB). 

### Preview
Final result (image courtesy of eater.net) - I will be posting images of my project and a video of a game I've been working on in assembly once completed. \
![image](https://user-images.githubusercontent.com/17733481/146108119-390edaeb-bc2b-4955-8d81-9244fb2a2c4c.png)


## Macro Keyboard with Oled
*Work in Progress Build*

A 3D printed macro keyboard case with a small OLED attachment. Macros created by yours truly. 

### Preview

![image](https://user-images.githubusercontent.com/17733481/146108600-e0d7c36f-e087-493c-a6db-ce3d424c0fb3.png)


