# Swap Usage

## Purpose

Detect swap consumption, identify processes using swap, and determine whether the cause is current memory pressure or inactive pages retained in swap.

## Workflow

1. Run `investigation.yml` to collect read-only memory and swap evidence.
2. Review total RAM, available RAM, swap usage, `vmstat`, and per-process swap.
3. Identify the responsible application or workload.
4. Select a reviewed remediation and rollback plan.
5. Set `allow_remediation=true` only after human approval.
6. Re-run the investigation and verify that the host remains healthy.

Simulation is disabled by default and must run only on an isolated lab host.

## Important note

Swap being used does not automatically mean the server has a current problem. Check available memory, swap-in/swap-out activity, application health, and historical trends before remediation.
