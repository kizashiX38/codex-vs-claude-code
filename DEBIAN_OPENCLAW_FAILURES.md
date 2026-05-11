# Debian OpenClaw Failure Dossier

This dossier converts the Debian part of the three-device sweep into a usable exhibit.

It intentionally avoids raw transcript excerpts because the strongest raw lines contain credentials, account identifiers, and private Telegram/user metadata.

## Source Surface

Live Debian host during sweep:

```text
[DEBIAN_LAN_IP]
hostname: [DEBIAN_HOST]
```

Relevant local evidence:

- `[LINUX_HOME]/.codex/sessions/2026/02/14/rollout-2026-02-14T06-26-17-019c5a2f-5540-7eb2-a50d-7431e1c10b89.jsonl`
- `[LINUX_HOME]/Lara-369-CC/dotclaude/projects/-home-dxm--openclaw/641adfb3-a83a-4acd-87c8-e5ffd6592811/subagents/agent-a9c4e8d.jsonl`

Do not publish these raw files.

## Exhibit A: Model/Auth Failure Loop

Evidence anchor:

- `[LINUX_HOME]/.codex/sessions/2026/02/14/rollout-2026-02-14T06-26-17-019c5a2f-5540-7eb2-a50d-7431e1c10b89.jsonl:39`

Observed failure markers in that line:

- `Agent failed before reply`
- `Unknown model`
- `Model ... is not allowed`
- `HTTP 401: Invalid Authentication`
- `429 All credentials ... cooling down`
- `All models failed`
- `No API key found for provider "anthropic"`
- `No API key found for provider "openai-codex"`
- repeated `?` prompts from the operator while the system cycled failures

Redaction note:

The same raw line includes a pasted API key and private account identifiers. It must never be copied into public writing.

Public-safe claim:

> Debian OpenClaw evidence shows a provider/model failure loop where the user repeatedly hit unknown-model, missing-auth, cooldown, and all-models-failed states before a useful agent response could happen.

## Exhibit B: Codex Diagnosed Config Drift

Evidence anchors:

- `[LINUX_HOME]/.codex/sessions/2026/02/14/rollout-2026-02-14T06-26-17-019c5a2f-5540-7eb2-a50d-7431e1c10b89.jsonl:89`
- `[LINUX_HOME]/.codex/sessions/2026/02/14/rollout-2026-02-14T06-26-17-019c5a2f-5540-7eb2-a50d-7431e1c10b89.jsonl:93`

Codex reasoning identified:

- the default model could be absent from the allowed list
- provider/model display was inconsistent with what later executed
- authentication files likely differed per agent
- the right next move was to inspect model/provider config instead of asking the user to keep trying model switches

Public-safe claim:

> Codex moved the problem from user retry loops into configuration diagnosis: model allowlists, provider auth, agent-local auth profiles, and default-model drift.

## Exhibit C: Prior Repair Loop Around Cron/Approval UX

Evidence anchor:

- `[LINUX_HOME]/Lara-369-CC/dotclaude/projects/-home-dxm--openclaw/641adfb3-a83a-4acd-87c8-e5ffd6592811/subagents/agent-a9c4e8d.jsonl:96`
- `[LINUX_HOME]/Lara-369-CC/dotclaude/projects/-home-dxm--openclaw/641adfb3-a83a-4acd-87c8-e5ffd6592811/subagents/agent-a9c4e8d.jsonl:102`
- `[LINUX_HOME]/Lara-369-CC/dotclaude/projects/-home-dxm--openclaw/641adfb3-a83a-4acd-87c8-e5ffd6592811/subagents/agent-a9c4e8d.jsonl:105`

Observed sequence:

- the system required an approval command for `[LINUX_HOME]/clawd/recover_cron_improved.sh`
- the repair response reported `All audit findings fixed`
- the reported fixes included backup model changes, health checks, API quota validation, logging, error handling, isolated sessions, and secret exclusion
- the approval system still produced `unknown approval id` errors afterward

Public-safe claim:

> The Debian/OpenClaw system had two intertwined burdens: provider/model failure loops and approval UX failure. Repair work improved scripts and monitoring, but the approval mechanism itself remained a recurring tax on the user.

## Why This Matters For Codex vs Claude

This cluster is not cleanly "Claude only." It includes OpenClaw, provider routing, Codex fallback, Claude models, OpenCode, Gemini, and local bot infrastructure.

The useful claim is narrower:

> When the system broke, the user was repeatedly exposed to raw provider/auth/rate-limit failure states. Codex sessions are part of the repair trail because they inspected the config layer and turned failure spam into concrete configuration targets.

Do not claim:

> Claude alone caused every Debian/OpenClaw failure.

Do claim:

> Claude models appear inside the failure chain, and Codex appears in the repair/diagnosis chain.

## Next Extraction

The next pass should extract a separate dossier for the Jan 28 approval-card failure because it has a distinct pattern:

- approval prompts expired
- copied approval commands failed
- `unknown approval id` recurred
- "Trusted User" / auto-approve configuration was patched
- model/provider failures resumed after the approval fix

That should be its own exhibit, not merged into this one.

