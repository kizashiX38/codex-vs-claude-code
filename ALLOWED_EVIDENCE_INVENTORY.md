# Allowed Evidence Inventory

This file fixes the project boundary for this repository.

The case is **Codex vs Claude Code**: observable agent behavior in Reem's local ops environment, with raw private material kept out of the repo.

## Explicit Boundary

Out of scope for this repo:

- `[OUT_OF_SCOPE_RESEARCH_DIR]`
- GPT-5.5 web-research handoff material
- Separate zero-point / portable-agent research projects
- Any unrelated repository or evidence corpus unless Reem explicitly assigns it to this repo

Do not use those sources to support this case.

## Allowed Local Source Surfaces

Current local source surfaces that belong to this case:

| Surface | Observed size/count | Use |
|---|---:|---|
| `[MAC_HOME]/.claude` | 1.6G | Claude Code state, sessions, settings, memory, project traces |
| `[MAC_HOME]/.claude-alt` | 4.6M | Alternate Claude config evidence |
| `[MAC_HOME]/.claude-max` | 8.8M | Claude Max split config and Max-session evidence |
| `[MAC_HOME]/.claude-private` | 219M | Private Claude evidence, redacted summaries only |
| `[MAC_HOME]/.codex` | 350M | Codex state and repair-session traces |
| `[MAC_HOME]/Lara-369-CC` | 549M | Lara/Claude ecosystem state and historical exported evidence |
| Downloads/Desktop/Documents exports | 181 obvious `.eml`/`.txt`/`.md`/`.jsonl`/`.pdf` artifacts | Support emails, exported sessions, screenshots, local notes |
| Text-ish Claude/Codex files | 9518 files | Search corpus for allowed evidence extraction |

These numbers are inventory proof, not final analysis.

## Allowed Evidence Classes

Use these evidence classes:

- Claude Code session exports and local transcript files.
- Codex session exports and local transcript files.
- `.claude*` configuration shape, aliases, session paths, and non-secret metadata.
- `.codex` session traces showing repair loops, tool use, verification, and concrete fixes.
- Downloaded Anthropic support/refund `.eml` files, summarized only.
- Local screenshots and exported chat files directly about Claude, Codex, Anthropic, Max, agent failures, or support/refund handling.
- Redacted commands and outputs that demonstrate agent behavior.

Do not publish raw `.eml`, `.jsonl`, `.claude`, `.codex`, screenshots with private identifiers, tokens, receipt numbers, or account details.

## Already Captured Incident Clusters

The repo currently contains redacted notes for:

- Arch deployment and Claude state sprawl: `ARCH_FINDINGS.md`
- Codex repair of Arch/network/memory path issues: `CODEX_ARCH_FINDINGS.md`
- Claude tool harness / skill YAML fixed by Codex: `LARA_OPENCLAW_REPAIR.md`
- Claude app session recovery fixed by Codex: `CLAUDE_APP_SESSION_RECOVERY.md`
- Read-only/audit-without-relief failure mode: `READ_ONLY_AGENT_TAX.md`
- NC#1 and NC#2 agent failure evidence: `NC_AGENT_FAILURES.md`

Those are May-heavy incident clusters. They are not the whole story.

## Next Allowed Sweep Targets

Next pass should stay inside the allowed surfaces and search for older evidence using exact handles:

- `Nov 2024`, `Jan 2025`, `July 2025`, `OpenClaw`, `Nova 369`, `vibe coding`
- `stopping here`, `read-only`, `audit`, `operator-loop`, `narrator-loop`
- `Claude Max`, `Max 5x`, `refund`, `quality of service`, `not fit for purpose`
- `Codex fixed`, `Codex repaired`, `GPT-5.1`, `GPT-5.2`, `GPT-5.4`, `GPT-5.5`
- `TPU`, `GPU`, `Trainium`, `Blackwell`, `GB200`, `GB300`

Output should be another redacted repo note, not raw transcript dumps.

## Claim Discipline

Keep three lanes separate:

- **Proven locally:** backed by a path, timestamp, transcript excerpt, or command output in the allowed source surfaces.
- **Supported but needs public source:** local evidence exists, but public claims about vendors, chips, pricing, model timelines, or support policy need official/public links.
- **Hypothesis:** Reem's lived technical thesis or inference, presented as inference unless independently sourced.

The repo wins by being hard to dismiss. Evidence first, rage outside the artifact.
