# Simagic Profile Manager

Simagic Profile Manager (SPM) is a SimHub plugin focused on **live tuning** your SIMAGIC wheelbase. Adjust supported settings in real time from SimHub, the SPM dashboard, a touchscreen or mapped controls on your wheel—without stopping to open a separate tuning app.

Save your settings as setups and **assign them to specific cars or classes** in each game. SPM can then load the matching setup automatically when you change cars; you can also switch setups manually whenever you want. For games without car or class information, you can assign a setup to the game itself.

## Public beta

SPM is currently in public beta. Some features may not work exactly as planned yet, especially with SIMAGIC Alpha EVO wheelbases.

If something goes wrong, tell us on [Discord](https://discord.gg/4XXsaW3CTe). The in-plugin bug report form is temporarily unavailable.

## Install

1. Download [SimagicProfileManager-0.1.0-beta.8.zip](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases/download/v0.1.0-beta.8/SimagicProfileManager-0.1.0-beta.8.zip) and extract it. You only need this one ZIP; there is no installer.
2. Close SimHub.
3. Copy **all three DLL files** from the ZIP's `Plugin` folder into your SimHub installation folder (usually `C:\Program Files (x86)\SimHub`). If you are updating, allow Windows to replace the old SPM files. Administrator permission may be required.
4. Double-click `Dashboard\Simagic Profile Manager.simhubdash` from the ZIP. SimHub will open and import the dashboard automatically.
5. Open Simagic Profile Manager in SimHub and follow First Start Setup. To import existing SimPro 2 setups, export them from SimPro 2 to files first.

When updating manually, always replace all three DLLs together. Your saved setups and assignments are kept separately and are not removed by replacing the plugin files.

## SIMAGIC Alpha EVO: experimental support

Alpha EVO Sport, EVO and EVO Pro support is **experimental and off by default**. If you want to try it, enable **Settings → Beta → Enable experimental SIMAGIC EVO compatibility**. Until you enable it, SPM will not apply profiles or tune an EVO wheelbase.

EVO support is still being tested, so some features may not work as intended. If you run into a problem, tell us your EVO model and what happened on [Discord](https://discord.gg/4XXsaW3CTe). The older Alpha series is more thoroughly tested.
