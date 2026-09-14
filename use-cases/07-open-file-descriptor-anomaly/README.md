# Open File Descriptor Anomaly

## Purpose

Detect abnormal growth or exhaustion of file descriptors at the host, service, and process levels. Common causes include unclosed files, sockets, pipes, application leaks, traffic spikes, and limits that are too low for a valid workload.

## Workflow

1. Run `investigation.yml` to collect read-only evidence.
2. Compare allocated descriptors with the kernel maximum.
3. Identify processes with unusually high descriptor counts.
4. Inspect the affected process limit and descriptor types.
5. Select an application-specific, reviewed remediation.
6. Set `allow_remediation=true` only after human approval.
7. Re-run the investigation and confirm descriptor usage is stable.

Simulation is disabled by default and must run only on an isolated lab host.

## Important note

Increasing a limit may hide an application leak. Check whether descriptor counts continue growing before changing limits or restarting a service.
