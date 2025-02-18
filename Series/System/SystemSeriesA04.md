# A04 ❯ Snapd Installation Guide

ℹ️ This article is part of AlmaLinux [System Series](../../series/).

***

\| 💡 | Experience Level | ⭐☆☆☆☆ | |--- | --------- | --------| | 📆 | Last modified | 2023-06-07 | 🔧 | Tested by\
↳ version \\| platform \\| date | NOT TESTED YET |\


## 🌟 Introduction

The snap packages for AlmaLinux can be found in the Extra Packages for Enterprise Linux (EPEL) repository. :package:

## Enable EPEL repo :minidisc:

If you haven’t done it yet, enable the EPEL repository for your AlmaLinux system:

```
sudo dnf install epel-release
sudo dnf upgrade
```

## Install :hammer\_and\_wrench:

:::tip :information\_source: Important for cloud images users!

Before proceeding with the installation of snapd, it’s important to install the `kernel-modules` package as these type of images come with limited number of modules. This package includes SquashFS, a compressed read-only file system for Linux, which is necessary for the snapd functionality. :::tip

Install the `kernel-modules`, using the following command:

```
sudo dnf install kernel-modules
```

With the EPEL repository and kernel-modules added to your AlmaLinux installation, you can now install the snapd package: :inbox\_tray:

```
sudo dnf install snapd
```

## Set up :gear:

Next, instruct systemd to enable the unit providing the snapd communication socket:

```
sudo systemctl enable --now snapd.socket
```

Then, enable classic snap support, create a symbolic link it requires:

```
sudo ln -s /var/lib/snapd/snap /snap
```

### Last installation step :checkered\_flag:

To make sure the paths for snapd are updated correctly, you just need to re-login. Reboot will work too. :arrows\_counterclockwise:

Congratulations, snapd is now installed and fully operational! :tada:

### Optional: for Desktop Users :desktop\_computer:

If you’re using a desktop environment, consider installing the Snap Store app (https://forum.snapcraft.io/t/installing-the-snap-store-app/10077) 🛍️
