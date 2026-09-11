# Safety and guardrails

- Diagnosis is read-only by default.
- Never execute raw LLM-generated shell commands directly.
- Allow only reviewed playbooks and constrained parameters.
- Keep credentials in a secret manager or Ansible Vault, never in prompts or Git.
- Redact tokens, passwords, cookies, private keys, and sensitive headers before LLM calls.
- Use least-privilege service accounts and short-lived credentials where supported.
- Require approval for restarts, configuration changes, package operations, scaling, deletion, and rollback.
- Enforce target allowlists, check mode, timeouts, concurrency limits, and audit logging.
- Stop execution when validation or rollback prerequisites are missing.
