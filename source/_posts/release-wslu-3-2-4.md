---
title: wslu 3.2.4 LTS (finally) released!
date: 2022-03-19 17:01:21
---

This is a update that people have been waiting for a really long time... it packs a lot of important fixes for the issues that people have a lot of headache with. Hope you enjoy this update! Here is a full changelog:

## Documentation

- Update Information for multiple Linux distributions (PR #203 by @crramirez )
- moving documentation to the official documentation site
- Improvement on manpage deployment

## Improvements

- wslu: provides a more detailed WSL Interoperability Check ([Details](https://s.patrickwu.space/sgfzs))
- wslu: improve parsing `/etc/wsl.conf` (fixes #200)
- wslvar: Allow variable names with parentheses (PR #212 by @diddledani )
- wslview: simplification of codes (closes #216)

 ## Bug Fixes

- wslu: ensuring `baseexec` works (PR #222 by @crramirez )
- wslu: disable `chcp` workaround for higher versions of Windows (fixes #199)
- wslu: fix an issue in WSL_INTEROP not properly set in WSL2 (fixes #215)
- wslview: fix an issue in not properly opening the file (fixes #198 , PR #201 by @IssacOscar )
- wslusc: fix a deprecated `which` command issue (fixes #205 , PR #203 by @crramirez )



Finally, if there is still any issue, don't hesitate to report to <https://github.com/wslutilities/wslu/issues>.