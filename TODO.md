# homelab to-dos

## general
- UPS integration / LXC / docker container

## `grimescloud.com`
### subdomains?
- `media.grimescloud.com`
  - `movies.grimescloud.com`
  - `shows.grimescloud.com`
  - `seer.grimescloud.com`
- `photos.grimescloud.com`

## reverse proxy
1. automate dyanmic IP updates
  - DDNS client via docker container
    - cloudfalre: `oznu/cloudflare-ddns`?
2. configure reverse proxy (`nginx`?)
  - `nginx` via docker container
  - configure `nginx` to catch incoming subdomaains and route to services
    - config file: `/etc/nginx/sites-available/homelab.conf`
3. automate SSL certs
  - install `certbot` and `nginx` plugin