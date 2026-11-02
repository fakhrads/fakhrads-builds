# Evolution X 12.3 for POCO F7 (onyx): build 20261102-2

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261102-2/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.3 on Android 17, Google apps included

### System & Launcher
- **Zero Launcher is back**: replaces the Pixel launcher, updated from Infinity-X, with Quickspace (date and weather) on the home screen.
- Recents and gesture navigation run in Zero Launcher.
- The Google feed and Google's At a Glance are gone with the Pixel launcher. Coming from the Pixel launcher, the home screen layout may need to be set up again.

### Display & Auto brightness
- **HyperOS auto brightness**: the brightness policy is ported from stock HyperOS (hysteresis and touch cover
  protection), so auto brightness reacts like on stock.
- **Game scene**: while a ZeroEngine game is open, auto brightness does not dim just because your hand covers the front sensor.
- **Dual light sensors**: the rear and front sensors are combined in the same time base, and the brightness
  holds when the front sensor is covered indoors instead of dropping.

### ZeroEngine & Gaming
- **5 thermal modes**: Ultra Cool Battery, Normal, Normal but not Normal, Performance and Ultra Performance (bypass).
- **5 KProfiles modes**: Cool Battery, Battery, Balance, High Performance and Ultra High Performance. The stored
  mode is reset to Balance once after the renumbering, and Bypass goes back to Auto on boot.
- **Per-app thermal profiles**: pick a thermal mode for each app, or let it follow the global one. Profiles of
  uninstalled apps are removed, and the app list no longer crashes.

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
