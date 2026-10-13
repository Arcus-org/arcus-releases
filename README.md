# Arcus releases

Desktop installers for [Arcus](https://arcusai.netlify.app): the investigation desk for support and solutions engineers.

Live transcript, local repo search, investigation notes, Slack, and ticket updates. Jira, Zendesk, ServiceNow, and Teams connect after your org's app or token is saved. MCP logs are Settings, Tools and MCP, in the app.

## Current download

Published release: **[v1.4.1](https://github.com/Arcus-org/arcus-releases/releases/tag/v1.4.1)** (2026-07-09).

Latest feed: https://github.com/Arcus-org/arcus-releases/releases/latest

| Platform | File |
| --- | --- |
| Windows x64 | `Arcus-Setup-1.4.1.exe` |
| macOS Apple silicon | `Arcus-1.4.1-arm64.dmg` |
| macOS | `Arcus-1.4.1.dmg` |
| Linux AppImage | `Arcus-1.4.1.AppImage` |
| Linux deb | `arcus-desktop_1.4.1_amd64.deb` |

Auto-update manifests on that release: `latest.yml` (Windows), `latest-mac.yml`, `latest-linux.yml`.

The public download page reads `https://api.github.com/repos/Arcus-org/arcus-releases/releases/latest`.

## Build pointers

Source repo: https://github.com/Arcus-org/arcus-core

`desktop/package.json` publish block:

- provider: `github`
- owner: `Arcus-org`
- repo: `arcus-releases`
- releaseType: `release`

`desktop/package.json` version today: **1.4.1** (same string as the July installer).

Commands, from `desktop/` on a clean commit:

- Windows: `npm run dist:win`
- macOS unsigned: `npm run dist:mac` (`CSC_IDENTITY_AUTO_DISCOVERY=false`, notarize skipped)
- Linux: `npm run dist:linux`

electron-builder uploads to this repo. Do not force-push `main`. Do not commit API keys or customer tokens.

Production API the desk calls: `https://arcus-api-production-a4fc.up.railway.app` (`GET /health` returns `service: arcus`).

## What v1.4.1 is, and is not

The GitHub Release assets are the July 9, 2026 installers. `arcus-core` `main` has moved since then.

| | |
| --- | --- |
| Published installer | v1.4.1, 2026-07-09. Release body was empty. |
| `arcus-core` `main` | `e79c2f4` (2026-10-08), merge of PR #59 (org notifications and SLA metrics) |
| Working tree | Dirty local changes on top of that commit. Not packaged. |

Do not treat the downloadable 1.4.1 binary as the October source tree. This repo update does not publish a new installer.

## Product the next installer should match

- Investigation desk: Home, Investigate, History, Tickets
- Live transcript while the engineer stays in their own meeting
- Local repo index; snippets leave the machine only when you ask
- Investigation notes and History (Leave keeps a draft, Finish and save closes the case)
- Slack in Settings
- Jira as org bring-your-own OAuth, or an API token
- Zendesk and ServiceNow when that customer's credentials are saved
- Teams when the Microsoft app is configured; chat search is not Slack search
- MCP in Settings, Tools and MCP
- Ticket updates only when posts are on and a tracker is actually connected

## Still open before calling an install current

- No spoken live call has been re-checked on the desktop against production since the Deepgram deploy that stopped sending `diarize=true` next to `diarize_model=v1`.
- OPENAI_API_KEY is unset on the API, so GPT-6 Luna is hidden from the model list.
- Teams client env, Zendesk subdomain, and ServiceNow are unset on the API. They are not zero-setup.
- Mac builds are unsigned. Right-click, Open. Windows SmartScreen needs More info, Run anyway until the installer is signed.
- A new installer from current `main` has not been built.
