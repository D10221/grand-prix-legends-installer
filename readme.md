# Grand Prix Legends installer <small>(wip)</small>
Grand Prix Legends installer for Wine

Creates wine prefix, mounts iso, downloads and runs the installer

## Works on:
  - Ubuntu
  - Maybe Debian/Ubuntu derivatives
  - MacOS
  - WSL (partially)

## Tested on:
  - Ubuntu 20.4
  - MacOS Monterrey 12.3.1
  - Windows 10 Wsl Ubuntu 20.4

## Requires:
   - bash 'on mac may require `brew install bash`'
   - wget
   - wine
   - md5sum|shasum
   - udisksctl
   - file
   - grep

## Downloads:
   - GrandPrixLegends.iso from archive.org
   - gplinstall_beta_1.08.exe from  grandprixlegends.info

## Notes:
  - on 'wsl' you will need get display working
  - on 'wsl' wine doesn't see the mounted drive even when successfully mounted

### TODO:
  - download dependencies and setup prefix for vb6 dependencies
  - redo argument parsing, its very picky about switch order
  - don't download until required
  - switches: NODOWNLOAD, NOCHECKSUM
  - uninstall doesn't uninstall but nukes the wine prefix
  - switch: --info, display installation details