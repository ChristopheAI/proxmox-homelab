# Architecture

## High-Level Topology

- Hypervisor: Proxmox VE
- Workloads: LXC-focused service layout
- Goal: isolate services, simplify maintenance, keep recovery paths clear

## Design Principles

- Keep services loosely coupled
- Prefer simple operational boundaries
- Document assumptions and dependencies
- Optimize for restoreability, not just uptime

## Next Updates

- Add host and container inventory table
- Add dependency map between core services
- Add monthly architecture review notes
