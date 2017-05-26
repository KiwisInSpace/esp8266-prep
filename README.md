# esp8266-prep

Lessons learned and useful resources to setup an ESP8266 development environment.

Most tools will be available for multiple operating systems. However the focus here is on `Microsoft Windows` and capturing the quirks discovered. For example proper driver setup and debugging can be a bit trickier in my experience.


## Basics

Just about all electronics use transistor-transistor logic (TTL) serial for debugging, bootloading, programming, serial output, etc. This includes the ESP8266 chip. But it's rare for a computer to have a serial port anymore. A USB to TTL serial cable or some adapter is needed. A common one is the `FTDI FT232` usb/serial adapter cable. It has a 6-pin socket at the end with 5V power and ground, as well as RX, TX, RTS and CTS at 3V logic levels. However it is more expensive than alternative solutions. Another common chip which is used by a number of Arduino compatible boards to provide USB connectivity is the the `CH340` chip.

## Windows Setup

This is the order of steps which worked for me when installing a development environment from scratch:

- Install USB-serial driver. Depends on the board or serial adapter being used.
  - CH340 USB to UART driver https://www.wemos.cc/downloads
  - FTDI drivers http://www.ftdichip.com/FTDrivers.htm
- Download Arduino IDE from https://www.arduino.cc/en/Main/Software
- In Arduino IDE > Sketch > Include Library > Manage Libraries... : install additional libraries as needed. For example:
    - CmdMessenger http://playground.arduino.cc/Code/CmdMessenger
    - WifiManager https://github.com/tzapu/WiFiManager
    - Adafruit ESP8266 https://github.com/adafruit/Adafruit_ESP8266
- Install the ESP8266 Board in Arduino IDE
    - Step-by-step: https://github.com/esp8266/Arduino#installing-with-boards-manager
    - Boards manager link: http://arduino.esp8266.com/stable/package_esp8266com_index.json
- Install Blynk tools and lib:
    - http://www.blynk.cc/getting-started/
    - The download and install needs to be done manually.
