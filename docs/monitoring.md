# Monitoring

## Layers

| Layer | Tooling (examples) | Question it answers |
|---|---|---|
| Endpoint up | Uptime Kuma | Is the URL/port up? |
| Network / device | LibreNMS | What changed on the network? |
| Host / guest pulse | pulse monitoring CT | Is the infra plane noisy? |
| Human path | Browser / curl host checks via proxy | Does the user path work? |

## Alert principles

- Prefer **actionable** alerts over chatty ones  
- After major changes, re-check the monitoring path itself  
- Failed units on LXC (AppArmor/sysusers noise) are tracked as known follow-ups when non-blocking  

## Portfolio signal

This is not a NOC. It is evidence of **reliability habits**: visibility before restart, and health surfaces per service type.
