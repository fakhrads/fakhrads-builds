# Evolution X 12.3 for POCO F7 (onyx): build 20261022

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261022/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- ZeroEngine (new): replaces NotGameTurbo and GameSpace. Game panel, per-game touch and thermal settings, new UwU icon.
- ZeroEngine floating apps: each app runs on its own virtual display in a window you can drag, resize, minimize, send to full screen or close. The game underneath is never touched.
- Charging management (new): BypassCharging is now in Settings > Battery.
- Cool charging: lowers the charge current as the battery warms up (10 A at 40 °C, down to 2.5 A at 43 °C).
- Fixed the fast charging power limit and cool charging cancelling each other.
- Haptics: new vibrator HAL with composition primitives and Pixel-style strengths. Fixed doubled and cut waveforms, loads the factory f0 calibration, plays ticks on the waveform closest to resonance.
- Thermal: onyx-thermalbreak lifts the normal profile's limits while touching, and the game profile's when it throttles.
- Display: calmer auto brightness. 90 Hz is held at low brightness to stop refresh rate flicker.
- Calls: fixed VoIP call volume dropping when a notification arrives (the beep now uses USAGE_ASSISTANCE_SONIFICATION).
- Calls: VoWiFi for Airtel and Teletalk (Bangladesh). HD and Wi-Fi calling icons show by default.
- SystemUI: fixed the screen-off unlock with the fingerprint sensor on the screen.
- Camera: hid the broken Pro mode RAW picture format.
- Dolby: no more crash at boot when the saved state can't be applied.

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
