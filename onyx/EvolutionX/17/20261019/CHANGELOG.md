# Evolution X 12.3 for POCO F7 (onyx): build 20261019

Android 17 · Unofficial · by Fakhri

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261019/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.3 on Android 17, Google apps included
- Thermal profile per app: social apps and everyday use run in Xiaomi's normal
  (cooler) thermal profile, games use the game profile, plus camera, video and
  maps profiles. Choose Automatic, Always normal, Always game or No limits in
  NotGameTurbo
- No limits thermal mode for players with an external cooler (resets after reboot)
- Bypass Charging: new fast charging power limit (5-60 W) and a Pixel-style page
- Brighter, more responsive auto brightness, fitted to the panel's brightness range
- Fewer app reloads and less stutter when opening many apps (memory tuning)
- Smoother scrolling: interaction boost on all CPU clusters
- Fix camera HAL SELinux denials (memory/CPU pressure access)
- Fix NotGameTurbo crashing at boot before the first unlock

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
