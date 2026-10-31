# Custom Z-Wave Firmware

Open-source replacement firmware for Z-Wave 700 series devices (Silicon Labs ZGM130S / EFR32ZG13), unlocked and reflashed over SWD with a J-Link.

## Why

Z-Wave 700 series chips have the hardware support for **Z-Wave Long Range**, but many 700 series devices shipped with firmware that lacks the software component. The goal of this project is to update these devices to **Z-Wave SDK 7.21.8** (released August 2026) to add Z-Wave Long Range support, fix bugs, and add new features.

Goals for every device:
- Z-Wave Long Range on SDK 7.21.8
- Works with Home Assistant / Z-Wave JS
- Instant reporting (Central Scene, Notification, etc.) instead of slow polling

## Devices

| Manufacturer | Device | Folder | Status |
|---|---|---|---|
| Ring | Alarm Keypad (2nd Gen) | [Ring/Keypad-Gen2](Ring/Keypad-Gen2) | ✅ Working (v2.0) |
| Zooz | ZEN17 Relay | [Zooz/ZEN17](Zooz/ZEN17) | 🔍 Reverse engineering |
| Kwikset | 620 Smart Lock | [Kwikset/620](Kwikset/620) | 🔍 Reverse engineering |
| NEO Coolcam | 4-in-1 Door/Window Sensor | [NEO-Coolcam/Door-Sensor-4in1](NEO-Coolcam/Door-Sensor-4in1) | 🛠️ In progress |
| NEO Coolcam | NAS-RP01Z1 Plug-in Temp Sensor / Repeater | [NEO-Coolcam/NAS-RP01Z1](NEO-Coolcam/NAS-RP01Z1) | 🔍 Reverse engineering |

## Folder layout

```
Manufacturer/
  Device/
    README.md      <- pinout, status, how to build and flash
    firmware/      <- source code
    tools/         <- test/diagnostic firmware, scripts
    zwave-js/      <- Z-Wave JS device config files (if needed)
```

## Toolchain

- Simplicity Studio 5 (Series 1 / 700-series chips are not supported in Studio 6)
- Z-Wave SDK 7.21.8 (Long Range is enabled by selecting a Long Range region, such as US_LR, in the region config header)
- SEGGER J-Link for SWD flashing

## ⚠️ Warning

Unlocking a chip usually **erases the original firmware permanently**. Back up anything you can first, and only do this on hardware you're willing to lose.

## License

MIT, see [LICENSE](LICENSE). Files that started from Silicon Labs sample code keep their original license.
