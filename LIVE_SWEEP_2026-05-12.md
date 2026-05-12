# Live Sweep Status — 2026-05-12

This file records what was actually checked live after the user corrected the scope: Codex evidence on Mac, Arch, and Debian/Zorin.

It is intentionally sanitized. Raw `.jsonl`, `.eml`, credentials, account identifiers, local paths, LAN topology, hostnames, private names, and medical/family details do not belong in the public repo.

## Mac

Status: checked live.

What was found:

- Local Codex memory exists and includes rollout summaries.
- The Mac memory index includes the Mac-to-Arch SSH repair rollout.
- Local history contains the current repo/publication task and the user correction that the requested sweep was Mac + Arch + Debian, not only repo-doc organization.

Evidence value:

- Confirms the Mac side has a durable Codex memory trail for the Arch SSH/cable repair.
- Confirms the current repo work is a separate public packaging layer, not the raw evidence source.

## Arch

Status: checked live on redo pass.

The first pass was wrong/incomplete because the Mac was not seeing the wired interface at that moment. Redo pass showed the wired interface active again and SSH round-trips to the Arch host succeeded.

What was found:

- Arch Codex state is substantial.
- Multiple Claude account/config trees exist alongside Codex state.
- Arch Codex contains imported Claude session material.
- Arch Codex contains generated session indexes for Claude session JSONLs.
- Arch Codex contains sanitized summaries/timelines derived from large Claude sessions.
- Arch Codex contains May 2026 session state, including a May 11 Codex rollout.

High-signal Arch findings:

| Finding | Public-safe meaning |
|---|---|
| Codex memory task list says Codex read a large Claude session and wrote a sanitized summary. | Codex was used to ingest and summarize Claude session evidence that was too large for casual manual review. |
| Codex memory task list says Codex generated an index of 41 Claude session JSONLs. | Codex created navigable structure over Claude's own sprawling artifacts. |
| Codex memory includes Claude session indexes with model/date/export columns. | Codex turned raw Claude history into an auditable evidence table. |
| Codex memory contains OpenClaw/Claude operational summaries and EWA-style evidence reports. | Codex was already functioning as the evidence and operations layer over the Claude/OpenClaw stack. |
| Direct Arch Codex search found recent May 2026 sessions and older March/April repair sessions with many Claude/OpenClaw hits. | The repair trail is not only local Mac memory; it exists on the Arch Codex machine itself. |

Evidence value:

- The earlier `Arch blocked` status is superseded.
- Live Arch read confirms direct on-machine evidence for Claude-session ingestion, indexing, OpenClaw repair context, and Codex-as-audit-layer.

## Debian/Zorin

Status: checked live over SSH.

What was found:

- Codex state exists and is substantial.
- Claude state exists and is substantially larger.
- Codex session history spans February through May 2026.
- Codex has bridge history files from other machines.
- Codex memory includes an Arch sync task list and Lara shared memory bridge.

High-signal Debian findings:

| Finding | Public-safe meaning |
|---|---|
| RDP failure handoff from Claude/Lara to Codex is present in Codex history. | Claude escalated a concrete workstation failure to Codex; Codex then operated on the machine instead of staying in analysis. |
| Codex history includes the user saying the RDP path worked without reboot. | The same incident has a success marker after Codex intervention. |
| OpenClaw migration request from Arch to Debian/Zorin is present. | Codex was used to move/repair agent infrastructure across machines. |
| Model/provider failures such as HTTP 400 and expired/invalid provider state appear in Codex history. | Codex was debugging model-routing/provider issues in the OpenClaw stack. |
| Arch sync task list says Codex read a large Claude session and generated an index of dozens of Claude session JSONLs. | Codex was used as the audit/ingest layer over Claude session evidence. |

## Newly Supported Evidence Rows

- `D1`: Debian RDP 0x207 handoff — Claude/Lara escalated to Codex; Codex performed live diagnostics and the user later marked it working.
- `D2`: Debian/Zorin OpenClaw migration — Codex handled the Arch-to-Debian agent copy/setup path.
- `D3`: Debian model/provider failure loop — Codex debugged OpenClaw provider/model errors.
- `D4`: Claude session ingestion/indexing — Codex read and indexed large Claude session artifacts.

## Blockers

- Raw Arch and Debian evidence contains secrets and private content, so only sanitized summaries should enter the public repo.
- Exact session IDs, local paths, hostnames, LAN IPs, account identifiers, tokens, and private transcript content must stay out.

## Next Exact Step

Extract four public-safe snippets:

1. Arch: task line showing large Claude session read + sanitized summary.
2. Arch: task line showing index generation over 41 Claude session JSONLs.
3. Debian: RDP handoff problem/action/success marker.
4. Debian: OpenClaw migration/model-provider failure handle.

Do not paste raw history lines without redaction.
