# Workload inventory (public-safe)

Snapshot style: guest **ID + name + type + role**.  
No LAN IPs. Status drifts; private control plane is authoritative.

Last public refresh: **2026-07-15** (from private inventory last verified mid‑2026).

## Typical LXC guests

| ID | Name | Role |
|---|---|---|
| 100 | pulse-monitoring | Monitoring |
| 101 | librenms | Network monitoring |
| 110 | uptime-kuma | Uptime checks |
| 111 | adguard-home | DNS |
| 1001 | immich-photos | Photos (bind mounts) |
| 2001 | unifi-controller | UniFi |
| 2003 | watchyourlan | LAN discovery |
| 2004 | samba-server | File shares (bind mounts) |
| 2005 | caddy-proxy | Reverse proxy |
| 2011 | rustdesk-server | Remote desktop relay |
| 2014 | Tailscale | Tailnet |
| 2016 | netbox | Workload inventory app |
| 2017 | vikunja | Tasks |
| 2020 | vaultwarden | Password vault |
| 2021 | cua | Automation / sandbox |
| 2025 | personal-site | Static / personal site CT |
| 2026 | umami-analytics | Analytics |
| 2028 | obsidian-livesync | CouchDB LiveSync |
| 2029 | mealie | Recipes |

## Typical VMs

| ID | Name | Role |
|---|---|---|
| 102 | home-assistant | Home automation hub |
| 2012 | ml-dev | Dev / ML experiments |
| 2013 | windows-lab | Windows lab (often stopped) |

## Lifecycle note

Guests get added, cleaned, and remove-drilled over time (e.g. old scrapers and one-off bots removed after backup confirmation). The catalog above is the **stable portfolio view**, not a forever freeze of every historical CT.
