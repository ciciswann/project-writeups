# Project Write-Ups 
Write-ups for hardware projects I've completed or am currently working on. 

![original](https://user-images.githubusercontent.com/17733481/146074542-fb7cf1b4-03c9-49d3-95a5-fd3a1cfece4f.gif)

All project images and videos were taken by me unless stated otherwise.

## Projects


- [Album Art Display on 64x64 LED RGB Matrix w/ Raspberry Pi 4 🎶](#album-art-display)
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


