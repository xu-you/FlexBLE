FlexBLE
==========

The firmware here is only for developers and hackers who are initerested in the BLE module of Flexbot.

Now, the firmware 'FlexBLE_1.0.0_cc254x.hex' is not compitable with the released apps(Flexbot 1.0.3 app for Android, Flexbot 1.0.1 app for for iOS). 

Instead, you can use the code in branch dev_v2 of HexNanoController_iOS to test with the firmware.

## There are three usable characteristics of the BLE firmware

char,      ddress,   value length,    access,                        more info
 
CHAR1,     0xFFE1,       6,           write without response,      use for rc channels(app-->BLE module)

CHAR2,     0xFFE2,       18,          write without response,      use for rx(send data from the app to the rx port of the BLE module)

CHaR4,     0xFFE4,       20,          notify,                      use for tx(receive data from the tx port of the BLE module)


## How to load Load the hex file onto the TI CC254x

**You Will Need**
* [TI CC-Debugger](http://www.ti.com/tool/cc-debugger) (must be purchased)
* [TI SmartRF Flash Programmer](http://www.ti.com/tool/flash-programmer) (free)

**Steps**
* Connect the CC-Debugger 
  * To your computer via USB
  * To the Flexbot BLE module,only five wires connections are needed
    *3.3V
    *GND
    *RESET
    *CC
    *DC
* Select **Program CCxxxx SoC or MSP430**
* Click on the **System-on-Chip** tab
* Use the following settings:
  * Set **Interface** to **Fast**
  * Flash image
    * Browse to the .hex file you want to load onto the chip
  * Ensure **Retain IEEE when reprogramming the chip** is checked
  * Select **Erase, program and verify**
* Click **Perform Actions**)
