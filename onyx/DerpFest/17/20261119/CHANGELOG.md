# DerpFest 17 for POCO F7 (onyx): build 20261119

Android 17 · Unofficial · by fakhrads

[Download](https://sourceforge.net/projects/fakhrads-builds/files/onyx/DerpFest/17/20261119/) ·
[Flashing guide](../FLASHING.md) · [Credits](../../CREDITS.md)

## Changelog

Casual Greeting
Conversation Log
lagi play nih

Kabar baik: Dolby Vision & HDR Boost di HP-mu sebenarnya sudah jalan 100% normal!

Ini bukti live-nya barusan pas mutar di Solid Explorer:

Decoder: c2.qti.dv.decoder (hardware Dolby Vision aktif)
Mode HBM: mMode=HBM_HDR, mBrightnessReason=automatic [ hdr ]
Panel HWC: Dynamice_range HDR, dataspace=BT2020_PQ
Brightness naik 8x: dari SDR 88.9 nits (0.072) → langsung naik ke 711.2 nits (mBrightnessState=0.592, hdrSdrRatio=8.0)!
Lalu kenapa videonya kelihatan lebih redup daripada UI?

Ada 2 alasan persis yang kelihatan di SurfaceFlinger barusan:

UI Solid Explorer Video Player-nya sendiri ikut minta HDR 5x (desiredHdrSdrRatio=5)

Layer UI sistem biasa (StatusBar, dll) sudah di-dim normal ke 88.9 nits (dimmingRatio = 0.125).
Tapi window UI Solid Explorer (VRI-pl.solidexplorer2) pakai DISPLAY_P3_EXTENDED dengan desiredHdrSdrRatio=5, sehingga tombol/teks UI player-nya digeber ke 444.5 nits!
Sementara di video Dolby Vision (BT2020_PQ), area normal/midtone sesuai standar PQ memang ada di kisaran 100–203 nits (hanya highlight seperti lampu/matahari yang tembus ke 711 nits).
Akibatnya: midtone video (~100–200 nits) kalah terang dibanding UI player-nya (444.5 nits), jadi di mata videonya terasa lebih redup.

Posisi brightness SDR awal masih rendah (88.9 nits)

Karena hdrRatio = 8.0 dikalikan dari brightness SDR saat itu (88.9 × 8 = 711 nits), peak videonya berhenti di 711 nits (padahal panel bisa sampai 3200 nits).
Kalau kamu naikkan slider brightness sedikit (misal ke 40–60%) saat nonton HDR/Dolby Vision — atau coba putar di player lain (misal MPV / Nova / VLC / YouTube HDR) yang UI-nya tetap SDR (dimmingRatio=0.125) — langsung kelihatan jauh lebih terang dan kontrasnya nendang!

Jadi di sisi ROM/kernel/HAL tidak ada yang rusak — jalur Dolby Vision (c2.qti.dv.decoder → dvs-aidl-service → BT2020_PQ → HBM_HDR 8x) semuanya sudah bekerja dengan benar.

jadi aman semua ?

Iya, aman semua!

Dolby Vision & HDR: Jalur hardware decoder (c2.qti.dv.decoder), dvs-aidl-service, SurfaceFlinger (BT2020_PQ), sampai HBM HDR boost 8x (HBM_HDR) semuanya sudah aktif dan jalan normal tanpa error/SELinux denial. Yang bikin terasa redup tadi cuma karena UI player Solid Explorer-nya sendiri ikut nge-boost 5x (444 nits) + brightness SDR awal lagi rendah (89 nits).
ZeroEngine: Error build sudah beres, polesan alert overheat dengan blur sudah masuk, sudah lulus kompilasi di builder, dan sudah di-commit + push ke origin/derp-17.

Kalau ada yang mau dicek atau dipoles lagi, tinggal bilang aja!

Sip, btw buat changelog first release apa aja yak? Buatin list nya dalam bentuk md

Ini draf Changelog First Release untuk DerpFest 17 (Android 17) — POCO F7 (onyx) dalam format Markdown, langsung siap copy-paste ke SourceForge / GitHub / CHANGELOG.md:

markdown
# DerpFest 17 for POCO F7 (onyx) — Initial Release
**Build Date:** 2026-11-19  
**Android Version:** 17 (DerpFest v17)  
**Build Type:** Community Stable (Signed, GMS included)  
**Firmware Required:** HyperOS Global OS3.0.x
---
## Highlights
- Initial bring-up of **DerpFest 17 (Android 17)** for POCO F7 (`onyx`)
- Built with **Pixel GMS** included out of the box and signed with private release keys
- **OTA Updater** configured out of the box (`Settings → System → Updater`)
## Device, Performance & Thermal
- **Qualcomm Power HAL (`perfd`) + BoostFramework** replacing `libperfmgr`, with QSPM HAL integration
- **Thermal & KProfiles** support with `thermalbreak` tuning and `sched_boost` perf lock integration
- **Dual-sensor Auto-Brightness** (front + rear ALS fusion) with HyperOS-style linear nits spline and darkening behavior
- **UDFPS** reliability improvements (auto-reopen display feature node and drop invalid short reads)
- **SELinux**: resolved denials across `parts_app`, `perfd`, `authsecret`, camera, GNSS, and QSPM HAL
- Reduced excessive per-frame camera and audio PAL log spam
## Display, Camera & Audio
- **Dolby Vision & HDR10 / HDR10+ / HLG** full pipeline (`c2.qti.dv.decoder`, `dvs-aidl-service`, fullscreen HBM HDR boost)
- **Leica Camera** integrated
- **LunarisDolby** audio enhancement integrated
- **Bypass Charging** & battery charging control support
## ZeroEngine (replaces GameSpace)
- **Redesigned In-Game Overlay**: customizable themes, shapes, live CPU/GPU load gauges, smooth tool scrolling, and tactile haptic feedback
- **AI Device Health Tab**: live telemetry diagnostics and recommendations, plus optional on-device **LiteRT-LM** AI summaries for gaming sessions and charging
- **HeatGuard (Overheat Protection)**: HyperOS-style skin temperature protection with frosted backdrop-blur alert and live cooling progress bar
- **Full Control Suite**: per-app thermal scenarios, KProfiles, touch tuning, bypass/cool charging, FPS monitor, and session reports
- Localized into **26 languages**
## ZeroLauncher (`Launcher3`)
- Ships **ZeroLauncher** as the default launcher (`com.android.launcher3`)
- DerpFest-native icon pack support
- **Recents Memory Info** showing ZRAM usage
- Configurable app drawer open haptics, double-tap actions, and full settings/drawer translations
- Smoother performance with off-main-thread At a Glance cards and corner-swipe assistant
## System & UI Defaults
- Starts with the **combined notification/QS shade** by default (separate shade remains selectable in Settings)
- **Assistant corner swipe** enabled by default
## Notes
- **Clean flash (format data)** is required when coming from HyperOS, Evolution X, or another builder's DerpFest build.
- Future updates from this build can be installed directly via **Settings → System → Updater**.

## Known issues

- None known
