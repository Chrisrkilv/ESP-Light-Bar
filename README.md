# ESP-Light-Bar

## Summary
Light Bar that connects to a hub housing an ESP32-C3 for control via ESPHOME or WLED
A simple light bar derived from my lamp design - https://www.thingiverse.com/thing:6421767

## Parts Needed
WS2811/WS2812/WS2812B or WS2813 (250mmr 5V) LED Strip - https://amzn.to/3Havtuk
Cable with at least 3 conductors with the outer diameter being no more than 3.5mm (an old USB cable is perfect. I didn't have one long enough so purchased this -
ESP32 Module (I used ESP32-C3-Supermini) - https://amzn.to/3vsUU7Z
JST Connectors & Crimping Tool -
(You can also use JSTS Connectors, I have included a file for this)

## Print Settings
Light Bar & End Cap - 0.20 Layer Height. 

Print Upright with no supports and at least 75% infill If using a lighter colour filament to ensure minimum light leakage.
If you have a multi-filament printer you could even print the infill in a darker colour to contain the light.
Diffuser - 100% Infill - 0.20 Layer, Print Flat

Skadis Mount - 25% Infill, 0.20 Layer, Supports On

### Light Bar
The light bar will accommodate an LED strip up to 250mm, I used an LED strip with 60 LED's Per Meter which ends up being 14 LED's in the light bar total.

### Mount
I have designed the mount to simply friction slot into the back of the light bar whilst also wedging the wire in place so there's no need for any glue or screws. The End Cap is also friction mounted.
Due to the nature of the mount design you could remix this to create a mount for almost anything and just slot it in, file fusion 360 files are included.
### Hub
I didn't want to have to run a separate ESP chip for every single light bar so I designed a central hub with connectors. This houses an ESP32-C3 Supermini and multiple 4 pin 3JST connections that are numbered. Number 1 is the main segment, the data pin of number one carries over to number 2 and so on and so fourth. Technically this could go on forever if you have a big neough power supply.

That way I can connect up to three light bars at once but still have individual control of them using segments and also power all three of them from one >2.5A 5v Power supply over USB.
