# Quota Orbit · 额度星盘: installation and first use

For public trial **1.3.6 (72)** on Apple silicon Macs running macOS 13 or later. [中文](INSTALL.md) · [README](../README_EN.md)

Use the desktop companion to view personal Codex quota, recovery times and public reset announcements. If you only need public announcements, use the [website](https://www.starshoreai.com/quota-orbit/) without installing or signing into Codex.

## 1. Set up Codex CLI and sign in

The public trial does not bundle Codex CLI. Personal quota requires a local CLI signed in with a **ChatGPT account**. Signing into the Codex desktop app alone does not establish this prerequisite; API-key usage is separate from ChatGPT subscription quota.

Open Terminal and run:

```sh
codex --version
```

If a version appears, the CLI is available in your terminal. Otherwise follow the [official OpenAI CLI guide](https://learn.chatgpt.com/docs/codex/cli). Its standalone macOS installation command is:

```sh
curl -fsSL https://chatgpt.com/codex/install.sh | sh
```

This downloads and runs OpenAI's installation script. Reopen Terminal, then check `codex --version` again. If the command is still missing, follow the installer's path instructions rather than repeatedly reinstalling.

Run `codex`, choose **Sign in with ChatGPT** when prompted, and finish sign-in in the official browser page. If already signed in with ChatGPT, keep that session. Consult the [official authentication guide](https://developers.openai.com/codex/auth) for sign-in problems. You do not need to submit a coding task to connect Quota Orbit.

## 2. Download and install Quota Orbit

1. [Download Quota Orbit 1.3.6 for Apple silicon](https://github.com/koi-lee/quota-orbit/releases/download/v1.3.6/Quota-Orbit-1.3.6-arm64.dmg). See the [same Release](https://github.com/koi-lee/quota-orbit/releases/tag/v1.3.6) for notes, source and checksums.
2. Quit any existing copy and keep the previous installer. Do not overwrite a newer local version with 1.3.6.
3. Open the DMG, drag Quota Orbit into Applications, eject the installation disk and launch from Applications.

The public package is Developer ID signed and Apple-notarized. It is distributed separately from the App Store edition; a public trial does not mean an App Store release. If macOS reports damage or cannot verify the app, download again from the Release and check the version and checksum; do not disable system protections.

Optional checksum: download `SHA256SUMS.txt` from the Release. Type `shasum -a 256 ` in Terminal, keeping the trailing space, drag the DMG into Terminal, and press Return. Compare the digest with the matching DMG entry. Do not run a mismatched package.

## 3. Read your quota

Click the companion to open its orbit panel, then choose quota. Expect the available quota windows, remaining percentages and recovery times returned for your account. Exit demo mode if enabled: example values are not personal data.

Open **Getting Started…** from the menu bar for help. Finish CLI sign-in under the same macOS user, then use the guide's connection check if prompted. Receiving public announcements does not prove that personal quota is connected.

## 4. Enable reminders if desired

Enable the desired announcement reminders in the app and allow system notifications if you want them. If no banner appears, check System Settings → Notifications → Quota Orbit and Focus settings.

This guide describes public version 1.3.6, not low-quota features in later local development builds. A public reset announcement does not prove that your own quota has recovered.

## Troubleshooting

| Symptom | Check | Expected result |
| --- | --- | --- |
| `codex: command not found` | Reopen Terminal and follow the official installer's path instructions | `codex --version` prints a version |
| CLI works but the app is disconnected | Complete ChatGPT sign-in as the same macOS user and retry the guide's connection check; relaunch the app if needed | Real quota or an actionable connection error |
| Failed, stale or missing quota | Check the network and CLI sign-in, then retry | Judge quota only after fresh data returns |
| Announcements without personal quota | Check CLI setup and demo mode | Keep public and personal data separate |
| Companion is missing | Use the menu bar's Show Companion entry | Companion is visible |
| No notification | Check app settings, system notifications and Focus | Clear permission state; enabled settings alone do not prove delivery |

Report unresolved issues in [GitHub Issues](https://github.com/koi-lee/quota-orbit/issues), with app/macOS versions, chip type, reproduction steps and redacted screenshots. Do not upload credentials, `auth.json` or full session logs.

CLI instructions were checked against official documentation on 2026-10-14. This documentation change was not a fresh installation/login test on a clean Mac. See the Release for historical verification and compatibility limits.
