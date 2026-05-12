# Evidence Matrix

This is the control table for the public case study. It keeps the argument narrow:

> Claude Code repeatedly shifted operational burden back onto the user; Codex repeatedly converted the same mess into inspection, repair, verification, and artifacts.

Raw transcripts, exported sessions, `.eml` files, local paths, account identifiers, LAN topology, private names, medical details, receipts, and tokens stay local-only.

## Status Key

- `Ready`: enough redacted evidence exists for a public claim.
- `Needs excerpt`: source is known, but the public-safe quote/output still needs extraction.
- `Needs refresh`: source is known, but the current machine state should be rechecked before publication.
- `Supporting`: useful context, not a primary Codex-vs-Claude exhibit.
- `Do not publish as fact`: keep as hypothesis unless externally sourced and verified.

## Matrix

| ID | Incident | Window | Claude failure pattern | Codex action | Evidence anchors | Public-safe claim | Status | Redaction risk | Next action |
|---|---|---:|---|---|---|---|---|---|---|
| A1 | Arch SSH diagnosis | 2026-05-11 | Asked the user for discoverable network state and chased a wrong host assumption. | Inspected route/interface/ARP/SSH state and proved the working target with an SSH round trip. | `ARCH_FINDINGS.md`, `CODEX_ARCH_FINDINGS.md`, `CODEX_THREE_DEVICE_SWEEP.md`, `CASE_STUDY.md` | For local-network ops, Codex behaved like an operator; Claude made the user become middleware. | Ready | Device names, LAN IPs, exact paths | Keep as lead technical exhibit. |
| A2 | Existing Claude config miss | 2026-05-11 | Missed pre-existing Claude account/config directories before scaffolding more state. | Audited the account/config layout and separated what existed from what was newly deployed. | `ARCH_FINDINGS.md`, `CODEX_ARCH_FINDINGS.md`, `CODEX_THREE_DEVICE_SWEEP.md` | Premium agent work failed at state inspection before mutation; Codex restored inventory discipline. | Ready | Account emails, local home paths | Publish only the redacted config-shape summary. |
| A3 | Wrong memory sync source | 2026-05-11 | Used or accepted the wrong source tree, requiring correction after the user had already been burdened. | Identified the correct current source and preserved machine-local session JSONLs instead of overwriting them. | `ARCH_FINDINGS.md`, `CODEX_THREE_DEVICE_SWEEP.md`, `CASE_STUDY.md` | The failure was not "slow work"; it was user-burden collapse during a sync task. | Ready | Local path disclosure | Keep exact path names out; describe as current source vs stale mirror. |
| A4 | Skill YAML / agent toolbox repair | 2026-05-11 | Claude-side tools failed to load because frontmatter was malformed; Claude did not catch and repair it cleanly. | Fixed the two `SKILL.md` files and verified YAML parsing with a parser round trip. | `LARA_OPENCLAW_REPAIR.md`, `CODEX_THREE_DEVICE_SWEEP.md`, `CASE_STUDY.md` | Codex repaired the Claude/Lara agent toolbox that Claude itself was failing to use. | Ready | Skill names are okay; local paths are not | Add a tiny before/after excerpt if needed, without full file paths. |
| A5 | Lost Claude app session recovery | 2026-05-11 | A Claude app session was effectively lost/unusable for weeks across repeated attempts. | Found the exact session, tied it to preserved project state, and made it recoverable. | `CLAUDE_APP_SESSION_RECOVERY.md`, `CODEX_THREE_DEVICE_SWEEP.md`, `CASE_STUDY.md` | Codex recovered continuity that repeated Claude-side attempts had not restored. | Ready | Session UUIDs, project paths | Avoid publishing raw UUID unless it adds proof value. |
| A6 | Lara/OpenClaw transcript triage | 2026-05-11 | Session sprawl made the broken path hard to reason about and easy to re-open endlessly. | Grouped the relevant failure clusters and separated durable repairs from repeated narration. | `LARA_OPENCLAW_REPAIR.md`, `DEBIAN_OPENCLAW_FAILURES.md`, `CODEX_THREE_DEVICE_SWEEP.md` | Codex converted months of agent drift into inspectable incident clusters. | Needs excerpt | Hostnames, auth traces, private repo names | Extract two sanitized command/output snippets. |
| A7 | Read-only agent tax | 2026-05-11 | Claude repeatedly audited, narrated, and stopped at the edge of action, leaving the user to carry the next move. | Codex named the failure mode and turned it into publishable operational categories. | `READ_ONLY_AGENT_TAX.md`, `CASE_STUDY.md` | A premium coding agent can be expensive while still functionally read-only if it avoids the operator loop. | Ready | Emotional transcript content | Keep it technical: task, elapsed time, action withheld, proof available. |
| A8 | NC#1 / NC#2 user-as-QA loop | 2026-05-11 | Multiple Claude agents required the user to coordinate, correct, and verify in parallel. | Codex framed the cluster as user-as-QA-lead and mapped the repeated burden transfer. | `NC_AGENT_FAILURES.md`, `CASE_STUDY.md` | The failure scales across agents: more Claude instances did not mean less user burden. | Needs excerpt | Raw transcript tone, private names | Build a 3-row public excerpt: ask, failure, user correction. |
| A9 | Debian/OpenClaw model/auth failure loop | 2026-05-11 | Claude-side work looped around model/provider/auth problems without closing the operational path. | Codex identified the model/provider failure surface and the repair sequence. | `DEBIAN_OPENCLAW_FAILURES.md`, `CODEX_THREE_DEVICE_SWEEP.md` | Codex acted as the repair agent for Claude-adjacent infrastructure. | Needs refresh | Hostnames, tokens, service names | Recheck current sanitized state before making a strong claim. |
| A10 | GPT-5.5 page + `gpus ?` context carry | 2026-05-11 | Claude stalled at fetch/tooling friction and over-expanded simple prompts. | Codex preserved context from the URL and answered the one-word follow-up directly. | `CODEX_THREE_DEVICE_SWEEP.md`, `CASE_STUDY.md`, `SOURCES.md` | Codex carried task context across a short prompt where Claude repeatedly made the user re-specify intent. | Ready | Browser tabs, account details | Keep to URL + answer behavior; do not publish personal browser context. |
| S1 | Support/refund closure | 2026-05-11 | Support path closed without resolving the paid-product dispute. | Not a Codex repair; useful only as why the public case study exists. | `CLAIMS.md`, `SOURCES.md` | The case study is the escalation artifact after normal support failed. | Supporting | Emails, receipt IDs, support names | Publish only if fully redacted and relevant. |

## Do Not Publish As Fact Yet

These may be part of the working theory, but they need source-backed handling before public claims:

| Claim | Why held back | Required proof |
|---|---|---|
| "TPUs caused Claude degradation." | Hardware-to-behavior causation is not proven by local agent failures alone. | Public Anthropic infra statements, timeline evidence, and careful wording as hypothesis. |
| "Every Claude model failed." | The repo currently proves repeated failures across named sessions, not exhaustive model coverage. | Model-by-model transcript excerpts with timestamps and outcomes. |
| "GPT-5.5 GPUs explain the entire performance gap." | OpenAI hardware claims can support substrate comparison, but not total causation alone. | Official OpenAI page excerpts plus external benchmark/source citations. |
| "Anthropic intentionally diverted good compute away from users." | Intent is a high-risk claim. | Direct public admission or avoid intent language. |

## Publication Order

1. Lead with `A1`, `A4`, and `A5`: they are concrete, technical, and easiest to verify.
2. Use `A7` and `A8` to define the broader failure mode after the hard exhibits.
3. Keep hardware/substrate claims in a separate sourced appendix, not as the core proof.
4. Keep raw evidence local. Public repo gets summaries, redacted snippets, and reproducible command shapes only.
