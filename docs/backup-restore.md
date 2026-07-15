# Backup and restore

## Principle

A backup that has never been restored is a hypothesis.

## Pattern

- **Proxmox Backup Server (PBS)** on a separate machine  
- Guest backups by criticality (personal data and secrets first)  
- Bind-mounted data paths (photos, shares) need explicit data ownership notes  
- Occasional **restore drills** on disposable guests  

## Restore drill (template)

1. Pick one representative guest or dataset  
2. Restore to a test target (not production data path)  
3. Validate start + data integrity  
4. Record what broke in the notes and fix the runbook  

## Public-safe note

Schedules, retention, and storage credentials stay private.
