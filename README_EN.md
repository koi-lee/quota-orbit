# Quota Orbit

See how much Codex quota remains, when it recovers, and what public reset announcements say—all from your Mac, so you can plan your work.

Quota Orbit puts this information within reach through a desktop companion and menu bar:

- **Before starting a task**, check remaining quota and recovery time to decide whether to continue now or return later.
- **While working**, review quota changes recorded during the current session.
- **When following resets**, read public announcements and their progress without repeatedly opening news pages.

Click the companion to expand the orbit, or check the menu bar. Personal quota requires Codex CLI installed and signed in locally. A public announcement does not mean your personal quota has recovered.

[Download the Mac public trial](https://github.com/koi-lee/quota-orbit/releases/latest) · [Installation and first use](docs/INSTALL_EN.md) · [Website](https://www.starshoreai.com/quota-orbit/) · [简体中文](README.md)

## Quota and messages on your desktop

### Remaining quota and recovery time

![Desktop companion with remaining quota and recovery time, using sample data](docs/images/desktop-quota.jpg)

Click the companion to switch between quota, messages and changes. You can also view quota in the menu bar.

### Public reset announcements

![Reset messages and message details in demo mode](docs/images/desktop-messages.jpg)

Open message details to follow public reset progress. Public announcements and personal quota are shown separately; an announcement does not guarantee a reset for your account.

### Quota changes on this Mac

![Two quota-change records with sample data](docs/images/desktop-changes.jpg)

Review changes during the current session. Recording starts again when the recovery cycle changes.

> These are actual app screens in demo mode. Quota, messages and times are sample values; demo alerts do not send system notifications.

## Mac public trial · 1.3.6 (72)

[Download 1.3.6 for Apple silicon](https://github.com/koi-lee/quota-orbit/releases/download/v1.3.6/Quota-Orbit-1.3.6-arm64.dmg)

Apple silicon · macOS 13 or later. This Developer ID signed and Apple-notarized public trial is distributed outside the Mac App Store; the App Store edition is not available yet. Trial software may contain issues.

1. Install Codex CLI and sign in with a ChatGPT account to view personal quota. This package does not bundle the CLI helper.
2. Open the DMG, drag Quota Orbit into Applications, then launch it there.
3. Click the companion to view quota and public messages. Enable notifications in the app if desired.

See [Installation and first use](docs/INSTALL_EN.md) for CLI setup, sign-in and connection checks. Quit an existing copy before replacing it and keep the previous installer for rollback. Report issues with your OS version and a screenshot, never credentials. The corresponding source is tagged `v1.3.6`; installer checksums are in the Release SHA256SUMS.txt.

## Optional: take Quota Orbit to AI Passport

If you own AI Passport hardware, its small screen can show public reset announcements. Add the separate Passport Mac Sync Assistant to display personal quota. Personal sync requires an awake Mac signed in to Codex on the same Wi-Fi as the device. None of these companion components are required to use Quota Orbit on your Mac.

| Goal | Product | Download |
|---|---|---|
| View Codex quota with a Mac desktop pet/menu bar | **Main Quota Orbit Mac client**, no Passport required | [Mac public trial](https://github.com/koi-lee/quota-orbit/releases/latest) |
| Sync Codex personal quota from Mac to AI Passport | **Passport Mac Sync Assistant**, separate from the Quota Orbit desktop app | [0.3.0 pre-release (Apple silicon)](https://github.com/koi-lee/quota-orbit-aipassport/releases/tag/passport-helper-v0.3.0) · [简体中文](https://github.com/koi-lee/quota-orbit-aipassport/releases/download/passport-helper-v0.3.0/README.zh_CN.md) · [繁體中文](https://github.com/koi-lee/quota-orbit-aipassport/releases/download/passport-helper-v0.3.0/README.zh_TW.md) · [English](https://github.com/koi-lee/quota-orbit-aipassport/releases/download/passport-helper-v0.3.0/README.en.md) |
| Install a play on AI Passport hardware | **Device firmware**, not a Mac installer | [Community installation](https://ai-passport.folotoy.cn/plays/1250/) |

[AI Passport firmware, device guides and sync assistant](https://github.com/koi-lee/quota-orbit-aipassport)

## Data and message sources

The app checks public messages while running and connected. Messages come from public sources or third-party transcriptions; check the original post. Credentials and usage data remain on your Mac and are not uploaded to this repository. Quota availability depends on what Codex returns. Missing, failed or stale data does not mean a reset has completed.

## Repository scope

This repository contains the Mac client's AGPL-3.0 source, tests and local companion assets. Server, website, browser extension and developer credentials are not included. Legacy v1.1.3 and earlier tags retain their MIT license and are discontinued.

Automatic GitHub Source code archives contain this Mac desktop client. AI Passport firmware and its sync assistant are maintained and distributed in their dedicated repository.

## Local build

With Xcode Command Line Tools and Swift 5.9+, run `swift test --disable-sandbox` then `./build-local.sh`. This produces an ad-hoc signed local app using a separate bundle ID. Set CODEX_BUILD_DIR to a fresh output path for another build.

`build-release.sh` builds the arm64 distribution app; release signing requires the developer's authorized Developer ID. Signing alone is not notarization. The release process notarizes and staples the app and DMG separately before upload.

See [LICENSE](LICENSE) and [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

## Verification limits

Source tests and local builds have been verified. Real notification banners, other hardware and systems, and first-time account connections depend on the user's environment. Source publication does not replace signing, notarization or store review. Quota Orbit is independent and is not an official OpenAI product or endorsement.
