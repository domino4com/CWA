# CWS Core WiFi Standard
This is the default core used in the Domino4 eco-system.

## Main ChipSet
The core is built around the [ESP32-WROOM-32](https://www.espressif.com/sites/default/files/documentation/esp32-wroom-32_datasheet_en.pdf) module from Espressif. Future versions of this core will be using newer version of the ESP32 chipset.

## Programming

### Programming in Arduino
- To program the Domino4 cores using Arduino, install the board files using the doumentation from [Espressif](https://github.com/espressif/arduino-esp32)
- Please read the notes regarding upload/transfer speed when using the [PPU](https://github.com/domino4com/PPU).
- Settings:
  - **Board:** Choose the ```ESP32 Dev Module```
  - **Speed:** Max 460800 bps
  - **Port:** Chose the port where your PPU is inserted. If you cannot see the port, the check out your [PPU installation](https://github.com/domino4com/PPU)

### Programming in Python.
- Download the MicroPython firmware from [micropython.org](https://micropython.org/download/esp32/)
- It is recommended to download and use the (Mu Editor)(https://codewith.mu/en/download)
- You can use the Mu Editor to upload the MicroPython Firmware.

## Pin Usage
### Touch Buttons
| Symbol | GPIO | T# |
|:-----------------------------:|:----:|:--:|
| :arrow_left:                  | IO13 | T4|
| :arrow_right:                 | IO15 | T3|
| :arrow_up:                    | IO12 | T5|
| :arrow_down:                  | IO27 | T7|
| :white_check_mark:            | IO4  | T0|
| :negative_squared_cross_mark: | IO14 | T6|
| :robot:                       | IO33 | T8|

### LEDs
| Postion | Color | GPIO | On when|
|:-----------------------------|:----:|:--:|:--:
|  Top |Red| IO25 | High |
|  Top |Blue| IO26 | High |
|  Middle |Yellow| IO19 | High |
|  Bottom |Red| IO17 | High |
|  Bottom |Green| IO18 | High |

### Other Pins
| Function |  GPIO | Notes|
|:-----------------------------|:----:|:--|
|  I²C SDA |21| |
|  I²C SCL |22| |
|  Serial TX |1| |
|  Serial RX |3| |
|  IO pin |2| When used for capacitative sensing, refer to T2|
|  Reserved |32| For future use|

## Troubleshooting
- If you try to upload code and getting this message ```A fatal error occurred: Timed out waiting for packet content``` or ```A fatal error occurred: Invalid head of packet (0xE0)```, change the transfer speed to 460800 pbs.
- If you try to upload code and getting this message ```[7886] Failed to execute script esptool the selected serial port [7886] Failed to execute script esptool
does not exist or your board is not connected```, your serial port is open by another application. Close the other application and try again.


