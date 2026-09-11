# Architecture

## Planned components

1. Evidence collector gathers read-only health data.
2. Normalizer removes sensitive fields and produces structured context.
3. LLM proposes diagnosis, remediation, validation, and rollback steps.
4. Policy layer rejects unsafe or out-of-scope actions.
5. Human approver reviews state-changing plans.
6. Ansible runner executes an approved playbook with limited credentials.
7. Audit logger records decisions and results without secret values.
