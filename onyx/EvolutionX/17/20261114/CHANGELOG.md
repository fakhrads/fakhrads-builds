# Evolution X 12.4 for POCO F7 (onyx): build 20261114

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261114/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

### Calls
- Fixed the robotic "derrt" crackle on WhatsApp calls through the earpiece when the other person
  talks loudly or at a high pitch. Xiaomi's VoIP earpiece volume boost is now switched off, as
  HyperOS does, also when a call moves to the earpiece from the speaker or Bluetooth
- At the top call volume steps, only the loudest peaks of VoIP calls on the earpiece are softened,
  so voices stay clean without making calls quieter. Lower volume steps are untouched

### Wi-Fi
- Wi-Fi driver updated to Qualcomm WLAN.LA.1.0.r1-09900 (was 09600)
- The hotspot can use HE MU beamforming when the Wi-Fi firmware supports it
- With the screen off and no Wi-Fi connection, the phone scans for saved networks half as often,
  which saves battery

### Bluetooth
- LE Audio (LC3) can now be turned on: pick unicast or broadcast in the LE Audio mode setting in
  Developer options, then reboot. It stays off by default, so earbuds keep using aptX Adaptive
  until you switch

### Kernel
- 169 upstream stability and security fixes merged from the LineageOS SM8750 kernel, including
  f2fs, Bluetooth and networking

### ZeroEngine and Bypass Charging
- Translated into 26 more languages, and the Indonesian translation is now complete
- ZeroEngine: the text on the main card stays readable with light wallpaper colors

### Zero Launcher
- Recents updates from AOSP (through Infinity-X): screen readers announce Recents every time it
  opens, and a task without a description is read out by its title


## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
