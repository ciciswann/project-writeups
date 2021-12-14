# Project Write-Ups
Write-ups for hardware projects I've completed or am currently working on.

![original](https://user-images.githubusercontent.com/17733481/146074542-fb7cf1b4-03c9-49d3-95a5-fd3a1cfece4f.gif)

## Projects


- [Album Art Display on 64x64 LED RGB Matrix w/ Raspberry Pi 4](#album-art-display)
- 6502 Microprocessor Breadboard Computer (WIP)
- Macro Keyboard (WIP)


## Album Art Display
Credit for this project idea goes to a user on the [r/raspberry-pi subreddit](https://www.reddit.com/r/raspberry_pi/comments/ombwwg/my_64x64_rgb_led_matrix_album_art_display_pi_3b/). It is a pretty good beginner project to start learning more about IoT and networking, as well as making minor hardware modifications that require soldering. 

### Preview

https://user-images.githubusercontent.com/17733481/146075286-3e12e833-f6dc-4c50-86b2-f484d3a61001.mov

### Hardware Components

- Raspberry Pi 3b or 4 (with Raspberry Pi OS)
- 64x64 LED RGB Matrix (Adafruit)
- RGB Matrix Bonnet (Adafruit)
- 5V 10A Power Supply

Soldering is required for the Bonnet to work with 64x64 Matrix. I use a Hakko FX888D-23BY digital soldering iron.

### Hardware Instructions

The hardware portion of this project is fairly plug and play, with the exception of some minor soldering on the bonnet to enable [PWM](https://learn.sparkfun.com/tutorials/pulse-width-modulation/all) and get the bonnet working with the 64x64 matrix. Make sure to read all of the [documentation for setup of the bonnet and matrix](https://learn.adafruit.com/adafruit-rgb-matrix-bonnet-for-raspberry-pi/). 

### Software Reqs 
The following need to be installed on your pi:
- [Shairport-sync-mqtt-display](https://github.com/idcrook/shairport-sync-mqtt-display)(Python-flaschen-taschen)
- Shairport-sync (instructions for installation can be followed in the documentation mentioned below)
- MQTT Broker (I used [Mosquitto](https://mosquitto.org/download/))
- [Flaschen-Taschen](https://github.com/hzeller/flaschen-taschen.git)

### Software Overview

The [documentation written by idcrook](https://github.com/idcrook/shairport-sync-mqtt-display/wiki) needs to be followed very carefully (also, follow the python-flaschen-taschen instructions for this specific project). When configuring shairport-sync make sure to include `--with-mqtt-client --with-pipe --with-airplay-2`. Before configuring shairport-sync, make sure to install your MQTT Broker. 

At the end you should have shairplay-sync and MQTT broker running as services. You should also have the python-flaschen-taschen app.py running (`python3 app.py`) from inside the shairport-sync-mqtt-display directory and the Flaschen-Taschen server running (`sudo ./ft-server --led-gpio-mapping=adafruit-hat-pwm --led-slowdown-gpio=2 --led-rows=64 --led-cols=64 --led-show-refresh --led-brightness=50`). 


