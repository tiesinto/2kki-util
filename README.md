## 2kki-util
This script simply takes Yume 2kki game archives and patches which you download from the <a href="https://wikiwiki.jp/yumenikki-g3/#Schedule">2kki Wiki</a> and does the following:
- Applies the patch (should you have specified one);
- Adds the <a href="https://tkool.jp/products/rtp/2000rtp.zip">japanese RPG Maker 2000 RTP</a> and its <a href="https://tkool.jp/products/rtp/RTP_patchk_190612.zip">patch</a>;
- Adds the <a href="https://github.com/ynoproject/ynotranslations">YNO translations</a> to the game folder;
- Converts all audio to Opus to reduce the game size to ~2GB;
- Patches the RPG_RT.ini to be able to use EasyRPG's widescreen hacks.

Run the script with --help to get started. Currently the script is only tested on Artix and Debian Linux with the Dash shell.

> N.B: Only the top level of directories in patches are applied to the game files case-insensitively (e.g. `GameOver` and `Gameover` will not conflict)—files and deeper subdirectories are not checked for matches and will be copied as normal.

## Dependencies
- curl for downloading
- unar for extracting
- opusenc for converting to Opus
- ffmpeg for converting ABPCM
- lame for converting MP3
- unshield for extracting the CAB files

> N.B: 7zip can also be used to speed up extraction although 7zip's support for the encoding that Yume 2kki uses is unpredictable or nonfunctional with archive formats that are not .7z. If you have issues using the `-7` flag then do not use it.

## Credits
The install_rtp() function was adapted from the <a href="https://aur.archlinux.org/packages/rpg2000-rtp">rpg2000-rtp PKGBUILD</a> written by <a href="https://github.com/carstene1ns">Carsten Teibes</a> of <a href="https://github.com/EasyRPG/Player">EasyRPG</a>; the rest of the script was written by tiesinto.
