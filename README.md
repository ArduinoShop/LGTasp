# LGTasp
USBasp/USBisp module for the LGT8F328P and AVR boards.

I created a small module to be able to program both LGT8F328P and AVR based Arduino boards without the hassle of a bunch of jumper wires, caps on RST, Linux permissions for the USB devices etc.  It is basically a [proMINI32](https://arduinoshop.ca/lgt8f328/promini32) with a shield on top that has connectors to plug in a [CP2102](http://arduinoshop.ca/accs/cp2102) UART board as well as targets such as the [Nano32](http://arduinoshop.ca/lgt8f328/nano32), [proMINI32](http://arduinoshop.ca/lgt8f328/promini32), [AVR Nano](http://arduinoshop.ca/atmelbased/arduino-nano) and the [AVR proMINI](http://arduinoshop.ca/atmelbased/promini5).  Actually most any AVR board could be programmed - it features an Arduino ISP connector but may need jumpers due to the mechanical layout..

This README is intended to serve as an Operatin Manual for the LGTisp module.

## HARDWARE

The basic hardware consists of a proMINI32 with female headers installed to accept this module as a sheild.  The sheild fits atop the proMINI32. Here are a couple of lousy photo which may or may not help in visualizing the programmer.  ( rev 0 boards picture )

                         Bare Bones                                          with CP2102
   ![bare unit](https://arduinoshop.ca/images/multiISP_0_360.png) ...... ![with CP2102](https://arduinoshop.ca/images/multiISP_1_360.png)
   
## Basic Operation:
  plug in a CP2102 board and either a LGT board or an AVR board..  Setup the Arduino IDE for the target board as follows:
  ### LGT boards:
    pay attention to the variant - the SSOP-20 has the serial I/O on different pins. Set the *Arduino as ISP* option to "Default(64)".
    select the **AVR ISP** programmer.
  
  ### AVR boards:
    setup the IDE as usual for your board - select the *Arduino as ISP* programmer.

Click on    *Sketch -> Upload Using Programmer* and watch the light show...   

here are some more lousy pictures... (not worth 1000 words but maybe 40-50...) **NOTE** the AVR proMINI installs with only 1 row on pins - OFFSET 1 pin on either end - the row with D12 and D13, VCC and GND etc. 

                    Nano32                                       AVR Nano
   ![NAno32](https://arduinoshop.ca/images/multiISP_Nano32_360.png) ...... ![with AVR Nano](https://arduinoshop.ca/images/multiISP_Nano_360.png)
   
 ## LEDs:  The shield has 4 LEDs to monitor status.
- **Blue LED** - *HeartBeat* - this LED flashes constantly when the LGTasp is running.
- **Green LED** - *UpLoading* - this LED lights while the sketch is being uploaded.
- **Red LED**   - *ERROR*     - this LED will light and stay lit if an error ocurred - it may also flicker as each buffer of data is uploaded.
- **Yellow LED** - This LED lights when a LGT board is properly connected..  stays off for an AVR board..
                  if no board is connected it flashes continously.
                  if both a LGT and an AVR board are connected the Yellow and Red LEDs flashes continously.

