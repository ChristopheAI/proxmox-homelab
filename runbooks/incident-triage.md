# Runbook: incident triage

## Classify

| Symptom | Likely layer |
|---|---|
| Nothing resolves by name | DNS |
| Name works, HTTPS fails | Proxy / cert / upstream |
| One app only | Guest / container / app process |
| Many guests down | Host, storage, or power |
| Off-LAN only | Tailscale / remote path |

## Actions

1. **Observe** — status, logs, last change  
2. **Contain** — don’t reboot the host as first move  
3. **Fix the highest layer that explains the blast radius**  
4. **Verify** user path (browser or curl)  
5. **Write** one line: cause + prevention  

## Red-sensitive

Stop/start/delete of secrets, photos, DNS, proxy, PBS — only with clear intent.
