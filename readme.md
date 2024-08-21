# QMK Json to UF2

Note: this was done compiling firmware for a lily58, I assume the steps are the same for any keyboad using a [pro micro](https://mechboards.co.uk/products/pro-micro-5v?_pos=1&_sid=de804ae38&_ss=r) for the microcontroller. 

This document will cover some quick steps to go from a configurations on [QMK Configuratior](https://config.qmk.fm) to compiled firmware for your [pro micro](https://mechboards.co.uk/products/pro-micro-5v?_pos=1&_sid=de804ae38&_ss=r) based keyboard

This guide has only been tested on windows. I am unable to offer any steps for linux at this time. 
 
 - Install [QMK MSYS](https://msys.qmk.fm/)
 - Configure your key mapping on [QMK Configuratior](https://config.qmk.fm)
 - select your keyboard from the dropdown
 - name the keymap
 - Confgirue our keys using the interace, Once you are happy, click the download keymap.json button
 - open a terminal (or QMK MSYS if you did not add to your path)
 - import the json file by running  `qmk import-keymap <path to json file>`
 - for the next step
  - `-km` flag will be the .json file name without the extension
  - `-kb` flag will be the keyboard value from [QMK Configuratior](https://config.qmk.fm)
 - compile the layout ` qmk compile -kb <keyboard> -km <key_mapping> -e CONVERT_TO=rp2040_ce`
 - this will create a .uf2 file in `~/qmk_firmware`
 - connect your keyboard to your computer and copy the generated UF2 file to your controller.


If you came across any issues please submit an issue and I will try to update the instructions. 

 ## TODO
  [ ] Fix left hand screen
  [ ] Write guide to customise each screen content.   
