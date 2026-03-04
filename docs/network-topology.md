# Network Topology (Public-Safe)

Last updated: 2026-03-04 19:20 UTC (live discovery from Proxmox host)

## Purpose
This document shows the real homelab architecture as portfolio evidence, while avoiding sensitive exposure in a public repository.

## High-Level Layout

```text
Internet
  |
Gateway / Router
  |
LAN (private range)
  |
Proxmox VE Host (single node, vmbr0 bridge)
  |
+-- LXC workloads
+-- QEMU VMs
+-- Self-hosted services (monitoring, automation, proxy, collaboration, security)
```

## Live Capacity Snapshot
- Proxmox node: 1
- LXC containers: 25 total (18 running)
- VMs: 2 total (1 running)
- Main bridge: `vmbr0`

## Service Domains (from active workloads)
- Monitoring/observability: Pulse, LibreNMS, Uptime Kuma, WatchYourLAN
- Networking/security: AdGuard Home, Tailscale, Vaultwarden, Caddy
- Productivity/collab: Vikunja, n8n, RustDesk
- Media/personal services: Immich, Samba
- Dev/experimentation: ml-dev VM, scanner/scraper/proxy tracks
