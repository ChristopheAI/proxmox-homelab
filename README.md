# Proxmox Homelab

Personal **Proxmox VE** homelab — documented as an operations practice, not a screenshot dump.

I run a single-node hypervisor at home with LXC-first workloads, reverse proxy, DNS, backups to **Proxmox Backup Server**, and runbooks that agents and I can follow. The private control plane lives elsewhere; this repo is the **public-safe** view for portfolio and hiring.

**Portfolio:** [vastpakt.be](https://vastpakt.be) · **Operator:** [ChristopheAI](https://github.com/ChristopheAI)

## Hardware (approx.)

| Piece | Role |
|---|---|
| Intel NUC (i7-10710U, 16 GB RAM, NVMe) | Proxmox VE host |
| Separate mini-PC | Proxmox Backup Server (PBS) |
| External HDD | Extra bulk storage / mounts for media & shares |

Exact firmware/IPs stay private.

## What runs here (by role)

| Role | Examples |
|---|---|
| **Access & edge** | Caddy reverse proxy, AdGuard Home (DNS), Tailscale |
| **Reliability** | Uptime Kuma, LibreNMS, pulse/monitoring CT |
| **Personal data** | Immich (photos), Samba shares, Vaultwarden |
| **Knowledge / ops** | Obsidian LiveSync (CouchDB), NetBox (scoped inventory), Mealie |
| **Network** | UniFi controller, LAN discovery |
| **Lab / dev** | ML/dev VM, automation sandbox, Windows lab VM (often stopped) |

Guest names and roles are documented without LAN addresses. See [`docs/services.md`](docs/services.md) and [`docs/workload-inventory.md`](docs/workload-inventory.md).

## Operating model

This lab is operated like a small production environment:

1. **Measure before changing** — inventory and health from the host, not memory  
2. **Runbooks over folklore** — health checks, backup/restore, incident triage  
3. **Agent-assisted ops** — I use coding/ops agents with a private control plane (runbooks + rules); they read docs and propose checks, they don’t get free rein on red-sensitive services  
4. **Public-safe by default** — no credentials, no internal IPs, no raw secret-bearing config in this repo  

Details: [`docs/operating-model.md`](docs/operating-model.md)

## Docs

| Doc | Content |
|---|---|
| [`docs/architecture.md`](docs/architecture.md) | Topology and design choices |
| [`docs/services.md`](docs/services.md) | Service catalog by role and priority |
| [`docs/workload-inventory.md`](docs/workload-inventory.md) | Guest map (IDs/names, no IPs) |
| [`docs/networking.md`](docs/networking.md) | DNS, proxy, remote access principles |
| [`docs/monitoring.md`](docs/monitoring.md) | Observability and alerting intent |
| [`docs/backup-restore.md`](docs/backup-restore.md) | PBS, criticality, restore drills |
| [`docs/discovery-method.md`](docs/discovery-method.md) | How inventory is produced |
| [`runbooks/`](runbooks/) | Health check, incident triage, monthly maintenance |

## Stack keywords

`Proxmox VE` · `LXC` · `QEMU` · `PBS` · `Caddy` · `AdGuard` · `Tailscale` · `Immich` · `NetBox` · `Uptime Kuma` · `Linux` · `runbooks`

## Status

Active. Public docs last refreshed **2026-07-15** from the live private control plane (sanitized). Inventory drifts; treat private host checks as source of truth for “what’s running right now”.

## License

MIT — see [LICENSE](LICENSE).
