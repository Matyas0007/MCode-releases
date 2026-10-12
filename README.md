# MCode

A minimalist, geeky app for your own Claude Code, for Windows and macOS.

MCode puts the `claude` you already use in a terminal into a calm, black, monospaced window with three panes:
your projects and sessions, the chat (or up to three side by side), and an inspector with every change as a diff.
Your usage limits are always in view, and model, effort, ultracode and permission mode are one key away. When
Claude asks you something, wants permission or has a plan, a banner slides up with the answers. MCode runs **your
own Claude Code**, logged in as you are; it never calls Anthropic's API itself.

**[Download the latest release](https://github.com/Matyas0007/MCode-releases/releases/latest)**

## Download

| File | System | What it is |
| --- | --- | --- |
| `MCode-Setup-X.Y.Z.exe` | Windows 10 or 11, 64-bit | The installer. **Download this on Windows.** |
| `MCode-X.Y.Z-universal.dmg` | macOS 13 or later, Apple silicon and Intel | The installer. **Download this on a Mac.** |
| `latest.yml`, `MCode-Setup-X.Y.Z.exe.blockmap` | Windows | Update files that installed copies read |
| `latest-mac.yml`, `MCode-X.Y.Z-universal.zip`, `.zip.blockmap` | macOS | Update files that installed copies read |

You never need to download the update files yourself.

## Requirements

- Windows 10 or 11 (64-bit), or macOS 13 (Ventura) or later on Apple silicon or Intel.
- Claude Code (Anthropic's `claude` command), installed and signed in: run `claude` once in a terminal and log in
  there. MCode never logs in for you. It finds `claude` in the usual places (such as `~/.local/bin/claude`, or on
  your `PATH`); if yours is elsewhere, point to it in Settings > Claude Code > Program.

## Install

**Windows.** Run `MCode-Setup-X.Y.Z.exe`. It installs for your user only, with no admin rights and no questions,
makes a Start-menu and a desktop shortcut, and starts MCode. The installer is not code-signed yet, so Windows
SmartScreen warns the first time: click "More info", then "Run anyway". Running a newer installer over an old one
updates it.

**macOS.** Open the `.dmg`, drag MCode to Applications, and start it from Applications. The app is signed with a
Developer ID and notarized by Apple, so it opens without a warning. Started from the `.dmg` or the Downloads folder
it can't update itself, and Settings > About says to move it to Applications.

## Updates

MCode updates itself from this page. Settings > About has "Check for updates" and "Check automatically" (on by
default): a few seconds after launch and then every 4 hours, MCode reads the update file of the newest release
(`latest.yml` on Windows, `latest-mac.yml` on the Mac). When there is a newer version, a pop-up offers Download;
nothing downloads by itself. Then "Restart to update" installs it.

- **Windows:** the download is checked against the SHA-512 in `latest.yml` before it is installed.
- **macOS:** the update is the `.zip`, and the system installs it only if it is signed by the same developer.

If the newest release has no files for your system yet, MCode simply says it is up to date. Updates replace only
the app: your settings, chats and Claude Code's data stay as they are.

## Uninstall

- **Windows:** uninstall MCode in Windows Settings > Apps. It removes the app only.
- **macOS:** drag MCode from Applications to the Trash.

What stays: MCode's own data (`%APPDATA%\MCode` on Windows, `~/Library/Application Support/MCode` on the Mac),
which you can delete yourself, and everything in `~/.claude`, which belongs to Claude Code (your sessions are there).

## Privacy

- No telemetry, no analytics, no crash reporter. Only Claude Code talks to Anthropic, as it does in a terminal.
- MCode itself contacts two places, only to look for updates: this repository's releases (for MCode) and npm's
  public registry (for the newest Claude Code version). The built-in browser loads the pages you or Claude open.
- MCode never reads Claude Code's credentials, never logs in for you, never handles a password, and never stores
  your account's e-mail.
- The one thing it holds is an Anthropic API key, if you paste one for an API-key account: stored only encrypted
  by your system (DPAPI on Windows, the Keychain on the Mac), never shown again, and given only to that account's
  `claude`, so only Claude Code sends it, only to Anthropic.
- The optional Discord status ("Playing MCode") goes only to the Discord app on the same computer, never over the
  network, and never names a chat, a message or a file. Settings > General > Discord turns it off.
- The error log stays on your computer, with personal details taken out.

## About this page

This repository holds only MCode's installers and update files. The source code is private.

1.0.35 is a fresh start for this page: earlier releases were removed.

## License

MCode is © 2026 Matyas Kucera. **All rights reserved.** It is not open source.

It bundles the Roboto Mono font, © 2015 The Roboto Mono Project Authors, under the SIL Open Font License 1.1 (the
full text ships in the app and is shown in Settings > About).

## Not affiliated with Anthropic

MCode is an independent app. It is not made by or affiliated with Anthropic. Claude and Claude Code are
Anthropic's names for their products. Claude Code is not part of MCode and is not shipped with it: you install it
yourself, under Anthropic's own terms.
