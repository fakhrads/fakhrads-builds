# DerpFest 17 for POCO F7 (onyx): flashing guide

In the commands below, `<date>` is the build date (for example `20261117`) and `<hash>` is the code at the
end of the zip name. Use the exact file names from the build's download folder.

## Pre-installation

- Unlocked bootloader
- HyperOS latest stable Global firmware is required. As of now: Global OS3.0.x
- Google apps are already included in the ROM, no separate GApps package is needed
- A PC with the latest platform-tools (`adb` and `fastboot`)

## First time installation (clean flash)

Coming from another ROM (Evolution X included) or from another builder's DerpFest? Do this clean flash.

1. Download all required files from the build's download folder:
   - `DerpFest-v17-<date>-onyx-Community-Stable-<hash>.zip`
   - `boot-<date>.img`, `dtbo-<date>.img`, `init_boot-<date>.img`, `vendor_boot-<date>.img`,
     `recovery-<date>.img`
2. Power off the device and boot into Fastboot mode: hold **Volume Down + Power** until FASTBOOT appears on the
   screen.
3. Flash the required images:
   ```
   fastboot flash boot boot-<date>.img
   fastboot flash dtbo dtbo-<date>.img
   fastboot flash init_boot init_boot-<date>.img
   fastboot flash vendor_boot vendor_boot-<date>.img
   fastboot flash recovery recovery-<date>.img
   ```
4. Reboot into recovery:
   ```
   fastboot reboot recovery
   ```
   If the device does not boot into recovery automatically: power off the device, then hold
   **Volume Up + Power** until the MI logo appears, and release.

   > Touch input works in recovery on most devices. If touch does not work, use the Volume keys to navigate and
   > the Power button to select options.
5. In recovery, select **Factory Reset** → **Format data / factory reset**, and confirm the formatting process.
   This removes encryption, wipes internal storage, and formats the cache partition (if present).
6. Return to the main menu and select **Apply Update** → **Apply from ADB**, then sideload the ROM:
   ```
   adb sideload DerpFest-v17-<date>-onyx-Community-Stable-<hash>.zip
   ```
   > The sideload process may stop at around 47% on the host computer. This is expected behavior and not a
   > failure.
7. Reboot to system.

## Updating from my previous DerpFest build

1. Open **Settings → System → Updater**. It reads the list of my builds; when a newer build is there, tap
   **Download**, then **Install** and **Reboot** when it is done (recommended).
2. Or download the zip yourself and pick it with the Updater's local update.

The update is installed in the other slot while you keep using the phone. If the new build does not boot,
the phone goes back to the old one by itself.

## Verify your download (optional)

Check the files against `SHA256SUMS` in the same download folder:

```
sha256sum -c SHA256SUMS
```
