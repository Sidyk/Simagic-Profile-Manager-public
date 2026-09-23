# Simagic Profile Manager — public beta

This repository is the binary distribution and update channel for Simagic Profile Manager. It does not contain the source code or build system.

Download the latest [release](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases), extract `SimagicProfileManager-Setup-<version>.zip`, close SimHub, then run `Install.ps1` from an elevated PowerShell window. The package contains the plugin DLLs, the SimHub dashboard, installer and uninstall scripts. Existing profiles and assignments are preserved.

The plugin checks [`update-manifest-beta.json`](update-manifest-beta.json) for new beta versions and verifies the release ZIP against its SHA-256 checksum before installation. The manifest is updated only after the matching release is published.

Versions up to `0.1.0-beta.2` point to the former update location, which is now private. Install `0.1.0-beta.3` manually once to move to this public update channel; later updates can be installed from within the plugin.

Simagic Profile Manager is an independent community project, not affiliated with SIMAGIC or SimHub. Use the plugin and wheelbase tuning at your own risk.
