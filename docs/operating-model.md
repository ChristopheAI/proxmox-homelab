# Operating model

## Goal

Keep the lab **restorable and understandable**, not maximally complex.

## Loop

1. **Orient** — what is the node, what is running, what failed?  
2. **Classify** — app vs guest vs host vs network vs backup  
3. **Check** — service health surfaces before restarts  
4. **Change small** — one lane at a time; red-sensitive needs explicit go  
5. **Write back** — if it will happen again, it goes in a runbook  

## Agent-assisted ops

I operate this lab with coding/ops agents under rules:

- Read-only checks first  
- No blind destroy/stop of critical guests  
- Markdown control plane (private) holds inventory, catalog, and handover  
- Public repo only gets **sanitized** docs  

This matches how I build software: agents do the mechanical work; I keep direction and production judgment.

## Runbooks in this repo

- [`../runbooks/health-check.md`](../runbooks/health-check.md)  
- [`../runbooks/incident-triage.md`](../runbooks/incident-triage.md)  
- [`../runbooks/monthly-maintenance.md`](../runbooks/monthly-maintenance.md)  
