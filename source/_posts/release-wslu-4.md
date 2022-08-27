---
title: wslu 4.0.0 is now finally released
date: 2022-08-27 18:55:27
---

After 2 years of (sporadic) development,  wslu 4.0.0 is now finally released with a lot of changes! Here is the changelog:

## Documentation

- Allow automatic manpage update
- Improve the contribution document

## Improvements

- wslu: `--debug` now usable; could work with `--verbose` properly now
- wslu: add Gentoo Linux, AlmaLinux, CBL Mariner, and Clear Linux support
- wslact: include new tool "memory reclaim"
- wslclip: brand new CLI (closes #221)
- wslfetch: add `-g, --generic`: this force the cli to use the generic WSL theme
- wslfetch: add `-t, --theme`: you can now provide your logo and color palette to use. also available as conf `WSLFETCH_THEME_PATH`
- wslfetch: add `-o, --options`: you can now customize what information to list out. also available as conf `WSLFETCH_INFO_SECTION`
- wslfetch: add conf `WSLFETCH_COLORBAR`: allows you to control color bar without passing param
- wslgsu: brand new CLI
- wslsys: add `-i, --ip`: get current WSL's IPv4 address. (closes #139 by #156 )
- wslsys: add `-T, --win-system-type`: get whether the WSL is running on Desktop or Server
- wslsys: add `-n, --name`: allow using the name to get the corresponding items
- wslsys: improvement on the speed to start up with a complete rewrite.
- wslusc: add `-s, --smart-icon`: add smart icon detection. Requires `wslpy`. can be set with conf `WSLUSC_SMART_ICON_DETECTION` (closes #176)
- wslusc: add `-d, --shortcut-debug`: allows you to view content of the generated shortcuts or any shortcuts
- wslusc: add `-N, --native`: allows you to generate shortcut using the native Wayland support. can be set with conf `WSLUSC_GUITYPE`
- wslvar: add configuration `WSLVAR_DEFAULT_VARTYPE`: this allows you to set default type of variable to get when not specifying option.
- wslview: add `-E, --engine`: you can now set the default method to start websites/folders/files. can be set with conf `WSLVIEW_DEFAULT_ENGINE` (closes #167, #197)

## Breaking Changes

- wslu: brand new configurations; default configuration located in /usr/share/wslu/conf
- wslu: individual version components are removed; they are hard to track
- wslu: ImageMagick is now a recommended dependency (closes #236 )
- wslact: `time-sync` is now `time-react`
- wslfetch: `-l, --line` and `-s, --splash` are removed with low usage

## Bug Fixes
- wslu: overall improvements on the code style to prevent problematic inputs
- wslview: redesigning the system to improve the detection (closes #181)



The release will be gradually rolled out to different distributions. Finally, if there is still any issue, don't hesitate to report it to <https://github.com/wslutilities/wslu/issues>.