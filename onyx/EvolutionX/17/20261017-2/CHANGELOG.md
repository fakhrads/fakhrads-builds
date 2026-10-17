# Evolution X 12.3 for POCO F7 (onyx): build 20261017

Android 17 · Unofficial · by Fakhri

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261017-2/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.3 on Android 17, Google apps included
- Synced with the latest Evolution X sources (October 18)
- Faster fingerprint unlock from screen off: the screen no longer turns off and on again before
  unlocking (about 0.5 s quicker when Always-on Display is off)
- Smoother UI: enabled ADPF performance hints for apps, SystemUI and SurfaceFlinger, so the CPU ramps up
  per frame when it is needed instead of running at full speed
- Less stutter when pulling down the notification shade and Quick Settings (SystemUI dropped frames
  went from about 9% to under 4%)
- Snappier response while touching the screen (touch boost for the foreground and top app)

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
