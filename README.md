# homeLab


## NAS (& Home Server

### Why NAS?

MOST IMPORTANT THINGS

WHAT IS PURPOSE? ROLES? ETC

NETWORK SECURITY

Centralization

Media Consumption

NAS VM connected to embedded HW (run weekly to monthly diagnostics on HW through automation)

Needs:

Home Server Tasks - Run Plex, Multiple users

NAS Tasks - Data Storage, Multiple users

Networking Education

Requirements:

Integrated GPU

4 bays initally with room to expand to 8

Motherboard Requiremets - 

PCie expandability - Use pcie expansion for GPUs, 10G NIC, etc.

NVme expandability (Min 2x Nvme, [one to run OS, VMs], etc, one to expand)

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

Setting SSL certs
https://www.youtube.com/watch?v=qlcVx-k-02E




### Future NAS?

Insert future goals here

<details>
<summary> 
  
  ### Resources 

</summary>

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
</details>

<details>
<summary>

  # Projects
</summary>

### Rpi5 NAS - The beginning

Although I am simulatenously building a larger NAS / Home Server - I still see value in working in more resource constrained environments. I think the rpi is the perfect introduction to this environment with respect to a home lab. I have used rpi's many times before and deployed simple python scripts on them and remoted in, but thats about it. I am not sure what this will turn out to be - but for now, my main goal would look something like a secondary storage. My first step on this path is spinning up the pi and putting pihole on it while I wait for the rest of my components to come in for the larger server. Once I get this up and running and get comfortable with the environment, I will see how and what this rpi can be repurposed to do. I envision it will have many lives and accomplish many tasks.

Specs:

- Raspberry Pi 5 4 GB
- Raspberry Pi SC1148 Active Cooler (Optional - it was cheap and i thought it would be fun to try one out)
- 2x ADATA ISSS31D 1TB SSD
- 2x ADP001 SATA to USB 3.0 Adapter

Notes: Install from network because I am too lazy to wipe one of my microSDs and i also want to keep those cards for my cameras for a trip coming up.



1. piHole Ad Blocker (with OS install over the network)

For my first basic project, I would like to install an rpi OS and get pihole up and running on my home network. Then some basic testing to see if it is working.

- Hooking up the components
  
  First, I removed the adhesive backing from the plastic cooler and installed it onto the pi. Then i plugged the fan connector into the 4 pin port labeled FAN (J12). Then I plugged in the sata to usb adapter and connected it to one of the ADATA drives.

- Apply Power and networking
  
  Now I connect power through USB-C to the pi and directly connect the pi to my network through a wired ethernet connection.

- Install pi OS over the network
  
Using the following guide https://www.tomshardware.com/reviews/raspberry-pi-headless-setup-how-to,6028.html I installed a pi OS over the network.

Install over network -> SSH (using Putty) -> Enable VPN -> VPN using Tiger VPN

***Some caveats here - you NEED to have the Rpi official 27W power suppy (5V @ 5A) or you will have trouble booting from USB (SSD.)





- 

  




2. NAS style 3D printed enclosure


### Main Home Server / NAS - The beginning

Setup -

Use Ventoy to create and organize ISOs

Installation Instructions:

How to Install Ventoy (new GUI version)

1. Go to the Ventoy download website:

https://sourceforge.net/projects/ventoy/files/

2. Click on the box to Download Latest Version

3. Right click on the file just downloaded and click on Extract Here.

4. A new Ventoy folder will be created. Move it to a permanent location.

5. Insert the USB stick.

6. In the terminal, type or paste the following:

cd ~/Downloads/ventoy-X.X.XX/

Replace the Xs with the correct version number.

7. Next, type or paste the following:

./VentoyGUI.x86_64

In the window that pops up, make sure the correct USB disk is selected, then click on Install or Update.

8. When updating, the disk can be safely removed when finished.

9. When doing a fresh install, mount the USB stick using Disks.

10. Open the new Ventoy USB stick and drag or copy/paste the desired ISO files into the window.

11. When done, Power Off the Ventoy Disk using Disks and wait until the wheel stops spinning before removing the drive. This may take quite a while.

You can always add more .iso files later by starting at step 9.


CONNECT SERVER TO ETHERNET BEFORE INSTALLING PROXMOX

Install Proxmox

Use web-gui to access

Use solar-putty or any other SSH tool to access proxmox console

ENABLE INTEL IOMMU - for PCI passthrough ([Link here](https://kb.protectli.com/kb/pci-passthrough-vt-d-proxmox-ve/))

Installed debian onto a VM


Proxmox -

Important Settings (https://www.youtube.com/watch?v=VAJWUZ3sTSI)

Configure Updates

VM best-practices


Next goals are getting portainer spun up and running

Getting network security figured out so we can remote in from wherever

monitoring services https://www.youtube.com/watch?v=vffhtqK3ZUg&t=92s&pp=ygURdW5yYWlkIG9uIHByb3htb3g%3D - may be able to help with resource usage, etc.


### Main Home Server / NAS - SECURITY

![image](https://github.com/user-attachments/assets/e5805f97-7307-4d30-8460-c30bf23b2480)


https://excalidraw.com/?#json=G46UxlBaGF_hoz6fRvYnx,y1iKoOjtQLrUYVqk89LGsQ
  
</details>


