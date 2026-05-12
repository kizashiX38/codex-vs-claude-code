# Live Sweep Status — 2026-05-12

This file records what was actually checked live after the user corrected the scope: Codex evidence on Mac, Arch, Debian/Zorin, and Windows-side Codex state mounted from the Debian PC.

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

## Windows Codex State Mounted From Debian

Status: checked live from the Debian PC against mounted Windows volumes.

This pass corrected a miss in the earlier sweep. Debian's Linux-side Codex state was not enough; the Windows user-profile Codex state mounted on Debian also had to be checked.

What was found:

- A large Windows-side Codex root exists under the Windows user profile.
- The root is about `1.2G` with thousands of files, dozens of JSONL files, and over a thousand Markdown files.
- Its newest inspected activity is from April 2026.
- An empty offline sandbox Codex profile also exists and has no evidence value by itself.
- Older Linux backup Codex roots are stored on Windows volumes and may be useful as historical mirrors, but they are not the main Windows Codex evidence node.

High-signal Windows Codex findings:

| Finding | Public-safe meaning |
|---|---|
| Windows Codex contains a handoff document written for Claude after a Windows/Arch recovery session. | Codex was not merely chatting; it was packaging operational state so Claude could continue without guessing. |
| The handoff records completed work, verified state, and known misses. | Codex preserved an evidence trail instead of leaving the next agent to reconstruct the situation from memory. |
| The handoff separates origin session state from later continuity state in the Lara/Claude recovery problem. | Codex distinguished "where the original session came from" from "which surviving path currently behaves like the strongest continuity." |
| The handoff rejects the absolute claim that a closed session is simply gone forever. | Codex corrected a bad Claude framing by grounding the answer in persisted transcript/session files. |
| The handoff identifies binary/runtime/root mismatch as a likely reason the same Claude session file behaved differently in different places. | Codex converted a mystical-feeling continuity failure into inspectable operational variables. |
| A separate isolated Claude test root exists around the recovered session file. | Codex/Windows-side work created a safer test lane instead of mutating the main Claude root. |
| Windows exports show a compaction/context-preservation incident where the user had to ask Claude to create proper Markdown memory files after an inadequate compact. | Claude's context management created extra user burden; the durable value was only recovered after explicit user direction and later file inspection. |
| Windows-side helper scripts exist for scanning Claude sessions across accounts and extracting continuity markers. | The recovery work had become procedural enough that scripts were needed to find what Claude should have tracked cleanly. |
| Some local helper scripts contain hardcoded SSH connection details. | Raw evidence cannot be published directly; the repo must keep only sanitized summaries and never include these helper scripts. |

Evidence value:

- This is a distinct evidence node from Mac, Arch, and Debian Linux home.
- It supports the claim that Codex acted as the forensic/operator layer over Claude's own session state.
- It also supports the "Claude made the user become middleware" pattern: the useful continuity map was produced by Codex after repeated Claude-side confusion.
- It adds a separate compaction/context-loss exhibit from April 2026, where the user had to force memory preservation after context was compressed badly.
- The public repo should describe the finding, but raw paths, volume IDs, account names, exact session IDs, transcript content, helper scripts, and credentials should stay local-only.

## Newly Supported Evidence Rows

- `D1`: Debian RDP 0x207 handoff — Claude/Lara escalated to Codex; Codex performed live diagnostics and the user later marked it working.
- `D2`: Debian/Zorin OpenClaw migration — Codex handled the Arch-to-Debian agent copy/setup path.
- `D3`: Debian model/provider failure loop — Codex debugged OpenClaw provider/model errors.
- `D4`: Claude session ingestion/indexing — Codex read and indexed large Claude session artifacts.
- `W1`: Windows Codex handoff for Claude — Codex preserved Windows/Arch recovery state and mapped Lara/Claude session-continuity evidence.
- `W2`: Windows compaction/context-preservation incident — Claude required explicit user direction to write durable memory files after context loss.
- `W3`: Windows helper-script evidence risk — local scripts prove procedural recovery work, but raw scripts contain secrets and must remain private.

## Blockers

- Raw Arch and Debian evidence contains secrets and private content, so only sanitized summaries should enter the public repo.
- Exact session IDs, local paths, hostnames, LAN IPs, account identifiers, tokens, and private transcript content must stay out.

## Next Exact Step

Extract seven public-safe snippets:

1. Arch: task line showing large Claude session read + sanitized summary.
2. Arch: task line showing index generation over 41 Claude session JSONLs.
3. Debian: RDP handoff problem/action/success marker.
4. Debian: OpenClaw migration/model-provider failure handle.
5. Windows Codex: handoff section showing origin-vs-continuity split and the correction that persisted session files still matter.
6. Windows Claude export: compaction/context-preservation request and resulting memory-file creation, paraphrased only.
7. Windows helper scripts: existence and purpose, with secret-bearing lines excluded.

Do not paste raw history lines without redaction.
