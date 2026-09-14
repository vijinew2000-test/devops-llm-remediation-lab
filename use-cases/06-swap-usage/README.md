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

## What symptoms indicate problematic swap usage?
Resource symptoms

High swap utilization
Increasing swap usage
Low available RAM
High memory utilization
High swap-in/swap-out activity
Application symptoms

Applications may become:

slow
intermittently unresponsive
slow to start
slow to respond to requests
System symptoms

You may see:

High disk I/O
High iowait
System sluggishness
Processes spending more time waiting

In severe cases:

OOM events
Services getting killed
Application failures
