# How to flash stm32f103 bootloader
Just edit flash.bat COM port an run it.

### Useful links

| Library | Download Link |
| ------ | ------ |
| STM32 Arduino | https://github.com/rogerclarkmelbourne/Arduino_STM32 |
| STM32duino bootloader | https://github.com/rogerclarkmelbourne/STM32duino-bootloader |
| HID v2 bootloader | https://github.com/Serasidis/STM32_HID_Bootloader |


### Wiring
So if your board has an LED on pin PC13 the makefile target is "generic-pc13" . At the time of writing the following geneirc targets are available (more may be added without this readme being updated each time, so please check the makefile to see the latest list of build targets)
The easiest way to upload to these board is to use a USB to Serial adapter connected to Hardware Serial 1 (Pins PA9 and PA10).
Additionally to enter serial bootloader mode, these boards, need to be configured so that Boot0 is HIGH and Boot1 is LOW. On most boards these pins are either connected to jump links or to switches.
Note. If the board is reset again, the code will not run if Boot0 is still HIGH etc, so once development is complete, both Boot0 and Boot1 need to be set to LOW so that the code runs immediately after power on or restart.


### Flash Commands
stm32flash.exe -w HID_Bootloaders\hid_generic_pc13.bin COM8

