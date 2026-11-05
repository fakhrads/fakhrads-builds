# Evolution X 12.4 for POCO F7 (onyx): build 20261105

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261105/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

### Device tree
- onyx: Drop the wet touch property trigger
- onyx: Hand the Expert mode nodes to the system user
- onyx: power: Add a hint for the ZeroEngine sched boost
- onyx: Let init turn wet touch rejection off
- onyx: Drop the Dynamic Island trusted overlay patch, it is upstream

### ZeroEngine
- ZeroEngine: Switch wet touch through the touchfeature HAL
- ZeroEngine: Add an Expert mode for the kernel knobs
- ZeroEngine: Expert mode: Show the sched boost ZeroEngine holds
- ZeroEngine: Turn wet touch off through the device tree

### Zero Launcher
- Launcher3: Revamp settings to Jetpack Compose M3 Expressive Bento UI
- Launcher3: Fix Compose settings and port the missing preferences
- Launcher3: Optimize performance and fix CTS haptic vibration on swipe-up
- Launcher3: Allow Circle to Search from anywhere on the nav bar
- Launcher3: Open Circle to Search from the corner swipe
- Launcher3: Add optional bouncy animations
- Launcher3: Add strength and speed sliders for bouncy animations
- Launcher3: Keep themed icons during launch and drag animations
- Launcher3: Add haptic feedback on icon taps

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
