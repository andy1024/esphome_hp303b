# esphome_hp303b
An ESPHome custom sensor component for the HP303B barometric pressure sensor.

An example of how to use this file is below:

```yaml
esphome:
  name: wemos-vindriktning
  platform: ESP8266
  board: d1_mini
  libraries:
    - "Wire"
    - "SPI"
    - git@github.com:far6/LOLIN_HP303B_Library.git
  includes:
    - hp303b.h

  
sensor:
  - platform: custom
    lambda: |-
      auto hp_sensor = new HP303BSensor();
      App.register_component(hp_sensor);
      return {hp_sensor};

    sensors:
      name: "Barometric Pressure"
      icon: "mdi:gauge"
      unit_of_measurement: hPa
      accuracy_decimals: 1
```
