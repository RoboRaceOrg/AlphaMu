# Roboracer Alpha Mu™ Firmware

Download this code as a zip file and extract the contents onto your computer. You will need to launch the xLoader program from the folder you extracted the zipped files into.

You can find the code for Roboracer Alpha Mu here:-
[Roboracer Alpha Mu™ Firmware repository](https://github.com/RoboRaceOrg/AlphaMu)


## How to Upload Roboracer Alpha Mu firmware to Roboracer Alpha microcontroller Using xLoader for Windows PC

### The following steps will help us use XLoader to upload HEX file on ATmega328 (Arduino Uno).

1. Open xLoader
1. Browse the HEX File from RoboracerAlphaMu™ folder.  The file is called:- RoboracerAlphaMu™.ino.hex
1. Select the device E.g. In case of Arduino Uno, it's ATmega328
1. Select COM Port
1. Select right baud rate in case of Arduino Uno it's 115200
1. Finally hit Upload Button



## How to Upload Roboracer Alpha Mu firmware to Roboracer Alpha microcontroller on Linux based system

1. Download and extract the contents of the zip file into your home directory.
1. Install Avrdude
 ```
cd
sudo apt-get install avrdude
```
1. Make project folder in user home:
```
mkdir RoboracerAlphaMu™
```
1. Find your serial device (tty)
```
ls -l /dev/ttyUSB* && ls -l /dev/ttyS*
```
1. Install the file called
```
avrdude -v -p atmega328p -c arduino -P /dev/ttyUSB0 -b 57600 -D -U flash:w:/home/RoboracerAlphaMu™/avrdude/RoboracerAlphaMu™.ino.hex:i
```
You should get the following output:-
```
avrdude: Version 6.3
         Copyright (c) 2000-2005 Brian Dean, http://www.bdmicro.com/
         Copyright (c) 2007-2014 Joerg Wunsch

         System wide configuration file is "/etc/avrdude.conf"
         User configuration file is "/home/pi/.avrduderc"
         User configuration file does not exist or is not a regular file, skipping

         Using Port                    : /dev/ttyUSB0
         Using Programmer              : arduino
         Overriding Baud Rate          : 57600
         AVR Part                      : ATmega328P
         Chip Erase delay              : 9000 us
         PAGEL                         : PD7
         BS2                           : PC2
         RESET disposition             : dedicated
         RETRY pulse                   : SCK
         serial program mode           : yes
         parallel program mode         : yes
         Timeout                       : 200
         StabDelay                     : 100
         CmdexeDelay                   : 25
         SyncLoops                     : 32
         ByteDelay                     : 0
         PollIndex                     : 3
         PollValue                     : 0x53
         Memory Detail                 :

                                  Block Poll               Page                       Polled
           Memory Type Mode Delay Size  Indx Paged  Size   Size #Pages MinW  MaxW   ReadBack
           ----------- ---- ----- ----- ---- ------ ------ ---- ------ ----- ----- ---------
           eeprom        65    20     4    0 no       1024    4      0  3600  3600 0xff 0xff
           flash         65     6   128    0 yes     32768  128    256  4500  4500 0xff 0xff
           lfuse          0     0     0    0 no          1    0      0  4500  4500 0x00 0x00
           hfuse          0     0     0    0 no          1    0      0  4500  4500 0x00 0x00
           efuse          0     0     0    0 no          1    0      0  4500  4500 0x00 0x00
           lock           0     0     0    0 no          1    0      0  4500  4500 0x00 0x00
           calibration    0     0     0    0 no          1    0      0     0     0 0x00 0x00
           signature      0     0     0    0 no          3    0      0     0     0 0x00 0x00

         Programmer Type : Arduino
         Description     : Arduino
         Hardware Version: 2
         Firmware Version: 1.16
         Vtarget         : 0.0 V
         Varef           : 0.0 V
         Oscillator      : Off
         SCK period      : 0.1 us

avrdude: AVR device initialized and ready to accept instructions

Reading | ################################################## | 100% 0.00s

avrdude: Device signature = 0x1e950f (probably m328p)
avrdude: safemode: hfuse reads as 0
avrdude: safemode: efuse reads as 0
avrdude: reading input file "/home/pi/avrdude/Blink200.hex"
avrdude: writing flash (32670 bytes):

Writing | ################################################## | 100% 0.62s

avrdude: 32670 bytes of flash written
avrdude: verifying flash memory against /home/RoboracerAlphaMu™/avrdude/RoboracerAlphaMu™.ino.hex200.hex:
avrdude: load data flash data from input file/home/RoboracerAlphaMu™/avrdude/RoboracerAlphaMu™.ino.hex:
avrdude: input file /home/RoboracerAlphaMu™/avrdude/RoboracerAlphaMu™.ino.hex contains 32670 bytes
avrdude: reading on-chip flash data:

Reading | ################################################## | 100% 0.48s

avrdude: verifying ...
avrdude: 32670 bytes of flash verified

avrdude: safemode: hfuse reads as 0
avrdude: safemode: efuse reads as 0
avrdude: safemode: Fuses OK (E:00, H:00, L:00)

avrdude done.  Thank you.
```
