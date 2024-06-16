# Lamp Controller with Matter
<p>
    <img src="https://github.com/vinepb/Matter-Lamp-Hardware/blob/main/images/iPhone_12_1.png" width="200">
    <img src="https://github.com/vinepb/Matter-Lamp-Hardware/blob/main/images/iPhone_12_2.png" width="200">
</p>

## Overview

This project is a smart lamp controller designed for a 3V3 3D printed lamp. It utilizes an ESP32 microcontroller and has been tested with Apple's HomeKit ecosystem. The project consists of both software and hardware components, making it a complete solution for controlling the lamp remotely.

![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white)
![CMake](https://img.shields.io/badge/CMake-%23008FBA.svg?style=for-the-badge&logo=cmake&logoColor=white)
![Espressif](https://img.shields.io/badge/esp%20idf-E7352C.svg?style=for-the-badge&logo=espressif&logoColor=white)
![KiCad](https://img.shields.io/badge/KiCad-2C45C8.svg?style=for-the-badge&logo=kicad&logoColor=white)

## Hardware

Refer to [Matter-Lamp-Hardware](https://github.com/vinepb/Matter-Lamp-Hardware).

## Software

This project is based on the following technologies:

- [esp-idf](https://github.com/espressif/esp-idf): Espressif's IoT Development Framework.
- [esp-matter](https://github.com/espressif/esp-matter): Espressif's SDK for Matter.

### Installation

Follow the installation instructions for [esp-idf](https://github.com/espressif/esp-idf)
```shell
cd ~ && mkdir esp && cd esp
git clone --recursive https://github.com/espressif/esp-idf.git
cd esp-idf; git checkout v5.2.1; git submodule update --init --recursive;
./install.sh
cd ..
```
Then install [esp-matter](https://github.com/espressif/esp-matter):
```shell
cd esp-idf
source ./export.sh
cd ..

git clone --recursive https://github.com/espressif/esp-matter.git
cd esp-matter
./install.sh
cd ..
```
Then clone this repository and configure the environment:
```shell
cd ~/esp
git clone https://github.com/vinepb/Matter-Lamp-Firmware.git

# The next two commands should be done with each new terminal session
source ~/esp/esp-idf/export.sh
source ~/esp/esp-matter/export.sh
```
Then set the device's serial port, build and flash:
```shell
cd ~/esp/Matter-Lamp-Firmware
export ESPPORT=/dev/tty.SLAB_USBtoUART # Set your board's serial port here
idf.py set-target esp32
idf.py build flash monitor
```

### Add acccessory in the Home app

Open the Home app on your iPhone/iPad and follow these steps

- Tap on "Add Accessory" and press "More options...".
- A device named "Matter Accessory" should show up, click it and use setup code 20202021.
- Select the "Add Anyway" option for the "Uncertified Accessory" prompt.