# ATmega328pProgrammer
A Schematic and PCB Design for an Arduino Nano based ATmega328p/Arduino Programmer

[<img src="https://github.com/estods3/ATmega328pProgrammer/blob/main/photos/programmer_pcb.png" title="Arduino Programmer" alt="drawing" width="500"/>](https://github.com/estods3/ATmega328pProgrammer)
[<img src="https://github.com/estods3/ATmega328pProgrammer/blob/main/photos/BuiltProgrammer.jpg" title="Arduino Programmer (Built)" alt="drawing" width="250"/>](https://github.com/estods3/ATmega328pProgrammer)

## Steps

1) Program your Arduino Nano using the SW/ArduinoISP/ArduinoISP.ino script in the Arduino IDE. NOTE: Do this BEFORE placing you Arduino Nano in the circuit made from this repository. The circuit in the repo disables the auto-reset function of the Nano using a capacitor from reset to ground. This will allow the Nano to act as a programmer using the SW/ArduinoISP/ArduinoISP.ino script.
2) Build the circuit outlined in the PCB folder. The schematic and board layout can be opened using Eagle.
3) Insert an Arduino Nano into the header pins of the board with USB port facing opposite of the 3 LEDs on the board. Make sure the Nano is powered off and not plugged into a PC or other USB device. Next, add an ATmega328p chip into the header pins with the notch facing to the left.
4) Plug in the USB cable from the Nano to the PC. Open the Arduino IDE and select "Arduino Uno" as the board under Tools. Select the port as the correct port for your Nano. These settings will be used to burn the bootloader for an Arduino Uno to the ATmega chip.
5) Burn the Bootloader. This will take a few seconds. Check red LED for errors.
6) Upload the test script (SW/Blink/Blink.ino) to test that the bootloader was burned successfully and the chip can now accept programs. Open the test script included in this repo in the Arduino IDE. Use the same settings as in step 4. Click "Sketch" then "Upload using Programmer" to upload the test script to the chip. The Test LED should begin to blink.

## Resources
https://docs.arduino.cc/built-in-examples/arduino-isp/ArduinoToBreadboard
