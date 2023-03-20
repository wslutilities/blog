---
title: 'From OBS to COPR: A migration of wslu packages'
date: 2023-03-21 01:47:17
tags:
---


Currently, we are using [Open Build Service](https://openbuildservice.org/) to build our packages for various distributions as well as [Copr](https://copr.fedorainfracloud.org/) for Fedora. However, I recently found that OBS has some issues with the build process of `wslu` packages. So I decided to migrate several packages to COPR. Currently, the migration is completed.

The following distributions installation are affected:
- CentOS 8/Stream 9
- Red Hat Enterprise Linux 8/9
- Oracle Linux 8/9
- OpenSUSE Leap 15.*
- OpenSUSE Tumbleweed
- SUSE Linux Enterprise Server 12
- SUSE Linux Enterprise Server 15

For CentOS/Red Hat/Oracle Linux, Version 7 will still be kept in OBS. For SUSE Linux Enterprise Servers (12/15) it will be kept in OBS as well, but SUSE Linux Enterprise Server 15 SP3/SP4 and 12 SP5 will be only supported.

For SUSE Linux Enterprise Server 15 SP3/SP4 and 12 SP5, there are also some changes in the installation process. Please remove the OBS repository and re-add the repository like this:

**For SUSE Linux Enterprise Server 15 SP3/SP4:**

```
sudo zypper addrepo https://download.opensuse.org/repositories/home:/wslutilities/SLE_15/home:wslutilities.repo
sudo zypper addrepo https://download.opensuse.org/repositories/graphics/SLE_15_SP3/graphics.repo
sudo zypper up
sudo zypper in wslu
```

**For SUSE Linux Enterprise Server 12 SP5:**

```
sudo zypper addrepo https://download.opensuse.org/repositories/home:/wslutilities/SLE_12_SP5/home:wslutilities.repo
sudo zypper addrepo https://download.opensuse.org/repositories/graphics/SLE_12_SP5/graphics.repo
sudo zypper up
sudo zypper in wslu
```


For OpenSUSE, 15.1/15.2 is no longer supported and 15.3/15.4 will be only supported in COPR. Please remove the OBS repository and add the COPR repository instead:

```
SUSE_VERSION="$(grep VERSION= /etc/os-release | sed -e s/VERSION=//g -e s/\"//g -e s/-/_/g)"
sudo zypper addrepo https://copr.fedorainfracloud.org/coprs/wslutilities/wslu/repo/opensuse-leap-${SUSE_VERSION}/wslutilities-wslu-opensuse-leap-${SUSE_VERSION}.repo
sudo zypper up
sudo zypper in wslu
```

For OpenSUSE Tumbleweed, the OBS repository will be removed and the COPR repository will be added instead. Please remove the OBS repository and add the COPR repository instead:

```
sudo zypper addrepo https://copr.fedorainfracloud.org/coprs/wslutilities/wslu/repo/opensuse-tumbleweed/wslutilities-wslu-opensuse-tumbleweed.repo
sudo zypper up
sudo zypper in wslu
```

For CentOS/Red Hat/Oracle Linux Version 8 or higher, the OBS repository will be removed and the COPR repository will be added instead. Please remove the OBS repository and add the COPR repository instead:

```

# for CentOS/RHEL 8 only
sudo dnf install epel-release dnf-plugins-core
sudo dnf config-manager --set-enabled PowerTools

sudo dnf copr enable wslutilities/wslu
sudo dnf install wslu
```

For further information, please visit our [installation guide](https://wslutiliti.es/wslu/install.html). If there is any issue with the installation, don't hesitate to report to <https://github.com/wslutilities/wslu/issues>.

