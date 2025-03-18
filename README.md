# esphome-multi-jk-bms
Use ESPHome JK BMS Multible with split config

Based on this: https://github.com/syssi/esphome-jk-bms -> esp32-ble-v14-multiple.yaml (JK PB Inverter BMS)

Just split the YAML file into more files, this makes it easier when using more BMS.

This cuts the main yaml in round 100 lines.

Just define your substitutions:
```
 name: esp32-jk-pb-bms
  bms0: "${name}-0"
  bms0_mac_address: c8:47:80:11:86:xx
  bms0_protocol_version: JK02_32S
```

And include multible bms:

```
  multiple_bms_0: !include 
    file: includes/inc_esp32-ble-v14-multiple.yaml
    vars: 
      id: 0
      name: ${bms0}
      bms0_mac_address: ${bms0_mac_address}
      bms0_protocol_version: $s{bms0_protocol_version}
```

This code uses a M5 Stack S3Lite as target HW

https://docs.m5stack.com/en/core/AtomS3%20Lite

Benefits:
- Nice Format, comes with a housing.
- RGB Adressable LEDs for Status Display
- Button for User Actions
