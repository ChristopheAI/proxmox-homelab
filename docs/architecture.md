# Architecture

## High-level topology

```text
Internet
   │
Gateway / router
   │
LAN (private)
   │
Proxmox VE (single node)
   ├── LXC containers  (most services)
   ├── QEMU VMs        (dev / lab / HA where needed)
   └── storage: local + LVM-thin + PBS remote
          │
   Proxmox Backup Server (separate machine)
```

## Design choices

| Choice | Why |
|---|---|
| **LXC-first** | Lower overhead, clear service boundaries, fast rebuilds |
| **Single node** | Home scale; recoverability > HA cluster complexity |
| **Separate PBS** | Backups off the hypervisor disk when possible |
| **Reverse proxy (Caddy)** | One ingress pattern; TLS and host routing in one place |
| **DNS (AdGuard)** | Local names + filtering; changes treated as sensitive |
| **Tailscale** | Off-LAN admin path without exposing the whole lab |

## Principles

- Isolate by service (one guest ≈ one job)  
- Prefer documented restore over “it still boots”  
- Bind mounts and personal data guests are **higher risk** (backup + change control)  
- Lab/dev guests may stay stopped; not every CT must be green  

## Not in this public repo

- LAN IPs, credentials, TLS private keys  
- Full proxy/DNS zone dumps  
- Automation that can destroy guests without human go  
