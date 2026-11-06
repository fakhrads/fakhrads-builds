# Evolution X 12.4 for POCO F7 (onyx): build 20261106

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261106/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.4 on Android 17, Google apps included
- Fix CTS only launcher3
- Add haptic to volume button
- Fix & optimized launcher3

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
