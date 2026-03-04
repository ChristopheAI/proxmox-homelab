# Network Topology (Public-Safe)

Last updated: 2026-03-04 19:17 UTC (live discovery from Proxmox host)

## Purpose
This document shows the real homelab architecture as portfolio evidence, while avoiding sensitive exposure in a public repository.

## High-Level Layout



## Live Capacity Snapshot
- Proxmox node: 1
- LXC containers: 25 total ( running)
- VMs: 2 total ( running)
- Main bridge: 

## Service Domains (from active workloads)
- Monitoring/observability: Pulse, LibreNMS, Uptime Kuma, WatchYourLAN
- Networking/security: AdGuard Home, Tailscale, Vaultwarden, Caddy
- Productivity/collab: Vikunja, n8n, RustDesk
- Media/personal services: Immich, Samba
- Dev/experimentation: ml-dev VM, scanner/scraper/proxy tracks
