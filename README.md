# ESP32 Bluetooth Library Compile Setup

This is a Platform IO project that will compile a stripped-down
version of the ESP-IDF Bluetooth library as used by the Arduino
Espressif32 framework. The libbt.a that is normally included in
framework-arduinoespressif32 has a lot of options enabled, resulting
in a large RAM usage.  For a project that needs only
Bluetooth Serial, it is possible to save a lot of RAM by omitting
unnecessary features such as BLE and audio.

## Usage

Clone this repo into a directory and compile therein using Platform IO.

* pio run

This will compile a lot of stuff, most of it unnecessary.

When the compilation is done, copy the file
.pio/build/esp32dev/esp-idf/bt/libbt.a into the Arduino Framework.
Typically the destination filename will be
$HOME/.platformio/packages/arduinoespressif32/tools/sdk/esp32/lib/libbt.a

Then if you compile an application against that framework, the Bluetooth
stack will use a lot less memory than it would otherwise.

## Framework Version

You might need to edit platformio.ini to choose the version of
framework-arduinoespressif32 that matches what you use in you
main project.
