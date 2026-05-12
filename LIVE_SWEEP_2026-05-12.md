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

Status: not reachable live from the Mac during this pass.

Observed current network state:

- The Mac was only on the Wi-Fi subnet plus a VPN/tunnel interface.
- The old wired subnet route went through the tunnel, not a local wired interface.
- Tailscale CLI reported Tailscale stopped.
- SSH to the remembered Arch addresses timed out.

What could still be used safely:

- Mac Codex memory mirror for the Arch SSH repair.
- The existing sanitized Arch evidence docs already in this repo.
- Debian Codex memory references to Arch-originated Claude sessions and the Arch sync task list.

Evidence value:

- No new live Arch file read was completed in this pass.
- Existing Arch evidence remains valid as historical evidence, but should be labeled as memory/repo-derived unless Arch is reconnected and rechecked live.

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

- Live Arch sweep is blocked until the Mac can reach Arch again through the local network or Tailscale/VPN.
- Raw Debian evidence contains secrets and private content, so only sanitized summaries should enter the public repo.

## Next Exact Step

Extract two public-safe snippets from Debian:

1. RDP handoff: problem statement, Codex action, success marker.
2. Claude-session ingestion: task line showing large Claude session read + index generated.

Do not paste raw history lines without redaction.
