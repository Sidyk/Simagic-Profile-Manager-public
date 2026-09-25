# Simagic Profile Manager

Simagic Profile Manager (SPM) is a SimHub plugin for saving, tuning and switching SIMAGIC wheelbase setups. You can import setups exported from SimPro 2 and use the manager from SimHub, a display or a phone.

## Public beta

SPM is still in beta. Features may change and some setups or wheelbases may not behave as expected. Keep a backup of your important setups and check the values on your wheelbase after applying a profile. We recommend closing SimPro Manager while SPM is loading or tuning setups so the two apps do not change the wheelbase at the same time.

If something goes wrong, tell us on [Discord](https://discord.gg/4XXsaW3CTe). The in-plugin bug report form is temporarily unavailable.

## Install

1. Download the ZIP from the [newest beta release](https://github.com/Sidyk/Simagic-Profile-Manager-public/releases) and extract it. You only need this one ZIP; there is no installer.
2. Close SimHub and SimPro Manager.
3. Copy **all three DLL files** from the ZIP's `Plugin` folder into your SimHub installation folder (usually `C:\Program Files (x86)\SimHub`). If you are updating, allow Windows to replace the old SPM files. Administrator permission may be required.
4. Double-click `Dashboard\Simagic Profile Manager.simhubdash` from the ZIP. SimHub will open and import the dashboard automatically.
5. Open Simagic Profile Manager in SimHub and follow First Start Setup. To import existing SimPro 2 setups, export them from SimPro 2 to files first.

When updating manually, always replace all three DLLs together. Your saved setups and assignments are kept separately and are not removed by replacing the plugin files.

## SIMAGIC Alpha EVO: experimental support

Alpha EVO Sport, EVO and EVO Pro support is **experimental and off by default**. If you want to try it, enable **Settings → Beta → Enable experimental SIMAGIC EVO compatibility**. Until you enable it, SPM will not apply profiles or tune an EVO wheelbase.

Some EVO settings are not yet confirmed and may be missing or shown differently from SimPro Manager. Check every value carefully before driving. If a value looks wrong, stop using SPM to change that setting and let us know your exact EVO model and what happened on [Discord](https://discord.gg/4XXsaW3CTe). The older Alpha series remains the more thoroughly tested option.
