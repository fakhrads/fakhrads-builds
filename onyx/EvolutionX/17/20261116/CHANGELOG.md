# Evolution X 12.4 for POCO F7 (onyx): build 20261116

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261116/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

### Performance and thermals
- App launches get a short boost like HyperOS (CPU, LLCC and L3 floors). It stays within the CPU
  profile you picked, so Battery and Cool battery keep their caps
- Games that put all their heavy threads on the prime core (Zenless Zone Zero, for example) can
  now spread them over every big core, through a new onyx-gameaffinity service
- ZeroEngine's Performance profile now runs Xiaomi's game thermal scenario (tgame), and a new
  Heavy profile runs Xiaomi's scenario for the heaviest games, with CPU and GPU free up to 48 °C
- "Normal but not Normal" now runs Xiaomi's per-normal thermal config. Before, it pointed to a
  config the phone does not have. The CPU stays uncapped below 37 °C; the GPU is held a little
  more than in Normal

### Display
- Automatic brightness darkens gradually, like HyperOS

### Fingerprint
- The under-display fingerprint service ignores invalid display events and recovers when the
  display event node goes away, instead of stopping

### System
- Lineage Charging control is removed from Settings > Battery. Bypass Charging replaces it, and
  the two no longer fight over charging
- Removed an old Termux workaround that mounted a second /dev/pts, which could break adb shell
  and root terminals opened early in boot
- The Wi-Fi diagnostics daemon uses Xiaomi's log size limits again

### ZeroEngine
- New layout with three tabs: Games, Panel and Device. Everything shown over a game is on the
  Panel tab
- New quick rail: a slim horizontal bar beside the handle with the frame rate, the profile, four
  tools, pinned apps and the full panel. Long press any button to see its name
- The edge handle follows the game when it rotates the screen. A floating app opened over a game
  no longer ends the game
- Locking the phone mid game no longer resets the game. The resolution, DND and the locks you set
  stay, and the game is only left after 5 minutes away. Starting a recording no longer restarts
  the game either
- Per game advanced settings: its own thermal scenario and CPU profile
- Per game device spoof: show a game another phone and CPU to unlock higher frame rate options
- Resolution scale now applies to the game only, through Android's game mode, instead of
  shrinking the whole screen. Restart the game after changing it
- Screen recording fixes: recordings without game audio are saved, a new recording is no longer
  dropped at once, the replay buffer keeps the last 30 seconds, and it stops when you leave the game
- An audio preset picked in the panel goes away when the game closes
- Danmaku no longer keeps notification access busy outside games, and its overlay costs nothing
  while no message is showing
- If ZeroEngine is closed in a game, DND, brightness and the touch mode are put back
- The frame rate target, 1% lows and throttle count are now right for each game. Sessions are
  recorded with the overlay off too
- New switches on the Panel tab: Boost, battery hold in games, the connection notice (which also
  stops its ping) and session history
- A new CPU or GPU limit in Expert mode undoes itself unless you keep it
- The Game panel tile closes the shade first and says when no game is open

### Bypass Charging
- New battery hold for games: ZeroEngine holds the battery at its level while you play, without
  changing your Smart or Bypass setting
- The battery always charges below 15%, and a hold never goes under 20%
- Smart mode stays on after a reboot
- The Smart limit can be set from 60% to 95%
- New optional heat pause: charging stops at 43 °C and resumes below 40 °C
- The screen shows what the kernel actually does, and warns when something else stops charging
- The mode chip and the battery current sign are shown correctly

### Dolby Atmos
- Dolby keeps one audio effect for the whole app and applies its settings once per playback
  start, instead of on every notification sound or pause
- Dolby no longer asks for notification access; it never needed it
- App profiles catch every app switch and go back to the profile you picked, also after a reboot

### Zero Launcher
- Restoring a backup no longer crashes the home screen. A backup is now fully checked before
  anything is replaced
- Hidden apps stay hidden in search. Work profile apps can be hidden and unhidden, and the Hidden
  apps screen loads faster
- Drawer search waits for you to stop typing before it searches
- A straight up swipe in a corner goes home unless it starts at the very edge. The corner swipe
  always opens the assistant you picked
- With the iOS drawer style, the search bar and the gestures no longer try to open a drawer that
  isn't there
- A pinch on the home screen no longer pulls down the notifications
- New switch for the vibration when the app drawer opens
- The recents memory info shows the ZRAM actually in use
- ZeroLauncher settings are translated, with full Indonesian

## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
