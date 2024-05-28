---
author: clausmalver
title: Enabling RSAT tools for Powershell
description: How to enable the RSAT tools in a closed enviroment.
date: 2024-05-28
categories: [Notes, Powershell]
tags: [rsat, powershell]
---
When installing RSAT Tools, you may encounter the error Error 0x800F0954. This occurs because the system cannot contact the Windows Update server, as the computers are set up to download updates from a WSUS server. This error will occur regardless of whether you install via the GUI (Settings - Apps - Optional features - Add a feature - RSAT: Active Directory Domain Services and Lightweight Directory Services Tools) or via PowerShell. To resolve this, follow these steps:

1. Open _regedit_ as an admin and navigate to:
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU`
2. Find `UseWUServer` and change the value to 0.

Once the change is made, Windows Update needs to be restarted. You cannot restart the computer, as the GPO will update regedit back to its previous state upon a reboot.

Open a PowerShell prompt as an administrator:
```Powershell
net stop wuauserv
```

Then run:
```Powershell
net start wuauserv
```

Now you can install RSAT Tools via PowerShell (must be run as an administrator):

```Powershell
Get-WindowsCapability -Name RSAT* -Online | Add-WindowsCapability
```

If you only need specific packages, follow these steps:

1. First, get a list of the packages that can be installed:
   ```Powershell
   Get-WindowsCapability -Name RSAT* -Online
   ```

2. Run this command and insert the package you need in _<tool name>_:
   ```Powershell
   Add-WindowsCapability -online -Name "<tool name>"
   ```