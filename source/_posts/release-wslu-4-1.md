---
title: wslu 4.1.0 is now released
date: 2022-10-27 11:20:07
---

Firstly, Happy holidays to everyone! (Also happy birthday to myself)

As promised, I released wslu 4.1.0 at the end of this year. Here is the changelog:

## Improvements

- wslu: additional allowed configuration file in `/etc/wslu/`
- wslsys: add systemd status check
- wslfetch: add systemd status check
- wslusc: add `ffmpeg` engine (#239)

## Bug Fixes

- wslview: fixes the potential of not opening the links/files (#256 and #243)
- wslu: allow handling quoted configurations in `wsl.conf` (#247)
- wslu: Correctly show the wslu version (#245)
- wslview: fixes `-E` not working (#250)



The release will be gradually rolled out to different distributions. Finally, if there is still any issue, don't hesitate to report it to <https://github.com/wslutilities/wslu/issues>.