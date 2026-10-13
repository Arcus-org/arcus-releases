# Arcus releases

Desktop installers for [Arcus](https://arcusai.netlify.app).

The website is the current public description of the product. The files in GitHub Releases are not.

## Public site

https://arcusai.netlify.app

Checked 2026-10-13 after the production deploy. The homepage is the investigation desk. The hero sentence is:

> Arcus is the desktop investigation desk for support and solutions engineers.

The example on that page is a Spinnaker pipeline failure: “A Spinnaker pipeline failure, investigated in Arcus.” The finding names `WaitForManifestStableTask` on Deploy Manifest.

That deploy is Netlify deploy `6aceb15d1c3f878fdb88ae7e` on the existing site `arcusai` (`1d53db9b-1ce2-475f-a0c2-8846ad918168`). The site is not connected to a Git repo, so production came from the Netlify CLI, not from a push to `main`.

Site source: `arcus-core` branch `site/investigation-desk-intro` at `945c25c`. `arcus-core` `main` is still `e79c2f4` (2026-10-08).

## Downloadable installers

Latest GitHub Release: **[v1.4.1](https://github.com/Arcus-org/arcus-releases/releases/tag/v1.4.1)**, published 2026-07-09.

These July 9, 2026 binaries are still the only installers. They are not the current product. They do not include later desktop work:

- transcript client
- connectors
- model list
- Teams panel
- Ask Arcus
- local repo

`desktop/package.json` in `arcus-core` is still `1.4.1`. No newer Windows, Mac, or Linux installer was built or uploaded. No version bump. No new GitHub Release.

A macOS `.dmg` cannot be built on Windows. This update did not produce one, and it did not replace the July Mac files.

| Platform | File | Published |
| --- | --- | --- |
| Windows x64 | `Arcus-Setup-1.4.1.exe` | 2026-07-09 |
| macOS Apple silicon | `Arcus-1.4.1-arm64.dmg` | 2026-07-09 |
| macOS | `Arcus-1.4.1.dmg` | 2026-07-09 |
| Linux AppImage | `Arcus-1.4.1.AppImage` | 2026-07-09 |
| Linux deb | `arcus-desktop_1.4.1_amd64.deb` | 2026-07-09 |

Auto-update manifests on that same release: `latest.yml`, `latest-mac.yml`, `latest-linux.yml`.

The public download page reads https://github.com/Arcus-org/arcus-releases/releases/latest, so it still offers these July apps.

## When a new installer is actually built

Source repo: https://github.com/Arcus-org/arcus-core

`desktop/package.json` publish block:

- provider: `github`
- owner: `Arcus-org`
- repo: `arcus-releases`
- releaseType: `release`

Commands, from `desktop/` on a clean commit, after the version is bumped:

- Windows: `npm run dist:win`
- macOS unsigned: `npm run dist:mac` (`CSC_IDENTITY_AUTO_DISCOVERY=false`, notarize skipped). This has to run on a Mac.
- Linux: `npm run dist:linux`

electron-builder uploads to this repo. Do not force-push `main`. Do not commit API keys or customer tokens.

Production API the desk calls: `https://arcus-api-production-a4fc.up.railway.app` (`GET /health` returns `service: arcus`).

The next installer should match the investigation desk on the site: Home, Investigate, History, Tickets; live transcript; local repo search; notes; Slack; Jira, Zendesk, ServiceNow, and Teams when that customer's app or token is saved; MCP in Settings; ticket updates only when a tracker is connected.
