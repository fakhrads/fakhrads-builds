# Evolution X 12.3 for POCO F7 (onyx): build 20261017

Android 17 · Unofficial · by Fakhri

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261017/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.3 on Android 17, Google apps included
- Upstreamed OSS Kernel to 6.6.144
- Offline Charging
- OTA Update

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
