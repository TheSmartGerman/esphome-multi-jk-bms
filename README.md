# esphome-multi-jk-bms
Use ESPHome JK BMS Multible with split config

Based on this: https://github.com/syssi/esphome-jk-bms -> esp32-ble-v14-multiple.yaml (JK PB Inverter BMS)

Just split the YAML file into more files, this makes it easier when using more BMS.

This code uses a M5 Stack S3Lite as target HW

https://docs.m5stack.com/en/core/AtomS3%20Lite

Benefits:
- Nice Format, comes with a housing.
- RGB Adressable LEDs for Status Display
- Button for User Actions
