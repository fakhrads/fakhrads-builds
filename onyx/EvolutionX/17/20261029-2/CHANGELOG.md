# Evolution X 12.3 for POCO F7 (onyx): build 20261029

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261029-2/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Dolby Vision: playback now works, including profile 5 (correct colors)
- Audio: the Qualcomm audio stack is now built from source instead of Xiaomi blobs
  - Fixed A2DP going silent after the Bluetooth codec is reconfigured
  - Fixed no sound in VoIP calls (WhatsApp and similar)
  - Fixed Dolby Atmos (Lunaris Dolby) failing to start
  - Louder speaker volume curve for media (max volume unchanged)
- Display: added "High touch sensitivity" (glove mode) and "High touch polling rate" in Settings > Display
- Performance: smoother notification shade pull-down (SystemUI no longer floods system_server on every frame)
- Performance: thermalbreak boosts touches in the normal profile again, short touches only, so the phone runs cooler while scrolling; game boosts stay above the normal ones
- Freeform: the "Freeform" option in Pixel Launcher recents now opens apps in a floating window (LMOFreeform)
- ZeroEngine: the temperature list no longer jumps back to the top and now has a graph
- ZeroEngine: the high touch polling rate stays on after leaving a game
- SELinux: fixed audio, MiEvent and authsecret denials

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
