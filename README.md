# homeLab


## NAS (& Home Server

### Why NAS?

Centralization

Media Consumption

Needs:

Home Server Tasks - Run Plex, Multiple users

NAS Tasks - Data Storage, Multiple users

Networking Education

Requirements:

Integrated GPU

4 - 8 Bays

PCie expandability

NVme expandability

NVMe vs SATA


NIC (10Gb desired)


### What Roles?

hypervisor (with a virtualized NAS)
https://www.youtube.com/watch?v=hJHpVi9LGqc



### How NAS?

First things first, chassis. Rolled the dice and got a sweet deal off of Mercari:

Fractal Node 804 ($50)

SATA expansion
https://www.amazon.com/LSI-Broadcom-9300-8i-PCI-Express-Profile/dp/B00DSURZYS

Enterprise HDDs
https://serverpartdeals.com/collections/manufacturer-recertified-drives/products/seagate-ironwolf-pro-st4000ne001-4tb-7-2k-rpm-sata-6gb-s-512e-nas-3-5-recertified-hard-drive

tailscle (secure remote access)


### Setup

Passing a physical drive through to a VM in ProxMox
https://www.youtube.com/watch?v=U-UTMuhmC1U

3(?) Plex Servers - One for internal, One for external Users, one for testing
https://www.reddit.com/r/PleX/comments/18q5v5y/pros_cons_for_jellyfin_vs_plex/

Setup beginning to end (Proxmox, two vms (truenas (in my case unraid), and debian), portainer, wireguard (to connect remotely securely), jellyfin server Part 1
https://www.youtube.com/watch?v=_sfddZHhOj4

part 2
https://www.youtube.com/watch?v=BoMlfk397h0



### Future NAS?




### Resources:

linux distros
https://www.youtube.com/watch?v=E6Jyj6whge4&t=0s

proxmox vms and automating them
https://www.youtube.com/watch?v=1nf3WOEFq1Y&t=0s
https://www.youtube.com/watch?v=dvyeoDBUtsU&t=0s

https://www.youtube.com/@CraftComputing
Whole network ad-blocking, setting up plex, vpn gateway

technotim
https://www.youtube.com/watch?v=1lXSdg-8evA


jeffgeerling

selfhost the interent
https://www.youtube.com/watch?v=OC67FoXVRPE

starting journey
https://www.youtube.com/watch?v=3-Nm15utD3g

turing pi 2 for ML, clustering, etc
https://turingpi.com/product/turing-pi-2-5/

Best homeserver operating systems
https://www.youtube.com/watch?v=xWz_-gyv3j4



