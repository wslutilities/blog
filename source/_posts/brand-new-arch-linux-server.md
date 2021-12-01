---
title: Arch Linux package server now available!
date: 2021-12-01 16:40:32
---

Last year, `wslu` got removed from AUR due to violating its policies([original notice](https://lists.archlinux.org/pipermail/aur-requests/2020-September/044992.html)):


> The AUR does not permit upload of packages ?which are intended for a non-Arch distribution, and are not useful, or don't work, on Arch.
>
>
>
> AUR packages must be written with the intention of working and achieving their purpose, at a minimum, on archlinux x86_64 (but may optionally support additional targets, e.g. ARM support is popular, Manjaro users often upload manjaro themes that can be equally used on Arch, users of parabola or artix upload openrc/runit based packages which can be used to install the official Arch installation media, then build your own alternative init system and replace systemd, thus being functional and useful on archlinux).

Basically it means due to there is no official support for Arch Linux on WSL, `wslu` will not allowed in the AUR.

But now I got good news!

We now have a dedicated server for Arch Linux for you! You can add the repository using the following method:

1. If not done so, initial `pacman-key` with `pacman-key --init`;
2. add the WSL Public Signing Key to `pacman` from the keyserver from keyserver using `pacman-key -r A2861ABFD897DD37` or download from our website and import the key:
```
wget https://pkg.wslutiliti.es/public.key
pacman-key --add public.key
```
3. Locally sign the key with `pacman-key --lsign-key A2861ABFD897DD37`;
4. add the following content in your `/etc/pacman.conf`:
```
[wslutilities]
Server = https://pkg.wslutiliti.es/arch/
```
5. Now update the repository and now you can directly download `wslu`!

If there is any issue with the repository, don't hesitate to report to <https://github.com/wslutilities/wslu/issues>.
