# Arcus releases

Desktop installers for [Arcus](https://arcusai.netlify.app).

The public site is https://arcusai.netlify.app.

The current desktop download is the unsigned Windows installer on **[1.4.2](https://github.com/Arcus-org/arcus-releases/releases/tag/v1.4.2)**. Mac was not built. The July 9, 2026 files on **[v1.4.1](https://github.com/Arcus-org/arcus-releases/releases/tag/v1.4.1)** are not the current app.

## Public site

https://arcusai.netlify.app

Checked 2026-10-13 after the production deploy. The homepage is the investigation desk. The hero sentence is:

> Arcus is the desktop investigation desk for support and solutions engineers.

The example on that page is a Spinnaker pipeline failure: “A Spinnaker pipeline failure, investigated in Arcus.” The finding names `WaitForManifestStableTask` on Deploy Manifest.

That deploy is Netlify deploy `6aceb15d1c3f878fdb88ae7e` on the existing site `arcusai` (`1d53db9b-1ce2-475f-a0c2-8846ad918168`). The site is not connected to a Git repo, so production came from the Netlify CLI, not from a push to `main`.

Site source: `arcus-core` branch `site/investigation-desk-intro` at `945c25c`. `arcus-core` `main` is still `e79c2f4` (2026-10-08).

## Downloadable installers

Current desktop: **[1.4.2](https://github.com/Arcus-org/arcus-releases/releases/tag/v1.4.2)**, published 2026-10-13.

| Platform | File | Published |
| --- | --- | --- |
| Windows x64 | `Arcus Setup 1.4.2.exe` | 2026-10-13 |

`Arcus Setup 1.4.2.exe` is an NSIS setup installer (160,822,834 bytes). It is unsigned. There is no signing certificate. Windows SmartScreen will warn: choose **More info**, then **Run anyway**.

Mac was not built. No `.dmg` is on 1.4.2. A Mac installer has to be built on a Mac.

Linux was not built.

This release does not include `latest.yml`, `latest-mac.yml`, `latest-linux.yml`, or a blockmap. GitHub `releases/latest` is this Windows installer only.

The July 9, 2026 files are not the current app. They stay on **[v1.4.1](https://github.com/Arcus-org/arcus-releases/releases/tag/v1.4.1)**:

| Platform | File | Published |
| --- | --- | --- |
| Windows x64 | `Arcus-Setup-1.4.1.exe` | 2026-07-09 |
| macOS Apple silicon | `Arcus-1.4.1-arm64.dmg` | 2026-07-09 |
| macOS | `Arcus-1.4.1.dmg` | 2026-07-09 |
| Linux AppImage | `Arcus-1.4.1.AppImage` | 2026-07-09 |
| Linux deb | `arcus-desktop_1.4.1_amd64.deb` | 2026-07-09 |

The July auto-update manifests (`latest.yml`, `latest-mac.yml`, `latest-linux.yml`) stay on that v1.4.1 release. They still describe the July apps.

`arcus-core` `main` is still `e79c2f4` (2026-10-08). Desktop version `1.4.2` is commit `70913d2` on `site/investigation-desk-intro`. This installer was built on Windows from that local desktop checkout, including later uncommitted desktop work. It is not an `arcus-core` `main` build.

## When a new installer is actually built

Source repo: https://github.com/Arcus-org/arcus-core

`desktop/package.json` publish block:

- provider: `github`
- owner: `Arcus-org`
- repo: `arcus-releases`
- releaseType: `release`

Commands, from `desktop/` on a clean commit, after the version is bumped:

- Windows: `npm run dist:win` with `CSC_IDENTITY_AUTO_DISCOVERY=false` and `win.signAndEditExecutable` set to `false`. This Windows account cannot create the winCodeSign symlinks, and there is no signing certificate.
- macOS unsigned: `npm run dist:mac` (`CSC_IDENTITY_AUTO_DISCOVERY=false`, notarize skipped). This has to run on a Mac.
- Linux: `npm run dist:linux`

electron-builder uploads to this repo. Do not force-push `main`. Do not commit API keys or customer tokens.

Production API the desk calls: `https://arcus-api-production-a4fc.up.railway.app` (`GET /health` returns `service: arcus`).

The next installer should match the investigation desk on the site: Home, Investigate, History, Tickets; live transcript; local repo search; notes; Slack; Jira, Zendesk, ServiceNow, and Teams when that customer's app or token is saved; MCP in Settings; ticket updates only when a tracker is connected.
