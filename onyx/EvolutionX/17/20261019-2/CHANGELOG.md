# Evolution X 12.3 for POCO F7 (onyx): build 20261019

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261019-2/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Fix USB drives formatted as exFAT showing as "needs formatting": a cleanly
  ejected drive now mounts right away instead of failing the slow disk check
  over the USB 2.0 port (large drives with many files)
- Fix flicker at low brightness with adaptive refresh rate: the screen now
  stays at 60 Hz when brightness is very low
- Fix touch not working in recovery
- Wi-Fi Calling toggle for Indosat, XL, Tri and Smartfren (Telkomsel already
  had it), and for more carriers in Southeast and South Asia (Singapore,
  Vietnam, Cambodia, Myanmar, Sri Lanka, Pakistan, Bangladesh, Nepal), plus
  a fix for carrier settings that never applied because of how their network
  codes were written
- NotGameTurbo: also detects games that don't declare themselves as games
  (Unity, Unreal, Godot and Cocos games, or apps with Play Games), so they get
  the game thermal profile. Apps that declare another category are left alone
- NotGameTurbo: Indonesian translation
- Dolby: fix the headphone surround strength slider not moving
- Latest Evolution X sources

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
