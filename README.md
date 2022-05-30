Todo before going public:

- [ ] Photo PCB
- [x] Image screen
- [x] Image DevKit
- [ ] Share PCB on PCBWay
- [x] Complete List of GPIO's used
- [ ] Make Tindie Listing for PCB + Headers


# ESP32-S3-DevKitC-1 + Touchscreen Combiner PCB
[![](https://badgen.net/github/last-commit/DustinWatts/ESP32-S3_TFT_Combiner)](https://github.com/DustinWatts/ESP32-S3_TFT_Combiner/commits/master)
[![](https://badgen.net/github/release/DustinWatts/ESP32-S3_TFT_Combiner)](https://github.com/DustinWatts/ESP32-S3_TFT_Combiner/releases)
[![](https://img.shields.io/discord/693862273864827012?color=5165f6&label=chat%20on%20Discord)](https://discord.gg/RE3XevS)
[![](https://badgen.net/github/license/DustinWatts/ESP32-S3_TFT_Combiner)](https://github.com/DustinWatts/ESP32-S3_TFT_Combiner/blob/main/LICENSE)
[![](https://badgen.net/badge/watch/Buy%20from%20PCBWay/028A0F)](https://www.pcbway.com)
[![](https://img.shields.io/twitter/follow/DustinWattsNL)](https://twitter.com/DustinWattsNL)

A PCB making it easy to combine an ESP32-S3-DevKitC-1 and an ILI9488 TFT + XPT2046 Touchsceen.

## Order a PCB + headers kit from me

On Tindie I sell a kit containing all the PCB and alle the male and female headers you need. Al you have to do is source the screen and the ESP32-S3-DevKitC-1. [Order the PCB + header kit from Tindie](https://www.tindie.com/products/dustinwattsnl/esp32-touchdown "Order the combiner and male and female headers me, via Tindie")

## Order directly from PCBWay

You can order the PCB's directly from PCBWay here: [Order PCBs from PCBWay](https://www.pcbway.com/project/shareproject/ESP32_TFT_Combiner_V1.html "Order the combiner board directly from PCBWay")

## Download Gebers and use your own fab house

If you want to use your own fab house, you can find the gerbers (as wel as a .zip file for easy upload) in the [Gerber folder](/Gerbers "Download the gerbers") in this repo.

## The PCB

The PCB is designed in KiCad and uses 22-pin double row headers for the ESP32-S3 so you can use the GPIO's not used by the screen. It also uses a 14-pin header for the screen and a 4-pin header for the SD card. I recommend using female headers so you can remove both the ESP32-S3 and the screen.

Pins used by the screen, touchcontroller and SD card are:

| ESP32-S3 | Function |
|---|---|
| GPIO4  | SD_SELECT  |
| GPIO5  | TFT_RESET  |
| GPIO6  | TFT_DC_RS  |
| GPIO7  | TFT_BACKLIGHT  |
| GPIO10  | TFT_SELECT  |
| GPIO11  | MOSI  |
| GPIO12  | SCK  |
| GPIO13  | MISO  |
| GPIO15  | TOUCH_SELECT  |
| GPIO16  | TOUCH_IRQ  |

And off course 3V3 and GND are connected to the screen. 

The rest of the pins you can freely use. Use the ESP32-S3-DevKitC-1 pinout card as a reference: [Pinout Card on espressif.com](https://docs.espressif.com/projects/esp-idf/en/latest/esp32s3/hw-reference/esp32s3/user-guide-devkitc-1.html#pin-layout "ESP32-S3-DevKitC-1 Pinout Card")

## The ESP32-S3
<img src="https://github.com/DustinWatts/ESP32-S3_TFT_Combiner/blob/main/Assets/esp32-s3-devkitc-1.png" alt="ESP32-S3-DevKitC-1" width="480"/>

The ESP32-S3 for this board is the ESP32-S3-DevKitC-1. Which is currently sold by:
- [Mouser](https://www.mouser.com/c/?q=ESP32-S3-DevKitC-1 "ESP32-S3-DevKitC-1 on Mouser")
- [DigiKey](https://www.digikey.nl/en/products/filter/rf-evaluation-and-development-kits-boards/859?s=N4IgTCBcDaIKIGUAKBmMBaBL0BECmAbgNICWALgMLoCMIAugL5A "ESP32-S3-DevKitC-1 on DigiKey")
- [Adafruit](https://www.adafruit.com/?q=ESP32-S3-DevKitC-1&sort=BestMatch "ESP32-S3-DevKitC-1 on Adafruit")
- [MakerFabs](https://www.makerfabs.com/search.html?&search=ESP32-S3-DevKitC-1 "ESP32-S3-DevKitC-1 on MakerFabs")

## The Touchsceen

<img src="https://github.com/DustinWatts/ESP32-S3_TFT_Combiner/blob/main/Assets/ILI9488_with_touch.png" alt="ILI9488 with Touch" width="480"/>

The touchscreen used with this board is a 3.5" ILI9488 TFT with XPT2046 touchcontroller. You can find the screen here: 

- [AliExpress](https://s.click.aliexpress.com/e/_AMAa6B "Buy the ILI9488 with Touch on AliExpress") *
- [Amazon](https://amzn.to/3z2bf3f "Buy the ILI9488 with Touch on AliExpress") *

_* Afilliate link_

***Note: When you but the ILI9488 make sure you select the option "With Touch" if you have the possibility to do so!***

<img src="https://github.com/DustinWatts/ESP32-S3_TFT_Combiner/blob/main/Assets/with_touch.png" alt="ILI9488 select with Touch"/>

## The User_Setup.h

The User_Setup.h file in the folder with the same name is the User_Setup.h file you need to use the combiner PCB with the [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI "TFT_eSPI lbrary by Bodmer") lbrary by Bodmer. Overwrite the contents of the original file and TFT_eSPI is now configured for use with the combiner board.

## FreeTouchDeck

<img src="https://github.com/DustinWatts/FreeTouchDeck/blob/master/case/ESP32_TFT_Combiner_Case/freetouchdeck_case1.jpg" alt="FreeTouchDeck" width="720"/>

FreeTouchDeck is currently being updated so it also supports the ESP32-S3. This also includes support for using the ESP32-S3 USB Keyboard HID. You can find the latest version here: https://github.com/DustinWatts/FreeTouchDeck. The updates are not in any release yet, you so you will have to download the source and compile it yourself. Hopefully this the next release will include ESP32-S3 support.

## The Case
<img src="https://github.com/DustinWatts/FreeTouchDeck/blob/master/case/ESP32_TFT_Combiner_Case/FreeTouchDeck_Case.png" alt="3D Printable Case" width="720"/>

The case was originally designed for the ESP32 + TFT combiner PCB and for use with FreeTouchDeck. But since the deminsions are the same, the case is also the same. You can find the .stl files to prin your own case in this repo in the folder called "3D Printable Case".

## Support Me

If you like what I am doing you there are a number of ways you can support me. 

<img src="https://github.com/DustinWatts/small_logos/blob/main/twitter_logo.png" alt="Twtter" width="24"/> 
You can follow me on Twitter: [@dustinwattsnl](https://twitter.com/dustinwattsnl "Follow me on Twitter")

<img src="https://github.com/DustinWatts/small_logos/blob/main/youtube_logo.png" alt="YouTube" width="32"/> 
You can subscrive to my channel on Youtube: [/dustinWatts](https://www.youtube.com/dustinwatts "Subscrive to my YouTube channel")

<img src="https://github.com/DustinWatts/small_logos/blob/main/patreon_logo.png" alt="Patreon" width="32"/> 
You can support me by becoming a Patron on Patreon: https://www.patreon.com/dustinwatts

<img src="https://github.com/DustinWatts/small_logos/blob/main/paypalme_logo.png" alt="PayPal.me" width="32"/> 
You can also make a one time donation using PayPal.me: https://www.paypal.me/dustinwattsnl
