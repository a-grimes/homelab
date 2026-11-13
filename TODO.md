# homelab to-dos

## general
### new linux VM start up
- qemu-guest-agent: install and/or enable + start
- openssh-server install (and start)
- curl
- wget
- ca-certificates
- git
- vim
- htop
- nfs-common

### backups

## rpi-alpha
### Network UPS Tools (NUT) server
- NUT data server

### pi-hole, adblock, unbound
- add unbound as the DNS resolver under pi-hole
- combine pi-hole with adblock?

## rpi-beta

## nas
- NUT client
- enable NFS share for access to *media*, *photos*

## pve
- NUT client (on proxmox host?)
  - feed data to every LXC and VM (standard code?)
- backup `pve` important folders to local SSD
  
  - Configuration	Location
  - Proxmox configuration, VM definitions, storage	/etc/pve
  - Network interfaces and VLAN configuration	/etc/network/interfaces
  - Storage mount configuration	/etc/fstab
  - Hostname and DNS configuration	/etc/hostname, /etc/hosts, /etc/resolv.conf
  - Systemd services, including NIC workarounds	/etc/systemd/system
- backup SSD backups to `nas` - automated from `pve`?

### (service) VPN
- gluetun or wireguard as standalone service
- direct other services that need discretion (LXCs/VMs) through this service
- [proxmox vm networking](https://industrialmonitordirect.com/blogs/knowledgebase/proxmox-vm-networking-gluetun-tailscale-traefik-architecture)
  - standalone `gluetun`

### (service) immich

### (service) "management"
- `homarr` or similar
- `portainer`? access all containers across LXCs/VMs?

### (service) reverse proxy
1. automate dyanmic IP updates
  - DDNS client via docker container
    - cloudflare: `oznu/cloudflare-ddns`?
2. configure reverse proxy (`nginx`?)
  - `nginx` via docker container
  - configure `nginx` to catch incoming subdomaains and route to services
    - config file: `/etc/nginx/sites-available/homelab.conf`
3. automate SSL certs
  - install `certbot` and `nginx` plugin

### (service) home assistant?