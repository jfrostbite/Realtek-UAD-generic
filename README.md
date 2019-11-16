### Compatibility
This Realtek UAD driver mod should install and function properly on all systems supporting Realtek Legacy HDA FF00 drivers that don't rely on any special audio enhancements. If used with devices relying on special audio enhancements functionality and feature set available may be limited.
### Project motivation
I have an old system that is not supported by OEM specific Realtek UAD drivers and I found HDA drivers to be very large, bloated and causing an unpleasant issue when equalizer was installed that was a pain to live with. Realtek UAD generic drivers were not affected so I permanently switched to them. But Realtek doesn't provide complete and official UAD generic drivers very often so I decided to custom craft it from parts since I discovered it is possible to do so without breaking WHQL signature.
### Repository contents
- source code of installer and updater used by this package;
- new release everytime official package that this mod is based on is updated on Realtek FTP server.
### How this package is built
- Download latest `{version}_UAD_RTK*.zip` or  `{version}_UAD_WHQL_RTK*.zip` whichever is the newer version from `ftp://spcust@ftp3.realtek.com/Realtek`; [1]
- Download and extract last available release;
- Extract `RTKVHD64.sys`and `RTAIODAT.DAT` from source codec folder, either `Win64` or `Win64\Realtek\Codec*` or `Realtek\Codec*` to `Realtek-UAD-generic\Win64\Realtek\UpdatedCodec` overwriting existing files; [1]
- Remove `RealtekAPO_*`, `RealtekHSA_*` and `RealtekService_*` folders from `Realtek-UAD-generic\Win64\Realtek`; [1]
- Extract `RealtekAPO_*`, `RealtekHSA_*` and `RealtekService_*` folders from RTK package located either under `Win64\Realtek` or `Realtek` folder to `Realtek-UAD-generic\Win64\Realtek`. [1]

Note [1]: `*` means any number or characters or both or absolutely nothing.
### Official installer
The MSI RTK package that this mod is most of time based off contains the official Realtek UAD installer. If you prefer it over my custom made open-source installer, move Win64 folder inside Official-Setup folder and run setup.exe as admin from there. Not all releases will have the official setup available.
