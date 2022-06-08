# Grand Prix Legends installer <small>(wip)</small>

Grand Prix Legends installer for Wine

Creates wine prefix, mounts iso, downloads and runs the installer

## Install

- Download
  'https://raw.githubusercontent.com/D10221/grand-prix-legends-installer/main/gplnx'

```bash
wget 'https://raw.githubusercontent.com/D10221/grand-prix-legends-installer/main/gplnx
```

- make it executable\
  `chmod +x gplnx`
- run it

```bash
./gplnx install
```

## Installation details

By default

It creates a new wine prefix at `~/.local/share/GPL/pfx`

And keeps the downloads at `~/.cache/GPL`

## Start ing GPL and GEM+

```
  WINEPREFIX=~/.local/share/GPL/pfx wine 'c:\Sierra\GPL\gpl.exe'
```

```
  WINEPREFIX=~/.local/share/GPL/pfx wine 'c:\GPLSecrets\app\GEM+\GEMP2.exe'
```
Or you can use this tool 

```
  ./gplnx start gpl 
  
```
it should start gpl.exe with ~/.local/share/GPL/pfx as wine prefix

```
  ./gplnx start gem 
```

it should start GEMP2.exe with ~/.local/share/GPL/pfx as wine prefix

```
  ./gplnx start gplc67

```
  It should start gplc67.exe with ~/.local/share/GPL/pfx as wine prefix


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
    - shasum
    - udisksctl
    - file
    - grep
    - [innoextract](https://constexpr.org/innoextract/)
    - xdg-open
On Ubuntu you prob need innoextract only , the rest  are built in

## Downloads:

- GrandPrixLegends.iso from archive.org
- gplinstall_beta_1.08.exe from grandprixlegends.info

## Notes:

- on 'wsl' you will need get 'X' working, see
  [gwsl](https://opticos.github.io/gwsl/)
- on 'wsl' wine doesn't see the mounted drive even when successfully mounted

# Usage

```
Grand Prix Legends wine Installer v0.0.1
Usage: 'gplnx [verb] [options]'
Verbs: 
  install [options?] [target]?   'run GPL installers'
      options:
          -h help
      target:
          gpl gem vbr
      example:
          $gpli install -r gpl # REINSTALL gpl
          $gpli install -r gpl gem vbr # reinstall gpl gem -u vbr
      Notes:   gem target has options see install gem -h for details
  uninstall [options?] 'remove cache,GPL,GEM and wine Prefix'
      options: 
          'gpl'   remove 'c:\Sierra\gpl'
          'geml'  remove 'c:\Sierra\gpl'
          'pfx'      remove 'prefix' (default)
  run [cmd]
      "run something on gpl's WINEPREFIX"
      examples:
          '$gplnx run wine winecfg'
  wine [cmd]
      "run wine 'something' on gpl's WINEPREFIX"
      examples:
          '$gplnx wine winecfg'
  open [options] [path]
      opens $WINEPREFIX location or sub location with default file manager or terminal
      options:
              -x with default filemanager
              -t with default terminal
              -h shows this
      examples:
          '$gplnx open' # opens $WINEPREFIX
          '$gplnx open dirve_c ' # opens $WINEPREFIX/drive_c
          '$gplnx open 'c:\Sierra' ' # opens $WINEPREFIX/drive_c/Sierra
  start [what]
      starts GPL or GEM+
      examples:
          '$gplnx start gpl'  # starts wine 'c:\Sierra\GPL\gpl.exe'
          '$gplnx start gem+' # starts wine 'c:\GPLSecrets\GEM+\GEMP2.exe'

Options:
  -h --help      'Show this'
  -v --version   'Show 'gplnx' version'
  --nomount      'Do not try to mount ISO'

Vars:
 NOMOUNT         'Do not try to mount ISO'
 NOUSERMOUNT     'Do not try to mount ISO in userspace'
 NOROOTMOUNT     'Do not try to mount ISO if requires root access
 DEBUG           'show debug info'
                  example '$ DEBUG='*' ./gpli.local install'
```
