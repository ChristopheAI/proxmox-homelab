# Backup and Restore

## Principle

Backups are only useful if restore steps are documented and tested.

## Baseline Process

- Identify critical data paths per service
- Define backup cadence by criticality
- Keep restore notes close to each workload

## Restore Drill Checklist

- Pick one representative service
- Restore to test target
- Validate service start + data integrity
- Record deviations and update runbook
