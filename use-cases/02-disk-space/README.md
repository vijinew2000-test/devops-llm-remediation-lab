# Disk Space

## Purpose

Detect filesystems with low free capacity and identify the largest safe investigation targets.

## Workflow

1. Run `investigation.yml` in read-only mode.
2. Review evidence and select a known remediation.
3. Set `allow_remediation=true` only after approval.
4. Run post-change health checks and record the result.

Simulation is disabled by default and must only target an isolated lab machine.
