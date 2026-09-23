# Simagic Profile Manager (SPM)

**Public beta · Windows · SimHub**

Simagic Profile Manager is a community plugin for keeping SIMAGIC wheelbase setups in one place. It was created to make switching between cars and games quicker: import your SimPro 2 setups, organize and tune them in SimHub, then assign a setup to a car or class for automatic loading. Use the SimHub window, a touchscreen/DDU, phone, tablet or mapped steering-wheel buttons.

This is the **binary distribution and update repository**. Source code and the build system are kept separately in a private development repository.

## What it does

- Stores editable setups per game and imports exported SimPro 2 profiles as independent copies.
- Loads an assigned setup when SimHub identifies the game, car or class; also supports manual selection.
- Lets you tune supported wheelbase settings and navigate with touch or physical controls.
- Shows the Profile Manager on a SimHub display, monitor, phone or tablet.
- Offers a first-start guide, backups, diagnostic beta reports and SHA-256-verified beta updates.

Verified legacy wheelbases: **SIMAGIC Alpha Mini, Alpha and Alpha Ultimate**. **Alpha EVO Sport, EVO and EVO Pro support is experimental and disabled by default.** Game/car/class detection depends on the data provided by SimHub.

> [!WARNING]
> This is beta software that can change wheelbase settings. Check setup values before applying them and keep a backup of important profiles. **We recommend closing SimPro Manager 2 while using SPM to load or tune setups**, so the two applications do not try to control the wheelbase at the same time. SimPro 2 can still be used to export profiles for import into SPM.

## Download

Download the complete [SimagicProfileManager-Setup-0.1.0-beta.4.zip](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases/download/v0.1.0-beta.4/SimagicProfileManager-Setup-0.1.0-beta.4.zip). This one ZIP contains the plugin DLLs, dashboard and installer. For future versions, get the ZIP from the [latest beta release](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases).

## Install

1. Install and open SimHub at least once, then close it completely. Close SimPro Manager 2 as well.
2. Download the release ZIP and extract it to a normal folder. Do not run the installer from inside the ZIP.
3. Open PowerShell **as Administrator** in the extracted folder and run `./Install.ps1` (or `./Install.ps1 -SimHubPath 'D:\Your\SimHub'` for a non-default installation).
4. Start SimHub and open **Simagic Profile Manager**. Follow the **First Start Setup** guide.

The installer copies the three DLLs and installs the dashboard. It backs up any previous SPM DLLs/dashboard before replacing them. It does **not** erase your setups or assignments in `%LOCALAPPDATA%\SimagicProfileManager`.

## First Start Setup

The guide walks you through choosing touch, buttons or both; mapping controls (optional); choosing a screen/DDU or phone/tablet (optional); and importing SimPro 2 exports or starting with an empty library. SimPro 2 profiles must be **exported to files first** and then selected in the import step. Choose the destination game when importing.

After setup, use **Profiles** to create/import/edit setups and **Auto Switch** to assign them to a game-specific car or class. Use **Settings → Display** to choose a SimHub screen or get the phone/tablet address and QR code. Phone/tablet and the SimHub PC must be on the same local network; allow incoming SimHub connections through the firewall. You can revisit onboarding from **Settings → First Start Setup** without deleting existing profiles.

## Experimental Alpha EVO support

Version `0.1.0-beta.4` can detect Alpha EVO Sport (`3670:0500`), Alpha EVO (`3670:0501`) and Alpha EVO Pro (`3670:0502`). EVO reads and writes remain **off until you explicitly enable Settings → Beta → Enable experimental SIMAGIC EVO compatibility**. When disabled, SPM may show the detected model but does not apply profiles or tune the EVO.

With the switch on, only the common mapped settings are writable. Smoothness, Feedback Frequency and Torque Limit have unverified EVO offsets and are **not writable**; profile application skips them with a warning. This has not been tested on physical EVO hardware yet. Legacy Alpha support remains the stable path.

EVO testers: capture **Settings → Diagnostics → CAPTURE EVO STATUS (0x81)** before and after changing one setting in SimPro Manager. Include the exact model, PID and both raw reports when using **Report a Bug**. Close SimPro Manager before allowing SPM to write to the wheelbase.

## Beta updates and feedback

SPM checks the public [`update-manifest-beta.json`](update-manifest-beta.json), downloads a release package and verifies its SHA-256 checksum before installing it. Versions `0.1.0-beta.1` and `0.1.0-beta.2` still point to the former private update location: install `0.1.0-beta.3` or newer manually **once** to switch to this public update channel.

Please use **Report a Bug** inside the plugin. Include what you were doing, the game/car and what happened. Do not post private logs or personal information in public issues without checking them first. Backup restore is not yet available in the beta UI.

Simagic Profile Manager is an independent community project, not affiliated with, endorsed by or supported by SIMAGIC or SimHub. SIMAGIC and SimHub are trademarks of their respective owners.
