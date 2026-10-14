# Changelog

Installer history for https://github.com/Arcus-org/arcus-releases. Source lives in https://github.com/Arcus-org/arcus-core.

## 1.4.2 — 2026-10-13

Windows installer only. The public site stays https://arcusai.netlify.app.

- `Arcus Setup 1.4.2.exe` (160,822,834 bytes), published as `Arcus.Setup.1.4.2.exe`. NSIS setup. Unsigned. No signing certificate. SmartScreen: More info → Run anyway.
- Mac was not built. No `.dmg` was uploaded.
- Linux was not built.
- The July 9, 2026 files are not this app. They remain on v1.4.1.
- This release does not include `latest.yml`, `latest-mac.yml`, `latest-linux.yml`, or a blockmap.
- Built on Windows from the local `site/investigation-desk-intro` desktop at version 1.4.2 (version bump `70913d2`), including later uncommitted desktop work. Not an `arcus-core` `main` build. `main` is still `e79c2f4` (2026-10-08).

Site, same day, unchanged by this installer publish:

- Homepage: “Arcus is the desktop investigation desk for support and solutions engineers.” Example: “A Spinnaker pipeline failure, investigated in Arcus” (`WaitForManifestStableTask`).
- Netlify production deploy `6aceb15d1c3f878fdb88ae7e` on site `arcusai` (`1d53db9b-1ce2-475f-a0c2-8846ad918168`). That site is not built from Git.
- Site source recorded for that deploy: `arcus-core` branch `site/investigation-desk-intro` at `945c25c`.

## 1.4.1 — 2026-07-09

July 9, 2026 files. They are not the current app. The current Windows installer is 1.4.2. Mac and Linux were not rebuilt.

- `Arcus-Setup-1.4.1.exe`
- `Arcus-1.4.1-arm64.dmg`
- `Arcus-1.4.1.dmg`
- `Arcus-1.4.1.AppImage`
- `arcus-desktop_1.4.1_amd64.deb`
- `latest.yml`, `latest-mac.yml`, `latest-linux.yml`

The GitHub Release body was empty when this tag was published.

## 1.4.0 — 2026-07-09

Previous installer set, same asset names with `1.4.0`. Superseded by 1.4.1.
