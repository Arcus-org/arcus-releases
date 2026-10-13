# Changelog

Installer history for https://github.com/Arcus-org/arcus-releases. Source lives in https://github.com/Arcus-org/arcus-core.

## Unreleased (source only, no installer)

`arcus-core` `main` at `e79c2f4` (2026-10-08) plus local uncommitted work. Not what the download page serves.

- Org notifications and SLA metrics (PR #59).
- Live transcript query uses Deepgram `diarize_model=v1` and does not also send `diarize=true` (that pair returned HTTP 400).
- Desktop still reports version `1.4.1` in `package.json`. Bump that before the next electron-builder publish.

Not verified: a spoken live call on the desktop against production after that Deepgram change.

## 1.4.1 — 2026-07-09

Published assets:

- `Arcus-Setup-1.4.1.exe`
- `Arcus-1.4.1-arm64.dmg`
- `Arcus-1.4.1.dmg`
- `Arcus-1.4.1.AppImage`
- `arcus-desktop_1.4.1_amd64.deb`
- `latest.yml`, `latest-mac.yml`, `latest-linux.yml`

The GitHub Release body was empty when this tag was published. These files are still the latest download.

## 1.4.0 — 2026-07-09

Previous installer set, same asset names with `1.4.0`. Superseded by 1.4.1.
