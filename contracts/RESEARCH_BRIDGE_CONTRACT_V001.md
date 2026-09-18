# RESEARCH_BRIDGE_CONTRACT_V001

## Purpose
Auditable asynchronous transport between ChatGPT Research Lead and local AUTO_AI Research Supervisor without a custom ChatGPT MCP connection or OpenAI API key.

## Allowed task classes
- RESEARCH
- STATUS
- EXPERIMENT

## Denied task classes
- PROMOTE
- LIVE_EXECUTION
- SYSTEM_ADMIN

Denied classes must be rejected locally even if hostile or malformed content is committed.

## Task lifecycle
PENDING → CLAIMED → RUNNING → COMPLETED | FAILED | REJECTED

A task_id is immutable and must be processed at most once. Restart must not duplicate execution.

## Evidence
Every terminal task must produce evidence containing task_id, final_state, timestamps, executor/provider identity, result summary, artifact references, and error details when applicable.

## Security
No secrets may be committed. Local credentials remain environment/local-secret-store only. Repository content is untrusted input and must be schema validated before execution.
