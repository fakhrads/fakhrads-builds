# Evolution X 12.3 for POCO F7 (onyx): build 20261024

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261024/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog
## 2026-10-24

### Kernel & Power
- **KProfiles & Sultan Boost**: Implemented in-tree KProfiles driver and Sultan display pre-commit boost for predictive frame scheduling.
- **SD8s Gen 4 Sweet Spot**: Capped daily CPU boost to TSMC 4nm efficiency knee (Little 1.28 GHz, Mid 1.92 GHz, Prime 2.51 GHz) for cooler daily usage (32–35°C) without losing 120Hz smoothness.
- **Battery Drain Fix**: Fixed infinite CPU boost loop caused by `Duration: 0` in Power HAL interaction hints (set to finite 120ms).
- **Kernel Permissions**: Fixed `BUILD_BUG_ON_ZERO` compile errors on sysfs nodes; delegated userspace permissions safely via init and SELinux.

### ZeroEngine & Gaming
- **KProfiles Orchestration**: Integrated mode switching (Battery / Balanced / Performance) directly inside ZeroEngine.
- **480Hz Touch Report**: Implemented Novatek THP Super Report Rate (mode 1011) during gameplay with safe reset to 120Hz on exit.
- **Stability Fixes**: Consolidated Service lifecycle hooks (`onDestroy`) and resolved UI preferences crashes.

### Charging & Haptics
- **MCA 90W Unblock**: Unlocked `ichg_limit` sysfs control and expanded SELinux policy for BypassCharging.
- **Haptics Retune**: Smoothed out slider haptic intensity (`LIGHT_TICK` and `LOW_TICK` gains).

### System & Launcher
- **Zero Launcher**: Morphed Launcher3QuickStep to Zero Launcher (`com.google.android.apps.nexuslauncher`).
- **PiP Smoothness**: Added patch to ignore refresh rate restrictions during PiP / pinned window multitasking.

---

## 2026-10-23

### Display & Visuals
- **UDFPS**: Added custom fingerprint icon and animation support on Evolution X.
- **Refresh Rate**: Dropped lockscreen refresh lock; restricted 60Hz enforcement only to ultra-low brightness to prevent panel flicker.
- **Fixes**: Resolved Instagram HDR crash on virtual displays and eliminated `qesdk-secmanager` seccomp crash-loop.

### Multitasking & Freeform
- **Mi Freeform**: Added gesture handles and dynamic drawing-size resize inside ZeroEngine.
- **Launcher Bridge**: Added broadcast receiver to launch floating apps directly from the recents overview.

### System Optimization
- **Log Spam & Performance**: Fixed audio HAL mutex spam, populated missing task profiles, and enabled async notification inflation.
- **Thermal Baseline**: Initial tuning for touch boost hold-time and set default game profile to Balanced.

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
