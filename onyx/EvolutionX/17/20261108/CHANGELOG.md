# Evolution X 12.4 for POCO F7 (onyx): build 20261108

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261108/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

- Evolution X 12.4 on Android 17, Google apps included

### Device tree
- onyx: Remove obsolete SurfaceFlinger properties
- onyx: Drop debug.sf.latch_unsignaled property
- onyx: Disable the property debug.sf.enable_gl_backpressure
- onyx: wifi: Turn firmware roaming off while the device idles
- onyx: wifi: Stop qcacld holding qcom_rx_wakelock for RX unicast packets
- onyx: hand the GPU ceiling to system, like the floor already is

### ZeroEngine
- ZeroEngine: the panel floats beside a dock, and the music card follows the player
- ZeroEngine: a narrower game panel, with the battery's temperature and power on it
- ZeroEngine: the most specific thermal setting wins, and the screens say so
- ZeroEngine: charging mode is one choice, Off, Smart or Bypass
- ZeroEngine: a switch follows a tap now, not the next temperature poll
- ZeroEngine: a game that ends badly no longer leaves heads-up notifications off
- ZeroEngine: the panel stops jumping to the top, and stops being nearly the whole screen
- ZeroEngine: one switch for the panel, and it lives in the app
- ZeroEngine: the tuning screen shows the choice you just made
- ZeroEngine: the panel keeps its settings, the connection figures become a notification
- ZeroEngine: the connection notice runs from the engine, not from the overlay
- ZeroEngine: no beacon, no strip, no card, just the panel
- ZeroEngine: give the HUD back its switch, inside the panel
- ZeroEngine: put the edge handle back
- ZeroEngine: move the music player inside the panel
- ZeroEngine: read the GPU load the kgsl driver actually publishes
- ZeroEngine: the per-game refresh rate leaves nothing behind
- ZeroEngine: Read the battery from what is actually available
- ZeroEngine: Battery notification laid out like a battery app
- ZeroEngine: Battery in the shade, and a recording that keeps up with the panel
- ZeroEngine: Telemetry, session reports and a real screen pipeline
- ZeroEngine: Close the gaps the audit found
- monitor: the floating monitor stays, with an opacity of its own
- battery: a refresh rate a game leaves behind is put back on the next boot
- tuning: only undo a rate that is still ours
- tuning: take the notification listener off the all-day payroll
- danmaku: the listener keeps its grant, and only leaves the list
- ping: rewrite PingMonitor to avoid /proc/net

### Zero Launcher
- Launcher3: the Lens chip does not take the launcher down with it
- Launcher3: keep the Lens chip, and keep Lens on it
- Launcher3: one motion system, one translucency scale
- Launcher3: Hand the corner swipe to Circle to Search without the hold
- Launcher3: Launch the assistant the user actually picked

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
