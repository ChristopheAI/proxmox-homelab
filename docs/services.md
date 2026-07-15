# Service catalog (public-safe)

Roles and priority as I operate them. No hostnames/IPs.

## Critical

| Service | Role | Why critical |
|---|---|---|
| AdGuard Home | DNS | Breaks name resolution for the house |
| Caddy | Reverse proxy | Breaks HTTPS routes to apps |
| Tailscale | Remote access | Breaks off-LAN admin path |
| Immich | Photos | Personal data + bind mounts |
| Vaultwarden | Passwords | Secrets-bearing |
| Samba | File shares | Data path + mounts |
| UniFi controller | Network | Wi‑Fi / LAN control plane |
| Obsidian LiveSync | Knowledge sync | Daily work memory |

## High

| Service | Role |
|---|---|
| Uptime Kuma | Endpoint uptime checks |
| LibreNMS / pulse monitoring | Infra visibility |
| Mealie | Recipes / household app |
| Automation sandbox | Agent/desktop automation lab |

## Medium / lab

| Service | Role |
|---|---|
| NetBox | Scoped inventory of workloads (not full enterprise CMDB) |
| Vikunja | Tasks |
| Umami | Analytics |
| RustDesk | Remote desktop relay |
| WatchYourLAN | LAN discovery |
| ML/dev VM | Experimentation |
| Windows lab VM | Occasional; often stopped |

## Operator rules

- **Red-sensitive:** DNS, proxy, Tailscale, backups, bind mounts, secrets guests — change only with explicit intent  
- **Expected stopped:** lab/archive guests are allowed to stay down  
- Live state always comes from Proxmox checks, not this markdown alone  
