# Geekworm x1202 UPS
Home Assistant Geekworm x1202 HACS Addon based on Home Assistant Geekworm x720 Addon from user Beduir https://github.com/Beduir/x720.git and Home Assistant Geekworm x750 Addon from user dincojazz https://github.com/dincojazz/Geekworm_x750

Сompatibility:
https://geekworm.com/products/x1202

![pic1](https://github.com/user-attachments/assets/33c2b31a-afe6-4330-92fe-7b1a4b3a384c)


configuration.yaml:

sensor:
   - platform: x1202
   name: 'RPi Battery'

Card in home assistant :

type: entities
entities:
   - entity: sensor.rpi_battery_voltage
   - entity: sensor.rpi_battery_capacity
   - entity: binary_sensor.ups_status
   - entity: binary_sensor.ups_charging
   - entity: update.geekworm_x1202_ups_for_raspberry_pi_update
title: Geekworm X1202 UPS

The 2 binary sensors come from HACS addon https://github.com/thecode/ha-rpi_gpio
And in configuration.yaml:

binary_sensor:
   - platform: gpio
      sensors:
      - port: 6
      name: "UPS Status"
      unique_id: "gpio_sensor_port_6"
      invert_logic: true
      - port: 16
      name: "UPS Charging"
      unique_id: "gpio_sensor_port_16"
      invert_logic: true
