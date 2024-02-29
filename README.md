# ESP-Light-Bar

## Summary
A Light Bar that connects to a hub housing an ESP32-C3 for control via ESPHOME or WLED

## See thingiverse for print settings/assembly
A simple light bar derived from my lamp design - https://www.thingiverse.com/thing:6421767

### LED's
The light bar will accommodate an LED strip up to 250mm, I used an LED strip with 60 LED's Per Meter which ends up being 14 LED's in the light bar total.

### ESPHOME
The provided ESPHome code is straightforward. It utilizes the NeopixelBus light component. Simply specify the number of LEDs you’re using. By default, the main light component is hidden using the “internal” option. We’ll then segment this main component into multiple other lights based on your preferences.

```
light:
  - platform: neopixelbus
    type: GRB
    variant: WS2811
    pin: GPIO3
    num_leds: ENTER_NUMBER_OF_LEDS
    name: "Hub"
    id: esphub
    internal: true
```

When configuring the partition segment for your LED strips, start with the first LED strip plugged into port 1 on the hub. Keep in mind that the first LED should be “0”. For example, if you have 14 LEDs, the last LED would be labeled as 13. The first LED on your next segment would then be labeled as 14, and so on.

```
- platform: partition
  name: "FRIENDLY_NAME"
  segments:
    # Use first 10 LEDs from the light with ID light1
    - id: esphub
      from: 0
      to: LAST_LED_ON_THIS_STRIP

- platform: partition
  name: "FRIENDLY_NAME"
  segments:
    # Use first 10 LEDs from the light with ID light1
    - id: esphub
      from: FIRST_LED_ON_THIS_SEGMENT
      to: LAST_LED_ON_THIS_SEGMENT`
```
### WLED

WLED is straightforward: flash your ESP device with WLED and create your segments. The wiring diagram uses the default GPIO pin that WLED employs, making it cross-compatible. Additionally, WLED starts with LED “0,” ensuring consistent numbering similar to ESPHome.

https://kno.wled.ge/features/segments/

