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
  - on 'wsl' you will need get 'X' working, see [gwsl](https://opticos.github.io/gwsl/)
  - on 'wsl' wine doesn't see the mounted drive even when successfully mounted

### TODO:
  - download dependencies and setup prefix for vb6 dependencies
  - redo argument parsing, its very picky about switch order
  - switches: NODOWNLOAD, NOCHECKSUM
  - switch: --info, display installation details
  - switch: --reinstall or verb 'reinstall'