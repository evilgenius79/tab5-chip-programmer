# Tab5 Chip Programmer

Standalone CH341-class programmer. **M5Stack Tab5** is the brain. An **M5-Bus hat** is the socket, rails, and clip.

Full source is in the project zip from the design session; this repo is the public home.

## What it programs

| Family | How it is chosen |
|---|---|
| SPI NOR (W25Q, GD25, MX25, EN25, N25, S25FL) | Auto: JEDEC 0x9F + SFDP |
| I2C EEPROM 24Cxx | Auto: scan 0x50-0x57 |
| Microwire 93C46/56/66/86 x8 or x16 | Manual family dropdown |

## Build

ESP-IDF 5.4+ target esp32p4. See firmware/ after you clone a complete tree.

```bash
cd firmware
idf.py set-target esp32p4
idf.py build
idf.py -p PORT flash monitor
```

## Safety

Target VCC off until Detect. 5 V is never automatic. Do not use G31/G32 for 24xx.

MIT.
