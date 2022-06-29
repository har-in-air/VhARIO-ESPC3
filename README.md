# VhARIO-ESPC3

The 'h' is silent, but the vario speaks ...

Kicad 6 schematic and layout for ESP32-C3 + MPU9250 + MS5611 audio vario. 

Uses a Kalman filter to fuse acceleration data and pressure altitude data for 'zero-lag' variometer response.

Configured via Wi-Fi web page.

Optional Bluetooth transmission of $LK8EX1 sentences to interface with apps like [XCTrack](https://xctrack.org).

ESP32-C3 flash and debug via built-in USB serial jtag peripheral and USB C interface.

Li-poly battery with recharging via USB-C.

2-layer PCB sized for [Hammond 1551K 80x40x20 mm enclosure.](docs/1551K.pdf)

All SMD passive components use Kicad hand-solderable footprints.

Apart from the ESP32-C3 module, IMU breakout board, battery connector and flash/debug switch, all SMD components are on one side of the board. This is to facilitate automated PCB assembly. 

[Schematic PDF](docs/vhario-espc3-schematic.pdf)

You can find the firmware [here](https://github.com/har-in-air/ESP32C3_BLUETOOTH_AUDIO_VARIO).

A previous revision (Rev A) of the hardware can be found in the releases section.

## Differences between Rev A and Rev B
* Rev B is a Kicad 6 project ( 6.0.6 as of date). Rev A was unfortunately developed with Kicad 6.99 branch which broke the project file format w.r.t. Kicad 6. The Rev A project can only be opened with Kicad 6.99 build 2022 Jan 26 or later.
* Flash and debug in Rev B uses the ESP32-C3 built-in USB serial jtag peripheral with a switchable jumper/spdt switch to facilitate flashing. For Rev A hardware, an external USB-UART adapter and jumper/switch is required for flash and debug. 
* For Rev B, all smd components except for a couple of modules have been placed on one side to facilitate automated pcb assembly.
* The firmware is compiled with a selectable #define configuration option to select Rev A or Rev B hardware.


## Hardware

* AI-Thinker  ESP-C3 12F module (C3FN4).
* CJMCU-117 IMU module (MPU9250 + MS5611).
* 74HC240 used as push-pull piezo driver.
* 1800mAH Li-Poly battery.
* MCP73871 battery charger @ 500mA max, via USB-C connector.
* Soft-switched power on/off
* "No activity" timeout automatic power-off.
* USB serial jtag programming and debug via USB C connector. No need for external USB-UART adapter.

## PCB Top
<img src="docs/top.png">

## PCB Bottom
<img src="docs/bottom.png">

# Credits

Prototype design, component sourcing and PCB assembly in collaboration with Benoit Arnal.
 