# Networking (public-safe)

## Pattern

- Home LAN behind a normal consumer/prosumer gateway  
- Proxmox bridge for guests  
- **AdGuard Home** as DNS for local names + filtering  
- **Caddy** as reverse proxy for HTTPS host routing  
- **Tailscale** for admin access off-LAN  

## Practices

- Prefer one reverse-proxy entry pattern over many open ports  
- Treat DNS and proxy edits as **sensitive** (easy to lock yourself out)  
- Document *intent* (who terminates TLS, who owns DNS) without publishing zone files  
- Avoid putting management UIs on the open internet  

## Not published here

CIDRs, static IP tables, full Caddyfiles, API tokens, Tailscale auth keys.
