# plexamp-headless

![](files/plexamp-header.png)

This Ansible playbook will install [Plexamp](https://www.plex.tv/plexamp/), the standalone music player for [Plex](https://www.plex.tv/), specifically the [headless](https://www.plex.tv/plexamp/#downloads) variety, so it can be controlled via a Plexamp running on your phone, computer or tablet. While the download page advertises the headless variant runs on a [Raspberry Pi](https://www.raspberrypi.com/), this project aims to automate the installation on a Raspberry Pi, or any generic Linux hosts. Having an enpoint to stream from Plex that can directly connect to a stereo component is the goal. Longer term I would like to see how close this could come to being a [Roon](https://roon.app/) replacement, which is not open source. Note, Plex is not open source, but free to use, and after years of being a paid for only option, Plexamp is now free as well. So while none of this is free as Open Source, it's the best music streaming option I've found to do what (I think) I want it to do.

## Requirements

* A Linux host to install Plexamp Headless on - this code has been developed on [Debian](https://www.debian.org/), which is the basis for the official [Raspberry Pi OS](https://www.raspberrypi.com/software/), in fact they used to call it [Rasbian](https://www.raspbian.org/), but once that is complete I would like to get it working on [Fedora](https://fedoraproject.org/) so we can see it running on [Silverblue](https://fedoraproject.org/silverblue/)), which is what I'm moving my Plex to next
* A running Plex server 

## Setup

* Install [Ansible](https://www.ansible.com/) and git - in Debian (Raspberry Pi OS, Ubuntu, Mint, etc...)

```
(sudo) apt install ansible git
```

* Checkout this Ansible code

```
git clone https://github.com/philcryer/plexamp-headless.git
```

## Install 

```
cd plexamp-headless
```

## Post-config

* Next we need the the claim code from your running Plex server. To do this, hit [https://www.plex.tv/claim/](https://www.plex.tv/claim/) and copy the code it displays

![](files/plex-claim.png)

## Running

* In a broswer you should be able to hit it directly, if it's running on the same host you could hit it at [localhost:32500/](localhost:32500/), otherwise target the IP that Plexamp Headless is running on, and add that port. Example: [129.168.1.50:32500](192.168.1.50]

![](files/plexamp-leeway.png)

* On a deskop, phone, or tablet running Plexamp, you should be able to see it under 'Players', click on the 'Cast' looking icon on the top right, and it'll give you a list of poential players. Click on the one you're running and you should now have remote control over that instance

![](files/plexamp-players.png)


## Acknowledgements

* [zonywhoop/ansible-role-plexamp-headless](https://github.com/zonywhoop/ansible-role-plexamp-headless/tree/main) - this helped me get started, it has the basis for much of what I've done, but I've rewritten/moderized it and added some useful items

## License

Thanks
