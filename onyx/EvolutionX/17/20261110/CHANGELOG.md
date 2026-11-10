# Evolution X 12.4 for POCO F7 (onyx): build 20261110

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261110/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

### Bluetooth audio
- New: aptX Adaptive for headphones that support it, including the newer release 2.2 mode
- New: Bluetooth codec settings inside Dolby Sound Lab (codec, sample rate, bit depth, LDAC quality,
  LHDC options, AAC variable bit rate), the same choices as Developer options but easier to reach
- Qualcomm high speed links (QHS) are now switched on for Bluetooth classic and LE audio

### Performance and battery
- Balance profile and below: the screen no longer pushes the CPU to a high speed on every frame, to
  save battery. High Performance and Ultra High Performance still do it
- Kernel tick changed from 250 Hz to 300 Hz, which lines up with the screen refresh
- Fixed a kernel boost bug where a boost request could be missed
- Fixed a touch boost that could get stuck in a busy loop after the touch driver restarted
- Removed power settings that did nothing (old camera and app launch hints)

### ZeroEngine
- Fixed screen recording and the replay buffer ending with "Nothing was recorded"
- "No limits" now uses the Ultra High Performance profile only while the screen is on. With the
  screen off the phone goes back to the profile you picked, so it does not idle at full power all night
- If ZeroEngine stops in the middle of a game, the refresh rate and screen resolution are put back to
  normal when it starts again
- Auto bypass charging in games no longer turns off a bypass that you switched on yourself
- "Apply at boot" in Expert mode no longer turns itself off when ZeroEngine restarts shortly after boot
- The battery notification is no longer refreshed while the screen is off
- Fixed a crash that could happen when moving the monitor opacity slider
- Other apps can no longer ask ZeroEngine to open floating windows (security fix)
- Expert mode now explains that the performance governor and full sched boost can lower benchmark scores

### Bypass Charging
- Bypass charging that you turn on right after the phone starts is no longer switched off a moment later

### Zero Launcher
- New funny messages in Quickspace (English and Indonesian), plus a few heartbroken ones for people like me

### Security
- The volume down key device is no longer open to every app

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
