# Codex Three-Device Sweep

This is the boundary-safe sweep index for Codex evidence across the operator's three-device environment.

It does not copy raw `.codex`, `.claude`, `.eml`, transcript, app-state, or secret-bearing material.

## Device Inventory

| Device | Live status during sweep | Codex state | Claude state | Notes |
|---|---|---:|---:|---|
| Mac | local | `[MAC_HOME]/.codex` = 351M, 10 session JSONL files | `[MAC_HOME]/.claude` = 1.6G | Contains May Codex-vs-Claude comparison artifacts and repo |
| Debian | reachable at `[DEBIAN_LAN_IP]`, hostname `[DEBIAN_HOST]` | `[LINUX_HOME]/.codex` = 242M, 82 session JSONL files | `[LINUX_HOME]/.claude` = 2.5G | Contains older OpenClaw/Codex repair traces |
| Arch | not reachable on current `[CURRENT_LAN]` LAN during this pass | previously captured in `CODEX_ARCH_FINDINGS.md` | previously captured in `ARCH_FINDINGS.md` | Prior evidence came from direct Arch access on `[PRIOR_ARCH_LAN]` |

Arch is not omitted. It is separated because the current Mac network is `[CURRENT_LAN]`, while the earlier Arch evidence was on `[PRIOR_ARCH_LAN]`.

## Confirmed Repair / Contrast Clusters

### 1. Arch SSH Diagnosis

Allowed evidence:

- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:649`
- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:858`
- `CODEX_ARCH_FINDINGS.md`

Pattern:

- Claude path: chased the wrong network suspect, asked for user-side SSH/firewall/debug outputs, and left the operator carrying the diagnostic loop.
- Codex path: identified `br0` down, found the live LAN address, then later confirmed the wired route and `ssh ... hostname` round-trip.

Usable public claim:

> On the Arch SSH incident, Claude pushed the user into network middleware. Codex inspected interface state and route behavior, found the working host path, and returned a verified SSH target.

### 2. Claude Config Sprawl / Existing State Miss

Allowed evidence:

- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:1239`
- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:1330`
- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:1520`
- `ARCH_FINDINGS.md`

Pattern:

- Claude path: proposed architecture before fully reading existing `.claude-*` state, aliases, account split, binary split, and session overlap.
- Codex/GPT path: forced the state comparison back into the loop and exposed what should have been read first.

Usable public claim:

> Claude Code failed the basic operator-agent expectation: inspect local state before proposing changes to that state.

### 3. Mac Skill Harness Failure

Allowed evidence:

- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:2072`
- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:2078`
- `LARA_OPENCLAW_REPAIR.md`

Pattern:

- Claude/Lara-owned skill files had invalid `SKILL.md` YAML.
- Codex startup surfaced exact broken files and parser locations.
- Codex fixed the frontmatter and verified parsing.

Usable public claim:

> Codex repaired the Claude/Lara agent toolbox after Claude-side sessions left invalid skill metadata in place.

### 4. Lost Claude App Session Recovery

Allowed evidence:

- `CLAUDE_APP_SESSION_RECOVERY.md`
- Session ID redacted except where already necessary in the technical file.

Pattern:

- Claude app/session state pointed at the wrong working directory.
- Codex found the exact app-side JSON record, preserved the original, created a copy with corrected Mac pathing, and kept the underlying CLI session ID linked.

Usable public claim:

> Codex recovered a Claude app session continuity problem by repairing app-side session state without mutating the original record.

### 5. Debian OpenClaw / Model Failure Evidence

Allowed evidence:

- `[LINUX_HOME]/.codex/sessions/2026/02/14/rollout-2026-02-14T06-26-17-019c5a2f-5540-7eb2-a50d-7431e1c10b89.jsonl`
- `[LINUX_HOME]/Documents/Backups/openclaw_backup_2026-02-13 2/Documents/openclaw-history-analysis/messages.html`

Observed failure markers:

- `Unknown model`
- `Model ... not allowed`
- `HTTP 401: Invalid Authentication`
- `429 All credentials ... cooling down`
- `All models failed`
- `No API key found for provider "anthropic"`
- repeated agent failure before reply

Observed repair marker:

- `All audit findings fixed`
- recovery script path recorded as `[LINUX_HOME]/clawd/recover_cron_improved.sh`
- cron/model fallback work recorded around OpenClaw monitoring

Usable public claim:

> Debian evidence shows the same operational class: model/auth/provider failures surfaced to the user repeatedly, followed by a later repair loop that converted failure spam into concrete config and recovery-script changes.

Do not overstate yet:

> Do not claim this Debian cluster is exclusively a Claude failure until the exact model/provider chain is fully extracted and redacted.

### 6. GPT-5.5 Page / One-Word Context Carry

Allowed evidence:

- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:2397`
- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:2401`
- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt:2420`

Pattern:

- Claude hit a web-fetch/Cloudflare wall and stopped at options.
- Codex fetched/summarized the OpenAI page.
- User asked `gpus ?`.
- Codex inferred the active context and answered with GB200/GB300 NVL72.

Usable public claim:

> In the same live session, Codex preserved task context across a one-word follow-up where Claude had stalled at fetch failure.

## Current Limits

This is not a complete year-scale extraction. It is the first three-device sweep index:

- Mac: live inspected.
- Debian: live inspected.
- Arch: not live-reachable on current LAN; prior direct Arch evidence already exists in repo notes.

The next pass should deepen each cluster by extracting redacted, line-numbered snippets into incident notes, starting with Debian because it has 82 Codex sessions and 2.5G of Claude state.

## Next Evidence Targets

Search Debian first:

- `All audit findings fixed`
- `recover_cron_improved`
- `All models failed`
- `No API key found for provider "anthropic"`
- `Unknown model`
- `openai-codex`
- `claude-opus`
- `claude-sonnet`

Search Mac next:

- `Codex did`
- `Codex fixed`
- `Claude couldn't`
- `stopping here`
- `read-only`
- `operator-loop`
- `narrator-loop`

Search Arch when reachable:

- `~/.codex/sessions/2026/05/11/`
- `~/.claude-*`
- `2f33`
- `claude-max`
- `auth status`

