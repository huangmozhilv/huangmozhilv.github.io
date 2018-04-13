---
layout: post
title: "Share Clipboard & Files between VirtualBox and Host System"
date: 2018-04-13
tags: [VirtualBox, Linux]
comments: true
---

**Host system: Windows 10**

**Guest system: Ubuntu 16.0 in VirtualBox**

**Goal 1** To copy and paste text from Clipboard btw VirtualBox Linux and Windows host.

**Goal 2** To share files btw VirtualBox Linux and Windows host. NOTE: all shared files should be placed in a shared folder which will be mentioned below.

## STEP 1

Open VirtualBox, single-click "ubuntu 16.0", click Settings > General > Advanced, set "Shared Clipboard" and "Drag'n'Drop" from "Disabled" to "Bidirectional", then run "ubuntu 16.0".

Alternatively, open VirtualBox, run "ubuntu 16.0". On left-top of Linux, click Devices > Shared Clipboard > Bidirectional, click Devices > Drag and Drop > Bidirectional.

## STEP 2 

On left-top of Linux, click Devices > Shared Folders > Shared Folders Settings > Shared Folders > Machine Folders > + > choose/create a shared folder. For me, I created a folder as "D:\ProgramFiles\Oracle\sharedBothVinLinux". NOTE: this folder is physically stored on Windows host.

## STEP 3

On left-top of Linux, click Devices > Insert Guest Additions CD image. If you get an error message as below:

> Unable to insert the virtual optical disk /usr/share/virtualbox/VBoxGuestAdditions.iso into the machine LM173KDE_Basic.
Could not mount the media/drive '/usr/share/virtualbox/VBoxGuestAdditions.iso' (VERR_PDM_MEDIA_LOCKED).
Result Code: NS_ERROR_FAILURE (0x80004005)
Component: ConsoleWrap
Interface: IConsole {872da645-4a9b-1727-bee2-5585105b9eed}
Callee: IMachine {b2547866-a0a1-4391-8b86-6952d82efaa0}

It means the Devices already has the .iso file. Please eject it: click Devices > Optical Drives > check VBoxGuestAdditions.iso, click Devices > Optical Drives > Remove disk from virtual drive; or go to files manager, eject VBox_GAs_5.2.8.

## STEP 4

Go to Terminal, run `sudo apt-get install virtualbox-guest-utils`.

## STEP 5

To access the shared folder as root/superuser, go to Terminal. `cd /media/`, `sudo mount -t vboxsf sharedBothWinLinux /media/sf_sharedBothWinLinux/`. NOTE:`sf_` was prefixed to the shared folder name by default.
