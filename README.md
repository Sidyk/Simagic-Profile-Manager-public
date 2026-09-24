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

Download [SimagicProfileManager-0.1.0-beta.6.zip](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases/download/v0.1.0-beta.6/SimagicProfileManager-0.1.0-beta.6.zip). This one ZIP contains all three plugin DLLs and the dashboard. Installation is manual; no installer or separate downloads are needed. For future versions, get the ZIP from the [latest beta release](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases).

## Install

1. Install and open SimHub at least once. Then close SimHub and SimPro Manager 2.
2. Extract the ZIP. Copy **all three DLLs** from its `Plugin` folder into the SimHub installation folder (usually `C:\Program Files (x86)\SimHub`, beside `SimHubWPF.exe`). Allow Windows to replace existing SPM DLLs; administrator permission may be required.
3. Double-click `Dashboard\Simagic Profile Manager.simhubdash` from the extracted ZIP. SimHub will open and import the dashboard automatically.
4. Open **Simagic Profile Manager** in SimHub and follow the **First Start Setup** guide.

Always replace all three matching DLLs when updating manually. Your setups and assignments in `%LOCALAPPDATA%\SimagicProfileManager` remain untouched. Once installed, SPM can still apply later SHA-256-verified beta updates through its built-in updater.

## First Start Setup

The guide walks you through choosing touch, buttons or both; mapping controls (optional); choosing a screen/DDU or phone/tablet (optional); and importing SimPro 2 exports or starting with an empty library. SimPro 2 profiles must be **exported to files first** and then selected in the import step. Choose the destination game when importing.

After setup, use **Profiles** to create/import/edit setups and **Auto Switch** to assign them to a game-specific car or class. Use **Settings → Display** to choose a SimHub screen or get the phone/tablet address and QR code. Phone/tablet and the SimHub PC must be on the same local network; allow incoming SimHub connections through the firewall. You can revisit onboarding from **Settings → First Start Setup** without deleting existing profiles.

## Experimental Alpha EVO support

Version `0.1.0-beta.6` can detect Alpha EVO Sport (`3670:0500`), Alpha EVO (`3670:0501`) and Alpha EVO Pro (`3670:0502`). EVO reads and writes remain **off until you explicitly enable Settings → Beta → Enable experimental SIMAGIC EVO compatibility**. When disabled, SPM may show the detected model but does not apply profiles or tune the EVO.

With the switch on, only the common mapped settings are writable. Smoothness and Feedback Frequency have unverified EVO offsets and are **not writable**; profile application skips them with a warning. An EVO Sport tester reports that EVO has no separate Max Torque control: FFB strength is its user-facing strength setting. The legacy Torque Limit profile field remains unsupported on EVO, and raw byte 23 is not identified as Max Torque. One EVO Sport before/after report correlates byte 48 with Dynamic Prediction, byte 50 with Filter Level and byte 52 with Slew Rate; these remain diagnostic-only, and the reported Filter Level did not match byte 50 one-to-one. These observations do not verify the mappings across EVO models. Legacy Alpha support remains the stable path.

The Diagnostics page now offers a manual hardware refresh and an optional 1.5-second live monitor to compare actual wheelbase values with the active SPM profile. SimPro 2/3 detection remains informational; its warning and shutdown guard are temporarily disabled in this beta.

EVO testers: capture **Settings → Diagnostics → CAPTURE EVO STATUS (0x81)** before and after changing one setting in SimPro Manager. Include the exact model, PID and both raw reports when using **Report a Bug**. Close SimPro Manager before allowing SPM to write to the wheelbase.

## Beta updates and feedback

SPM checks the public [`update-manifest-beta.json`](update-manifest-beta.json), downloads a release package and verifies its SHA-256 checksum before installing it. Versions `0.1.0-beta.1` and `0.1.0-beta.2` still point to the former private update location: install `0.1.0-beta.3` or newer manually **once** to switch to this public update channel.

Please use **Report a Bug** inside the plugin. Include what you were doing, the game/car and what happened. Do not post private logs or personal information in public issues without checking them first. Backup restore is not yet available in the beta UI.

Simagic Profile Manager is an independent community project, not affiliated with, endorsed by or supported by SIMAGIC or SimHub. SIMAGIC and SimHub are trademarks of their respective owners.
