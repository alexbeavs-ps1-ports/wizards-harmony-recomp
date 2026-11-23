<p align="center"><a href="https://alexbeavs-ps1-ports.github.io/psxrecomp-ports/"><img src="https://raw.githubusercontent.com/alexbeavs-ps1-ports/psxrecomp-ports/main/docs/assets/alexbeav-ps1-recomps-banner.png" alt="Alexbeav's PS1 Recomps" width="100%"></a></p>

# Wizard's Harmony

<!-- retcomm-readme-metrics -->
[![GitHub downloads (all assets, all releases)](https://img.shields.io/github/downloads/alexbeavs-ps1-ports/wizards-harmony-recomp/total)](https://github.com/alexbeavs-ps1-ports/wizards-harmony-recomp/releases)
[![GitHub downloads (latest release)](https://img.shields.io/github/downloads/alexbeavs-ps1-ports/wizards-harmony-recomp/latest/total)](https://github.com/alexbeavs-ps1-ports/wizards-harmony-recomp/releases/latest)
[![GitHub release](https://img.shields.io/github/v/release/alexbeavs-ps1-ports/wizards-harmony-recomp)](https://github.com/alexbeavs-ps1-ports/wizards-harmony-recomp/releases/latest)
<!-- /retcomm-readme-metrics -->

Static recompilation of **Wizard's Harmony** built on
[psxrecomp](https://github.com/mstan/psxrecomp) and
[recomp-ui](https://github.com/RetroPortingToolKit/recomp-ui).

This is an owned-input setup kit. You supply your own SLPS-00194 disc image
and your own SCPH-5500 (Japan) BIOS dump; first-run setup generates and compiles the game on
your machine. The kit and its release archives contain no game disc, retail BIOS,
generated game code, or saved game.

| | |
|---|---|
| Region | Japan |
| Disc serial | SLPS-00194 |
| Discs | 1 |
| Supported dump | Redump `Wizard's Harmony (Japan).cue` as CUE/BIN or CHD |
| BIOS | SCPH-5500 (Japan), 524288 bytes, SHA-256 `9c0421858e217805f4abe18698afea8d5aa36ff0727eb8484944e00eb5e7eadb` |

<!-- release-standard:bios -->
**BIOS:** SCPH-5500 (Japan) retail BIOS, 524288 bytes, SHA-256 `9c0421858e217805f4abe18698afea8d5aa36ff0727eb8484944e00eb5e7eadb`. Supply your own dump; releases do not use OpenBIOS.
<!-- /release-standard:bios -->

## Setup

1. Download the setup ZIP for your platform from [Releases](https://github.com/alexbeavs-ps1-ports/wizards-harmony-recomp/releases)
   and extract it into a writable folder.
2. Start `wizards_harmony` (`.exe` on Windows).
3. In the setup wizard select your disc image (the Redump CUE, or a CHD of the
   same dump) and your BIOS file.
4. Run Generate & rebuild and wait for the game to start. The first run compiles
   the game and takes several minutes.

On Windows the wizard downloads the portable build tools (cmake-clang-v1) or uses
cmake/ninja already on PATH. On Linux and macOS install CMake, Ninja, Python 3,
and a C/C++ compiler first. Keep a CUE and every file it references together.
Setup produces both a normal and a diagnostic build; see *Diagnostic mode* below.

<!-- retcomm-readme-launcher -->
## Retro Launcher

You can run this title **standalone** (release zip + the built-in recomp-ui
Generate & Build flow), or manage installs, updates, ROM/BIOS wiring, and queued
builds more intuitively with
**[Retro Launcher](https://github.com/RetroPortingToolKit/Retro-Launcher)** —
the Retro Compilation Manager hub for self-compiling recomps.

[Downloads](https://github.com/RetroPortingToolKit/Retro-Launcher/releases) ·
[Full README & features](https://github.com/RetroPortingToolKit/Retro-Launcher#readme)

<p align="center">
  <img src="https://raw.githubusercontent.com/RetroPortingToolKit/Retro-Launcher/main/docs/screenshots/hub-and-game-launcher.png" alt="Retro hub with a background build, next to a title’s recomp-ui launcher" width="720">
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/RetroPortingToolKit/Retro-Launcher/main/docs/screenshots/queue-and-background-build.png" alt="Background cmake build with titles queued" width="720">
</p>

Retro checks for updates, rebuilds with existing build data when possible,
shares the portable toolchain used by per-title launchers, and automates
BIOS/ROM/save plumbing so you are not stuck repeating each game’s wizard by hand.
<!-- /retcomm-readme-launcher -->

## Status

Version 0.1.0. This kit was imported from the wave 12 census scaffold, which built
on pin-j-v0.1.8 (psxrecomp `6e8cf2ac6`, recomp-ui `1f79bfe`).
No release package has been built from this kit yet, and no play testing is recorded.

## Diagnostic mode

If the game crashes, freezes, or misbehaves, switch to the diagnostic build
that first-run setup already produced (no recompiling): create an empty file
named `diagnostic-mode.txt` next to `wizards_harmony.exe` and start the game as
usual, or run `wizards_harmony.exe --diagnostic`. Reproduce the problem, quit, then
run `wizards_harmony.exe --collect-diagnostics`: it writes `diagnostics-<date>.zip`
next to the exe. Attach that zip to a GitHub issue on this repository with a
short description of what you did. The zip holds only the runtime's report
files, never saves, BIOS, or disc images. Delete `diagnostic-mode.txt` to go
back to normal mode. Details: `psxrecomp/docs/DIAGNOSTIC_MODE.md`.

## Legal

You must own the original game. Disc images under `disc/` are gitignored and
must never be committed. Retail BIOS dumps are not redistributed and OpenBIOS is
not shipped: this title is retail-BIOS-only, so first-run Generate needs your own
legally dumped SCPH-5500 image.

Default app icon: `assets/psxrecomp.ico` (and `.png` / `.svg`) — Retro-themed controller mark from `psxrecomp/assets/`. Windows builds embed it via `APP_ICON`.

Box art is not shipped in this kit or its repository. Redistribution permission for third-party cover images is unresolved, so the launcher runs without one.

## About this project

This project was developed with AI assistance. AI assists with code,
documentation, and investigation; Alex tests the game and makes release
decisions. Validation claims describe only the tests actually performed.

## Credits and licenses

Framework: [psxrecomp](https://github.com/mstan/psxrecomp), built from the
pinned fork commit named by the `psxrecomp` submodule. Launcher:
[recomp-ui](https://github.com/RetroPortingToolKit/recomp-ui), pinned by the
`recomp-ui` submodule. This kit's own files are under [LICENSE](LICENSE); third-party
notices are in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md), and the framework
and launcher licenses remain in their source directories. The original game and its
trademarks belong to their respective owners.

<!-- retcomm-readme-raid -->
---

<p align="center">
  <sub><b>R.A.I.D. — Retro AI Development</b> · a Discord for AI-assisted retro reverse-engineering, decomp &amp; recomp</sub>
</p>

<p align="center">
  <a href="https://discord.gg/Ad9BwSzctP"><img src=".github/raid-discord.png" alt="Join the Retro AI Development (R.A.I.D.) Discord" width="200"></a>
</p>
<!-- /retcomm-readme-raid -->
