---
title: IRO has issues
date: 2023-11-13T07:07:07+01:00
categories: ["Games", "MMO", "Fix", "Ragnarok Online"]
series: "Games"
---
## iRO

for those that don't know Ragnarok Online a old game that started in earlys 2000's.
It was one of my favorite games including Eve-Online ,Diablo 2, Starcraft and some others (im only including those with 10k+ hours of gameplay)

#### Why Now?

I honnestly never played renewal and decided to try official server now that they fixed the bot issues. ( Ever since they added EAC and remade part of the clien OpenmKore doesn't work anymore on their servers )
It still won't fix the paytowin aspect of the official client but i told myself why not?

#### How wrong i was....

Playing private servers most of them is download a zip file, extract and Launch. So when you play official servers you expect even less of an hassle right? Well i was wrong.

Two issues one after another.

* Cannot connect to patch server
* Client Mismatch Ragexexe.exe

# iRO issues

## 1. Patch server issue

### 1.1 Pihole issues only
First part i had to ensure my pihole wasn't blocking the server ( it wasn't but shown lots of DNSSEC issues and errors from certificates )
In pihole admin panel at said url */admin/dns_records.php Local DNS Records
patch.1.online.ragnarok.warpportal.net,patch1.playragnarok.com 128.241.93.38
and just to make sure */admin/groups-domains.php Domain management added 
patch1.playragnarok.com patch.1.online.ragnarok.warpportal.net to Regex whitelist

Turn out it was showing errors still due to DNSSEC validation. Basically patch1.playragnarok.com forward you to patch.1.online.ragnarok.warpportal.net and then fail some certificates and check and pihole seem to hate this...

### 1.2 Windows Hosts edit
Some computer without using pihole had issues for patch-server as well so lets go very basic then....
edit C:\Windows\System32\drivers\etc\hosts in admin mode (Path letter may differ) 

[20231113_015231_hosts.txt](/assets/files/20231113_015231_hosts.txt) remove the .txt extension or edit hosts and copy paste

```bash
# Copyright (c) 1993-2009 Microsoft Corp.
#
# This is a sample HOSTS file used by Microsoft TCP/IP for Windows.
#
# This file contains the mappings of IP addresses to host names. Each
# entry should be kept on an individual line. The IP address should
# be placed in the first column followed by the corresponding host name.
# The IP address and the host name should be separated by at least one
# space.
#
# Additionally, comments (such as these) may be inserted on individual
# lines or following the machine name denoted by a '#' symbol.
#
# For example:
#
#      102.54.94.97     rhino.acme.com          # source server
#       38.25.63.10     x.acme.com              # x client host

# localhost name resolution is handled within DNS itself.
#	127.0.0.1       localhost
#	::1             localhost
128.241.93.57	warpportal.com
128.241.93.57	www.warpportal.com
128.241.93.17	support.warpportal.com
128.241.93.3	forums.warpportal.com
128.241.93.38	patch1.playragnarok.com
```
Did it fix? Patch server is fixed but now another issue arise!

## 2. Ragexe.exe Unknown Version
### 2.1 Reload patcher at specific patch
Solution was found on warpportal forums.
Browse to install files. Delete Ragexe.exe then visit this website [Choobs Patcher fixer](https://choobs.org/stuff/patch.php) set server to chaos ( renewal ) patch number to 4763 click download and proceed to overwrite same file inside ragnarok folder with the fresh download patch.inf
Restart Ragnarok.exe let it download now Ragexe.exe should be 10,119KB
If you are getting sprite errors redo those steps but at patch version input 4742
### 2.2 Complete Fix downloading whole client archive
If more issues arise best solution is to download full.zip client from here [iRO wiki Full Client ZIP](https://irowiki.org/wiki/Clients_and_Patches)
Extract and run as long as ur able to connect to game server.

#### Ragnarok nowadays...
To be fair its a very old game and gravity seem to have shifted to gacha model years ago. They mostly focus on Smartphone content as well so it's fair to think that the official servers are on their last legs. The game will live on mostly due to hardcore fans and server emulators such as herculez and rathena.