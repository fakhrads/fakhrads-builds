# Evolution X 12.3 for POCO F7 (onyx): build 20261031

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261031/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.3 on Android 17, Google apps included
- Implement OEM-grade DualSensorPolicy fusing rear ALS (sip1328) with front under-display sensor
- Fix auto-brightness hunting and 0-lux dropouts on bright/white content (CWB compensation collapse)
- Add shade and tree protection to prevent sudden brightness spikes in shadowed environments
- Synchronize fast and slow ambient lux buffers to eliminate abrupt dimming transitions
- Add physical occlusion heuristic (auto-bypasses rear sensor when phone is flat on desk/bed, in motorcycle mounts, or during gaming grip)
- Add direct sunlight override (>= 8000 lux) for instantaneous High Brightness Mode (HBM) trigger
- Add camera flashlight/torch interlock with 1000ms cooldown to prevent sensor blinding
- Fully event-driven sensor listening with 0% idle battery drain (no accelerometer/IMU polling)
- Add dedicated DualSensorPolicy logcat tag and dumpsys display telemetry support

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
