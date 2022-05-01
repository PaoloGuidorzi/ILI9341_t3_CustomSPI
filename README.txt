Modified version of ILI9341_t3 with SPI clock speed setting
By default ILI9341_SPICLOCK was defined 30000000 (30 MHz) and ILI9341_SPICLOCK_READ was defined 6500000 (6.5 MHz) but not all TFT displays can manage these speeds, or problems may arise if long wires connect the TFT to Teensy. Lowering ILI9341_SPICLOCK to 15 or 10 MHz usually solves the problem. Also, some TFTs allow a faster speed, up to 35 or 38 MHz or also higher

To set SPI clock, just before TFT begin call, add these 2 lines:

  MyTFT.Selectable_SPICLOCK_SET( CUSTOM_ILI9341_SPICLOCK , CUSTOM_ILI9341_SPICLOCK_READ ); 
  MyTFT.setClock( CUSTOM_ILI9341_SPICLOCK );
  
  MyTFT.begin();  

where CUSTOM_ILI9341_SPICLOCK and CUSTOM_ILI9341_SPICLOCK_READ are the custom SPI clock frequencies in Hz.

------------------------------------------

Discussion regarding the original optimized version by Paul Stoffregen:

http://forum.pjrc.com/threads/26305-Highly-optimized-ILI9341-%28320x240-TFT-color-display%29-library

------------------------------------------

This is a library for the Adafruit ILI9341 display products

This library works with the Adafruit 2.8" Touch Shield V2 (SPI)
  ----> http://www.adafruit.com/products/1651
 
Check out the links above for our tutorials and wiring diagrams.
These displays use SPI to communicate, 4 or 5 pins are required
to interface (RST is optional).

Adafruit invests time and resources providing this open source code,
please support Adafruit and open-source hardware by purchasing
products from Adafruit!

Written by Limor Fried/Ladyada for Adafruit Industries.
MIT license, all text above must be included in any redistribution

To download. click the DOWNLOADS button in the top right corner, rename the uncompressed folder Adafruit_ILI9341. Check that the Adafruit_ILI9341 folder contains Adafruit_ILI9341.cpp and Adafruit_ILI9341.

Place the Adafruit_ILI9341 library folder your arduinosketchfolder/libraries/ folder. You may need to create the libraries subfolder if its your first library. Restart the IDE

Also requires the Adafruit_GFX library for Arduino.
