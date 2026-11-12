# Evolution X 12.4 for POCO F7 (onyx): build 20261112

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/EvolutionX/17/20261112/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

### Zero Launcher
- New: the app drawer search also finds Settings pages, app shortcuts and contacts, not only apps.
  A Settings result opens that exact page, and Enter on the keyboard opens the top result
- New: the search bar in the dock opens this drawer search. A switch in ZeroLauncher settings
  (Home screen) brings back the Google app instead
- New: At a Glance from Google in Quickspace, the same weather and event cards Pixel shows
  (can be turned off)
- New: tabs in the app drawer (your own tabs plus app categories), switch them with a sideways
  swipe. Off by default, turn it on in ZeroLauncher settings > App drawer
- New: hide apps from the app drawer and its search (long press an app > Hide app). Home screen
  icons stay where they are
- New: pick the icon shape, 23 shapes with a live preview
- New: choose what a double tap or a pinch on an empty part of the home screen does: lock the
  screen, notifications, quick settings, app drawer or recents
- New: landscape mode switch for the home screen
- New: back up and restore your home screen layout and launcher settings to a file
- New: search inside ZeroLauncher settings
- New: Select chip in Recents, to pick text from the app on screen and copy, share or search it.
  Everything stays on the phone, and password fields are skipped
- The corner swipe now shows the assistant over the app you are using ("Ask Gemini"), like on
  Pixel, instead of opening the Google app

### Camera
- 4K 60 fps video now records at 100 Mbps instead of 50 Mbps, for both H.264 and HEVC
- Other video modes that were held at 50 Mbps now get their full rate: 4K DCI 57.5 Mbps, 8K
  74 Mbps, 720p slow motion 55 Mbps
- RAW and Ultra RAW are back in Pro mode, now saving the real RAW photo instead of only the
  preview frame

### Bluetooth audio
- aptX Adaptive at 44.1 kHz now plays without resampling: Bluetooth music is mixed at the rate
  your headphones use (44.1 or 48 kHz) instead of always 48 kHz
- Fixed aptX Adaptive staying resampled after changing the codec during playback or turning
  Bluetooth back on, until the next reconnect

### Haptics
- Taps feel fuller and stronger, like HyperOS: an ordinary tap now uses the vibration closest to
  the motor's natural frequency, and taps in apps and the system UI play at full strength.
  The low touch vibration setting still softens them, and slider and scrolling ticks are unchanged


## Known issues

- **Wi-Fi in the Setup Wizard:** use WPA3 or WPA2/WPA3 mixed mode. An upstream Evolution X bug makes the
  Setup Wizard treat WPA2-only networks as WPA3, so they fail to connect. On a WPA2-only network, skip Wi-Fi
  during setup and connect from Settings afterwards, which works normally.
