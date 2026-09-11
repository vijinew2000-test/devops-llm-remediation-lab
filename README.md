# DevOps LLM Remediation Lab

A safe, test-driven lab for detecting infrastructure problems, generating remediation plans with an LLM, and executing approved automation.

## Goals

- Collect and normalize operational evidence.
- Ask an LLM for an explanation and proposed remediation.
- Validate proposed actions against explicit safety guardrails.
- Require approval before potentially disruptive changes.
- Execute repeatable remediation through Ansible.
- Record the request, decision, execution result, and rollback evidence.

## Repository layout

- `llm/` — prompts, schemas, examples, and evaluation cases.
- `ansible/` — inventories, reusable roles, and shared automation.
- `docs/` — architecture, guardrails, testing, and troubleshooting guidance.

## Safety principles

1. Never store passwords, private keys, API keys, or access tokens in Git.
2. Default to read-only diagnosis.
3. Validate targets and limit execution scope.
4. Require human approval for state-changing actions.
5. Prefer idempotent automation with explicit rollback steps.
6. Test in a non-production environment first.

## Status

Initial repository scaffold.
