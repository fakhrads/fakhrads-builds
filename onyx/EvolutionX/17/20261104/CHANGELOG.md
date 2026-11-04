# Evolution X 12.3 for POCO F7 (onyx): build 20261104

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261104/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.3 on Android 17, Google apps included

Changes since 2 November 2026:

### Device tree
- onyx: DualSensorPolicy: Feed rear samples in the ring buffer's time base
- onyx: DualSensorPolicy: Hold the ambient lux when the front ALS is covered indoors
- onyx: Port the HyperOS auto brightness policy
- onyx: Port the HyperOS game scene of auto brightness
- onyx: Track touch cover on its own thread
- onyx: Ship Zero Launcher
- onyx: audio: Load the SIA ACDB on units with SIA smart amps
- onyx: Patch the auto brightness nits splines to linear like HyperOS
- onyx: Patch the landscape Dynamic Island window to a trusted overlay
- onyx: Drop the biometric wake and unlock patch, it is upstream
- onyx: Let BypassCharging vote on the MCA charge enable node

### Kernel
- kprofiles: Boot into Balance (3) after the 5-tier renumbering
- display-drivers: sde_kms: Follow the 5-tier KProfiles numbering
- onyx: Give the camera and audio overlay labels onyx-only names

### ZeroEngine
- ZeroEngine: Fix KProfiles default and bypass reset after the mode renumbering
- AppProfilesActivity: Use the framework SearchView
- MainFragment: Keep the hero card colors under Settings Expressive
- ZeroEngine: Redesign in Compose like LunarisDolby
- ZeroEngine: Add a system monitor
- ChargingUi: Show the power while bypass is on
- ChargingUi: Describe bypass without the charging control limit
- ZeroEngine: Keep the CPU profile on the Normal thermal modes

### BypassCharging
- SettingsFragment: Keep the hero card colors under Settings Expressive
- BypassCharging: Redesign in Compose and let ZeroEngine control it
- ChargingUi: Show the power while bypass is on
- BypassCharging: Bypass through the MCA charge enable vote

### Zero Launcher
- Launcher3: Update to the Infinity-X 17 snapshot of 2026-10-29
- Launcher3: Build the Quickstep app as ZeroLauncher
- Launcher3: Tint themed icon backgrounds with the system theme
- Launcher3: Vibrate when opening the app drawer
- Launcher3: Show ZRAM in the recents memory info

### LunarisDolby
- dolby: Add more DAP controls, Sound Lab and a new home screen
- dolby: Sound Lab: 10 band EQ, headphone correction and precision mode
- dolby: Sound Lab: Keep the compressor stage enabled
- dolby: Sound Lab: Do the loudness boost in DynamicsProcessing

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
