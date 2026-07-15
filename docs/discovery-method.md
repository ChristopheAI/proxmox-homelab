# Discovery method

Inventory and health are generated from **live Proxmox state** (SSH/API/scripts), not from memory.

Private control plane tools produce:

- guest list (type, name, running/stopped)  
- storage usage snapshots  
- service catalog / situation layer for operators  

This public repo receives a **sanitized extract**:

- no IPs  
- no credentials  
- no secret-bearing descriptions from the hypervisor  

When private and public disagree, **private live checks win**.
