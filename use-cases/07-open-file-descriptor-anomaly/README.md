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
------------------------------------
1. Simulation

Book: ofd-simulation.yml

ansible-playbook -i inventory ofd-simulation.yml

After it completes, note the Simulator PID.

2. Investigation

Book: ofd-investigation.yml

ansible-playbook -i inventory ofd-investigation.yml

Look for the simulator PID in:

top_fd_processes

You should see something like:

5004 24581 ofd_simulator.sh

So here the PID is 24581.

3. Remediation

Book: ofd-remediation.yml

Pass the PID from the investigation:

ansible-playbook -i inventory ofd-remediation.yml -e "remediation_pid=24581"

Replace 24581 with whatever PID your investigation finds.
