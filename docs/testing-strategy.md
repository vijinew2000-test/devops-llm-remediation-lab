# Testing strategy

1. Unit-test parsers, redaction, policy rules, and structured LLM output.
2. Run Ansible syntax checks and linting.
3. Use check mode where modules support it.
4. Test remediations against disposable lab hosts.
5. Inject known failures and verify diagnosis, approval, remediation, health checks, and rollback.
6. Confirm that secrets never appear in prompts, logs, artifacts, or Git history.
