# Changelog

Installer history for https://github.com/Arcus-org/arcus-releases. Source lives in https://github.com/Arcus-org/arcus-core.

## Unreleased (site updated, no new installer)

2026-10-13. The public site https://arcusai.netlify.app shows the investigation desk and the Spinnaker Deploy Manifest example. No new desktop binary was published.

- Homepage: “Arcus is the desktop investigation desk for support and solutions engineers.” Example: “A Spinnaker pipeline failure, investigated in Arcus” (`WaitForManifestStableTask`).
- Netlify production deploy `6aceb15d1c3f878fdb88ae7e` on site `arcusai` (`1d53db9b-1ce2-475f-a0c2-8846ad918168`). That site is not built from Git.
- Site source is `arcus-core` branch `site/investigation-desk-intro` at `945c25c`. `arcus-core` `main` is still `e79c2f4` (2026-10-08).
- Downloadable assets are still v1.4.1 from 2026-07-09. `desktop/package.json` is still `1.4.1`.
- Those July binaries do not include later desktop fixes: transcript client, connectors, model list, Teams panel, Ask Arcus, local repo.
- No Windows, Mac, or Linux installer was built for this update. A Mac `.dmg` was not attempted; this was done on Windows, which cannot produce one.

## 1.4.1 — 2026-07-09

Published assets. These are still the latest files a downloader can get. They are not the current product described on the site.

- `Arcus-Setup-1.4.1.exe`
- `Arcus-1.4.1-arm64.dmg`
- `Arcus-1.4.1.dmg`
- `Arcus-1.4.1.AppImage`
- `arcus-desktop_1.4.1_amd64.deb`
- `latest.yml`, `latest-mac.yml`, `latest-linux.yml`

The GitHub Release body was empty when this tag was published.

## 1.4.0 — 2026-07-09

Previous installer set, same asset names with `1.4.0`. Superseded by 1.4.1.
