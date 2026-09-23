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

Supported wheelbases in this beta: **SIMAGIC Alpha Mini, Alpha and Alpha Ultimate**. SIMAGIC EVO wheelbases are **not supported**. Game/car/class detection depends on the data provided by SimHub.

> [!WARNING]
> This is beta software that can change wheelbase settings. Check setup values before applying them and keep a backup of important profiles. **We recommend closing SimPro Manager 2 while using SPM to load or tune setups**, so the two applications do not try to control the wheelbase at the same time. SimPro 2 can still be used to export profiles for import into SPM.

## Download

Get the [latest beta release](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases). Choose the complete `SimagicProfileManager-Setup-<version>.zip` package for the easiest installation. The same release also provides the individual DLLs and dashboard. For direct downloads from the repository, see [`manual/`](manual/).

Current manual-copy files (`0.1.0-beta.3`):

| File | Destination |
| --- | --- |
| [`User.SimagicProfileV2.dll`](manual/User.SimagicProfileV2.dll) | SimHub installation folder |
| [`SimagicProfileV2.Core.dll`](manual/SimagicProfileV2.Core.dll) | SimHub installation folder |
| [`SimagicProfileV2.Devices.dll`](manual/SimagicProfileV2.Devices.dll) | SimHub installation folder |
| [`Simagic Profile Manager.simhubdash`](manual/Simagic%20Profile%20Manager.simhubdash) | Import through SimHub Dash Studio; **do not** put it beside the DLLs |

The `manual/` files must always be used **together from the same version**. Do not mix DLLs from different releases.

## Install with the release package (recommended)

1. Install and open SimHub at least once, then close it completely. Close SimPro Manager 2 as well.
2. Download the release ZIP and extract it to a normal folder. Do not run the installer from inside the ZIP.
3. Open PowerShell **as Administrator** in the extracted folder and run `./Install.ps1` (or `./Install.ps1 -SimHubPath 'D:\Your\SimHub'` for a non-default installation).
4. Start SimHub and open **Simagic Profile Manager**. Follow the **First Start Setup** guide.

The installer copies the three DLLs and installs the dashboard. It backs up any previous SPM DLLs/dashboard before replacing them. It does **not** erase your setups or assignments in `%LOCALAPPDATA%\SimagicProfileManager`.

## Install by copying files manually

1. Close SimHub and SimPro Manager 2. Download **all four** files from [`manual/`](manual/) using each file's **Download raw file** button, or download the matching individual assets from [Releases](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases).
2. Find your SimHub installation folder — usually `C:\Program Files (x86)\SimHub`, containing `SimHubWPF.exe`. Back up any existing SPM DLLs there.
3. Copy the **three DLLs** into that folder, alongside `SimHubWPF.exe`. Allow Windows to replace the older SPM DLLs. Administrator permission may be required.
4. Import `Simagic Profile Manager.simhubdash` in SimHub's Dash Studio. This is a dashboard package, **not** a DLL and not a file to copy into the SimHub root folder.
5. Restart SimHub, open **Simagic Profile Manager**, and complete First Start Setup.

If updating an existing manual installation, replace **all three DLLs** and reimport the matching dashboard. Your user data stays in `%LOCALAPPDATA%\SimagicProfileManager`.

## First Start Setup

The guide walks you through choosing touch, buttons or both; mapping controls (optional); choosing a screen/DDU or phone/tablet (optional); and importing SimPro 2 exports or starting with an empty library. SimPro 2 profiles must be **exported to files first** and then selected in the import step. Choose the destination game when importing.

After setup, use **Profiles** to create/import/edit setups and **Auto Switch** to assign them to a game-specific car or class. Use **Settings → Display** to choose a SimHub screen or get the phone/tablet address and QR code. Phone/tablet and the SimHub PC must be on the same local network; allow incoming SimHub connections through the firewall. You can revisit onboarding from **Settings → First Start Setup** without deleting existing profiles.

## Beta updates and feedback

SPM checks the public [`update-manifest-beta.json`](update-manifest-beta.json), downloads a release package and verifies its SHA-256 checksum before installing it. Versions `0.1.0-beta.1` and `0.1.0-beta.2` still point to the former private update location: install `0.1.0-beta.3` manually **once** to switch to this public update channel.

Please report bugs using **Beta Report** inside the plugin. Include what you were doing, the game/car and what happened. Do not post private logs or personal information in public issues without checking them first. Backup restore is not yet available in the beta UI.

Simagic Profile Manager is an independent community project, not affiliated with, endorsed by or supported by SIMAGIC or SimHub. SIMAGIC and SimHub are trademarks of their respective owners.
