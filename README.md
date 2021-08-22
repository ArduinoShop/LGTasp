# LGTasp
USBasp/USBisp module for the LGT8F328P and AVR boards.

I created a small module to be able to program both LGT8F328P and AVR based Arduino board without the hassle of a bunch of jumper wires, caps on RST, permissions on the Linux for USB devices etc.  It is basically a [proMINI32](https://arduinoshop.ca/lgt8f328/promini32) with a shield on top that has connectors to plug in a (CP2102)(http://arduinoshop.ca/accs/cp2102) UART board as well as targets such as the [Nano32](http://arduinoshop.ca/lgt8f328/nano32), [proMINI32](http://arduinoshop.ca/lgt8f328/promini32), [AVR Nano](http://arduinoshop.ca/atmelbased/arduino-nano) and the [proMINI](http://arduinoshop.ca/atmelbased/promini5).  Actually most any AVR board could be programmed - it features an Arduino ISP connector.

This README is intended to serve as a operatin Manual for the LGTisp module.

**HARDWARE**

The basic hardware consists of a proMINI32 with female headers installed to accept the sheild which this module is.  The sheild fits atop the proMINI32.    I attach a couple of lousy photo which may or may not help in visualizing the programmer.

Bare Bones ![bare unit](https://arduinoshop.ca/images/multiISP_0_360.png) with CP2102 ![with CP2102](https://arduinoshop.ca/images/multiISP_1_360.png) 
