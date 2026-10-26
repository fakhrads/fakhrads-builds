# Evolution X 12.3 for POCO F7 (onyx): build 20261026

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261026-2/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.3 on Android 17, Google apps included

## 2026-10-26

### Kernel & Power
- **KProfiles now steers the scheduler**: Battery caps the CPU clusters, Balanced holds them at the efficiency knee, Performance is uncapped.
- **Touch boost retuned**: cooler everyday use, with the boost dropped as the phone heats up and ending 500 ms after the last touch.
- **120 Hz at low brightness**: the display no longer drops to 60 Hz.

### ZeroEngine & Gaming
- **Bullet notifications (Danmaku)**: chat messages float over the game, and heads-up banners are silenced while you play.
- **Lock gestures in games**: block the status bar and the navigation gestures while a game is open.
- **Floating windows**: now handled by LMOFreeform, with corner resize and no ghost handles.
- **Touch report rate**: high touch report is per game only. The global switch is gone.
- **Temperatures**: new screen with the battery, board, CPU and every other sensor.
- **New look**: ZeroEngine and BypassCharging follow the Material 3 Expressive style.

### Charging
- **BypassCharging**: redesigned page with a live hero card and temperatures.

### System & Launcher
- **Zero Launcher removed**: back to the Pixel launcher.

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
