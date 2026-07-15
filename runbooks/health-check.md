# Runbook: health check

## When

- Start of an ops session  
- After power events or network changes  
- Before/after guest upgrades  

## Steps (read-only first)

1. Node reachable (SSH/API)  
2. Proxmox reports expected guests running  
3. DNS resolves a known local name (AdGuard)  
4. Proxy path returns expected status for 1–2 critical apps  
5. PBS / backup job last success (if checkable)  
6. Note anomalies; don’t restart blindly  

## Stop conditions

- Cannot reach hypervisor → network/Tailscale path first  
- DNS broken → fix DNS before app restarts  
- Proxy misroute → fix Caddy host rules before blaming the app  
