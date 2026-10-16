# Evolution X 17 for POCO F7 (onyx): flashing guide

In the commands below, `<date>` is the build date (for example `20261016`) and `<hash>` is the code at the
end of the zip name. Use the exact file names from the build's download folder.

## Pre-installation

- Unlocked bootloader
- HyperOS latest stable Global firmware is required. As of now: Global OS3.0.x
- Google apps are already included in the ROM, no separate GApps package is needed
- A PC with the latest platform-tools (`adb` and `fastboot`)

## First time installation (clean flash)

1. Download all required files from the build's download folder:
   - `EvolutionX-17.0-<date>-onyx-12.3-Unofficial-<hash>.zip`
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
   adb sideload EvolutionX-17.0-<date>-onyx-12.3-Unofficial-<hash>.zip
   ```
   > The sideload process may stop at around 47% on the host computer. This is expected behavior and not a
   > failure.
7. Reboot to system.

## Updating from my previous Evolution X build

1. Download the new ROM zip.
2. Open **Settings → System → Updater → local update** and pick the downloaded zip (recommended).
3. Reboot when the update is done.

Coming from another ROM, or from another builder's Evolution X? Do the clean flash above.

## Verify your download (optional)

Check the files against `SHA256SUMS` in the same download folder:

```
sha256sum -c SHA256SUMS
```
