# Application operations on Proxmox

## Point

Proxmox is the **platform**. The value of this lab for an **application administrator / ICT operations** story is the **applications** that run on it — and how they are kept usable.

## What “managing an application” means here

For a typical app guest (e.g. Immich, Mealie, Vaultwarden, NetBox):

| Concern | What I do |
|---|---|
| Runtime | LXC/VM healthy, on-boot policy deliberate |
| Access | DNS name + reverse proxy route (Caddy); no random open ports |
| Health | Uptime / HTTP path checks where it matters |
| Data | Know where data lives (incl. bind mounts); backup criticality |
| Change | Prefer small changes; red-sensitive apps need explicit go |
| Failure | Triage: DNS vs proxy vs guest vs app process |

That is application beheer: **not only “container is running”**, but “the service path works and can be recovered”.

## Examples (roles, not secrets)

| Application | User-facing job | Ops sensitivity |
|---|---|---|
| Immich | Photos | High — personal data, mounts |
| Vaultwarden | Passwords | Critical — secrets |
| Mealie | Recipes / household | High — daily use |
| Obsidian LiveSync | Knowledge sync | Critical — work memory |
| NetBox | Inventory of workloads | Medium — operator tool |
| Uptime Kuma | “Is it up?” | High — eyes on the rest |
| Caddy + AdGuard | How apps are reached | Critical — access plane |

## Link to professional application administration

Same questions as on a job:

- Who uses this app?  
- What breaks if it dies?  
- How do we restore it?  
- How do we know it’s healthy?  
- What must not be changed lightly?  

Homelab = smaller blast radius, same discipline.

## Related docs

- [services.md](services.md) — catalog by priority  
- [operating-model.md](operating-model.md) — measure → change → write back  
- [backup-restore.md](backup-restore.md) — restore over hope  
- [../runbooks/health-check.md](../runbooks/health-check.md)  
