# homelab to-dos

## general

## rpi-alpha
### Network UPS Tools (NUT) server
- NUT data server

### pi-hole, adblock, unbound
- add unbound as the DNS resolver under pi-hole
- combine pi-hole with adblock?

## rpi-beta

## nas
- NUT client
- enable NFS share for access to data

## pve
- NUT client (on proxmox host?)
  - feed data to every LXC and VM (standard code?)
- add second SSD
  - wipe disk, *LVM-Thin*?, etc.
  - use as storage pool for new LXCs/VMs

### (service) VPN
- gluetun or wireguard as standalone service
- direct other services that need discretion (LXCs/VMs) through this service
- [proxmox vm networking](https://industrialmonitordirect.com/blogs/knowledgebase/proxmox-vm-networking-gluetun-tailscale-traefik-architecture)
  - standalone `gluetun`

### (service) *arr stack
#### OS: Debian?
|CPUs|RAM|Storage (SDD)|
|---|---|---|
|?|?GB|?GB|
- migrate from nas docker to pve docker inside VM
- setup docker compose with current (working) versions
- copy config files?
- reduce quality (1.5-2GB per 1080p hour?)

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