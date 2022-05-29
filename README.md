Todo before going public:

- [ ] Photo PCB
- [ ] Image screen
- [ ] Image DevKit
- [ ] Share PCB on PCBWay
- [x] Complete List of GPIO's used
- [ ] Make Tindie Listing for PCB + Headers


# ESP32-S3-DevKitC-1 + Touchscreen Combiner PCB
A PCB making it easy to combine an ESP32-S3-DevKitC-1 and an ILI9488 TFT + XPT2046 Touchsceen.

## The PCB

The PCB is designed in KiCad and uses 22-pin double row headers for the ESP32-S3 so you can use the GPIO's not used by the screen. It uses a 14-pin header for the screen and a 4-pin header for the SD card.

Pins used by the screen, touchcontroller and SD card are:

|GPIO|Function|
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

## The ESP32

The ESP32 for this board is the ESP32-S3-DevKitC-1. Which is currently sold by:
- [Mouser](https://www.mouser.com/c/?q=ESP32-S3-DevKitC-1 "ESP32-S3-DevKitC-1 on Mouser")
- [DigiKey](https://www.digikey.nl/en/products/filter/rf-evaluation-and-development-kits-boards/859?s=N4IgTCBcDaIKIGUAKBmMBaBL0BECmAbgNICWALgMLoCMIAugL5A "ESP32-S3-DevKitC-1 on DigiKey")
- [Adafruit](https://www.adafruit.com/?q=ESP32-S3-DevKitC-1&sort=BestMatch "ESP32-S3-DevKitC-1 on Adafruit")
- [MakerFabs](https://www.makerfabs.com/search.html?&search=ESP32-S3-DevKitC-1 "ESP32-S3-DevKitC-1 on MakerFabs")

## The Touchsceen

The touchscreen used with this board is a 3.5" ILI9488 TFT with XPT2046 touchcontroller. You can find the screen here: https://s.click.aliexpress.com/e/_AMAa6B *

_* Afilliate link_

## The User_Setup.h

The User_Setup.h file in the folder with the same name is the User_Setup.h file you need to use the combiner PCB with the [TFT_eSPI](https://github.com/Bodmer/TFT_eSPI "TFT_eSPI lbrary by Bodmer") lbrary by Bodmer. Overwrite the contents of the original file and TFT_eSPI is now configured for use with the combiner board.

## FreeTouchDeck

FreeTouchDeck is currently being updated so it also supports the ESP32-S3. This also includes support for using the ESP32-S3 USB Keyboard HID. You can find the latest version here: https://github.com/DustinWatts/FreeTouchDeck. The updates are not in any release yet, you so you will have to download the source and compile it yourself. Hopefully this the next release will include ESP32-S3 support.

## The Case

The case was originally designed for the ESP32 + TFT combiner PCB and for use with FreeTouchDeck. But since the deminsions are the same, the case is also the same. You can find the .stl files to prin your own case in this repo in the folder called "3D Printable Case".
