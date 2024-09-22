---
author: clausmalver
title: Notes for Offensive Security
description: Page for quick glance notes for offensive security.
date: 2024-09-21
categories: [Notes, hacking]
tags: [webexploitation, powershell]
---
## Clone a website

Clone a website including images, css, etc.
`wget -mk -nH [URL]`

## Bypass Powershell Execution Policy
`Set-Executionpolicy -Scope CurrentUser -ExecutionPolicy UnRestricted`

## Reverse shells
[Reverse Shell Generator](https://www.revshells.com/)

## Alfa Networks

Get USB wifi adapter into monitor mode

```
sudo ifconfig wlan0 down
sudo iwconfig wlan0 mode monitor
sudo ifconfig wlan up
```
Check if adapter is in monitor mode:

`iwconfig wlan0`

### Monitor using Kismet

`kismet -c wlan0 -p ~/log_directory -t output_file`

### Deauth attacks

https://github.com/flashnuke/wifi-deauth

Install and run on system
```
git clone https://github.com/flashnuke/wifi-deauth.git
sudo pip3 install .
sudo wifi-deauth -i <iface>
```

Remember to let it run for a bit so the app can collect clients it can deauth

