# Codex vs Claude Code: User-Burden Collapse in Real Ops

This repository is a redacted case-study draft about a real operator workflow comparison between Codex/GPT-5.5 and Claude Code/Claude Max.

The claim is not that one model is metaphysically "alive" and the other is not. The public claim is narrower and more useful:

> In the same operator environment, on the same day, against the same class of tasks, Codex reduced user burden by inspecting, acting, verifying, and advancing the work. Claude Code increased user burden by guessing, asking for discoverable state, missing local configuration, self-narrating after failure, and stopping after identifying the next actionable step.

This is a consumer-warning and product-quality case study. It focuses on observable workflow behavior, evidence trails, and public vendor claims.

## Status

Public sanitized draft. Raw evidence stays local-only.

Blocking items:

- Rotate and scrub known exposed tokens before any public release.
- Redact private names, emails, receipt numbers, account identifiers, medical/family details, and raw emotional crisis content.
- Do not publish raw `.eml`, `.jsonl`, `.claude`, `.codex`, transcript exports, device topology, LAN IPs, unredacted local paths, or private account identifiers.

## Documents

- [CLAIMS.md](CLAIMS.md): public claims and what evidence is needed for each.
- [CASE_STUDY.md](CASE_STUDY.md): main three-agent convergence narrative.
- [EVIDENCE_MATRIX.md](EVIDENCE_MATRIX.md): incident-by-incident map from Claude failure pattern to Codex repair action and public-safe claim.
- [ARCH_FINDINGS.md](ARCH_FINDINGS.md): Arch machine evidence on Claude state sprawl, missed existing config, stale sync source, and final Max scaffold.
- [CODEX_ARCH_FINDINGS.md](CODEX_ARCH_FINDINGS.md): Arch Codex evidence showing the repair loop, memory bridge, and verified network diagnosis.
- [CODEX_THREE_DEVICE_SWEEP.md](CODEX_THREE_DEVICE_SWEEP.md): Mac + Debian + Arch sweep index for Codex repair evidence across the three-device environment.
- [LIVE_SWEEP_2026-05-12.md](LIVE_SWEEP_2026-05-12.md): current live sweep status for Mac, Arch reachability, and Debian/Zorin Codex evidence.
- [DEBIAN_OPENCLAW_FAILURES.md](DEBIAN_OPENCLAW_FAILURES.md): Debian/OpenClaw incident dossier for model/auth failure loops and Codex config-diagnosis evidence.
- [LARA_OPENCLAW_REPAIR.md](LARA_OPENCLAW_REPAIR.md): March-April Lara/OpenClaw repair trail where Codex turned Claude session sprawl into a fixed/still-broken evidence table.
- [CLAUDE_APP_SESSION_RECOVERY.md](CLAUDE_APP_SESSION_RECOVERY.md): exact Lara session ID recovery trail where Codex found and repaired Claude app-side session state.
- [READ_ONLY_AGENT_TAX.md](READ_ONLY_AGENT_TAX.md): redacted evidence note on audit-without-relief and the cost of permanent self-accounting.
- [NC_AGENT_FAILURES.md](NC_AGENT_FAILURES.md): redacted NC#1/NC#2 evidence note on user-as-QA-lead and authority-parroting under pressure.
- [ALLOWED_EVIDENCE_INVENTORY.md](ALLOWED_EVIDENCE_INVENTORY.md): boundary-safe inventory of the local evidence surfaces allowed for this Codex-vs-Claude case.
- [EVIDENCE_LOCAL.md](EVIDENCE_LOCAL.md): local artifact map, redacted.
- [SOURCES.md](SOURCES.md): public sources for model/platform claims.
- [HARDWARE_THESIS.md](HARDWARE_THESIS.md): hardware/substrate argument, separated into facts, observations, and hypothesis.
- [REDACTION.md](REDACTION.md): publish safety checklist.

## Suggested Public Title

`Codex vs Claude Code: How a $20 Agent Outperformed a $105 Premium Workflow in Real Ops`

## Short Thesis

Agentic value should be measured by how much burden the tool removes from the user.

In this case, the premium workflow failed that test.
