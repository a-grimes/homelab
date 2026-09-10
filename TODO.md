# homelab to-dos

## general

## rpi-alpha
### Network UPS Tools (NUT) server
- NUT data server

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