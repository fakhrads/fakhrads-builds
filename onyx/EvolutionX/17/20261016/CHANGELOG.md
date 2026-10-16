# Evolution X 12.3 for POCO F7 (onyx): build 20261016

Android 17 · Unofficial · by Fakhri

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261016/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.3 on Android 17, Google apps included
- Vendor blobs and firmware updated to HyperOS OS3.0.303.0.WOLMIXM (the zip flashes the firmware)
- Dolby Atmos for speaker and headset (LunarisDolby)
- Xiaomi Camera (MiuiCamera)
- New: Bypass Charging Quick Settings tile, no root needed
  - **Smart**: charges to 80%, then the phone runs from the charger; charging resumes at 77%
  - **Bypass**: holds the current battery level (minimum 70%) while plugged in; turns itself off after a reboot
- NotGameTurbo (game turbo)
- XiaomiParts device settings
- Xiaomi haptics (vibratorfeature HAL)
- HyperOS auto-brightness ramp rate
- Fixed Termux apt failures (devpts / ptmx)
- Signed with private release keys

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
