+++
title = 'Self-hosting'
date = 2025-07-18T08:09:16Z
draft = false
tags = ['self-hosting']
+++
# Self-hosting

I finally gave in and bought one of those MiniPC's you can find from Aliexpress and like for cheap. I have been avoiding these quite long though because I read somewhere that cheap MiniPCs never get firmware/BIOS upgrades or even have spyware which is calling back home. Anyway I really wanted something to tinker with and do my self-hosting on but I had space constraints. My apartment is quite compact so running something proper like server rack or even PC case is out of question. 

There is plenty of these MiniPCs sold second hand and I ended up with something branded as "Firebat AK2" for 120€.. It has couple years old Intel N100 CPU, 16Gb RAM and 512 NVMe, sounded like enough for some self-hosting. Surprisingly system came with Linux Mint installed, apparently previous owner had used it
to watch and record TV shows and such. I tried to ask why he did not need it anymore but did not get very clear answer. When I got home though I found out that Wifi connectivity was pretty spotty and of course this system comes with integrated Realtek RTL8221CL chip which Linux drivers have always sucked.. Probably this was one reason it was sold. Luckily I have option to use ethernet cable so I could just forget about wireless. However I could have placed this thing nearby my TV so I could have used it with Kodi. 

## Things to host

Before acquiring mini home server I had been running some stuff on my personal laptop Thinkpad X270. I bought this one second hand as well to replace my trusty X220 (from 2011!) but I was quite disappointed (maybe another post about that coming). 
Thinkpad was running some media streaming and collection stuff like:

- [Jellyfin](https://jellyfin.org) - media streaming service similiar to Plex 
- [\*Arr stack](https://wiki.servarr.com) - Radarr, Sonarr and such used to find and collect stuff
- [Jellyseerr]https://docs.jellyseerr.dev) - nice interface for finding new movies and series
- Qbittorrent and SABnbzd for downloading Linux ISO's

My X270 is running Gentoo, and I have been running these services on [rootless Podman](https://github.com/containers/podman/blob/main/docs/tutorials/rootless_tutorial.md). This setup has been working nicely as long as I dont forget to keep my laptop on. 

Additionally I have some compute instances running on Oracle Cloud free tier. On these I have been hosting   
- [Teslamate](https://docs.teslamate.org/docs/installation/docker) - Graphana dashboards and service to pick up stats from Tesla API. Running on Docker
- [Wireguard](https://www.wireguard.com) - Greatest invention since sliced bread 
- [PiHole](https://pi-hole.net) - DNS server with nice WebUI and ad blocking 
- [Syncthing](https://syncthing.net) - Like Dropbox but without SaaS service in between and free!
- [Nextcloud](https://nextcloud.com) - Also like Dropbox with some Office suite and collab features and more

Oracle cloud in general has been bit hit and miss and I would like to rant about it in another post. However its free so how much I'm allowed to complain about it :-\)

### Things I would like to host ( at least )

- [Bitwarden](bitwarden.com) password manager, currently I'm on their SaaS offering
- ZFS snapshot backup host  
- Google Photo / iCloud alternative like [Immich](https://immich.app)

## Plan

My intention is to move most of my existing services to my new MiniPC. I dediced that this will happen with [FreeBSD](https://www.freebsd.org) and more about this decision later. 


