# Lara/OpenClaw Repair: March-April Claude Attempts, Codex Triage

This note summarizes a longer-running pattern around Lara/OpenClaw sessions on Arch. It uses redacted local evidence only and does not publish raw session JSONL, tokens, bot secrets, or full transcripts.

## Evidence Surface

Observed Claude-side session/state surfaces from March-April:

- `claude-opus-4-6` session indexed from 2026-03-29 to 2026-04-04.
- `claude-opus-4-6` session indexed from 2026-04-02 to 2026-04-03.
- `Claude Code v2.1.114 / Sonnet 4.6` transcript on 2026-04-22.
- `Claude Opus 4.7` / `2f33e078` Lara session material in `.claude-2f33-test` and Lara verification notes.

This is enough to support:

> Multiple Claude-side model/session surfaces touched the Lara/OpenClaw state across March-April.

It is not enough, by itself, to publish:

> Every Claude model failed.

Use the first statement publicly unless a fuller model-by-model proof is added.

## April 22 Claude/Lara Failure Shape

The April 22 Lara transcript was a 908-line Claude Code session around Kimi/OpenClaw.

Observed problem cluster:

- Kimi/OpenClaw bot responses showed a membership/API rejection.
- Telegram polling showed `409 getUpdates conflict`.
- The session checked multiple containers, including `kimi-v3.11` and `openclaw-kimi`.
- The root cause for one plugin-loading problem was an entrypoint reset:
  - `chown -R ubuntu:ubuntu /home/ubuntu`
- That reset caused OpenClaw to treat plugins as suspicious or incorrectly owned.

Claude-side progress:

- Found the entrypoint ownership reset.
- Injected a post-start ownership workaround before the supervisor loop.
- Reported that blocked plugin errors disappeared and plugins loaded.
- Still had unresolved Telegram `409 getUpdates conflict`.
- Still had no final verified end-to-end bot interaction.
- Session ended at usage limit before full recovery was proven.

## Codex Triage

Codex later read the April 22 Lara transcript directly and did what the case study expects an operator agent to do:

- Confirmed it read the actual 908/909-line transcript, not just the filename.
- Separated `actually fixed`, `still broken`, and `only assumed`.
- Identified the plugin ownership problem as actually fixed or improved.
- Identified Telegram `409 getUpdates conflict` as still not proven resolved.
- Identified Kimi membership/API rejection as not shown resolved.
- Preserved the usage-limit ending as part of the evidence.

This matters because Codex turned a long, emotionally and operationally tangled Claude session into a verifiable state table.

## Later Process Evidence

Later Codex-side inspection showed `kimi-v3.11` running with:

- `/usr/local/bin/openclaw-ubuntu-entrypoint`
- `gateway-supervisor.sh`
- `openclaw`
- `openclaw-gateway`
- `sshd`

This supports that the repair state was inspectable after the Claude session, but it does not by itself prove a complete end-to-end Telegram recovery.

## Public Framing

Use:

> Codex did not just fix a single command. It repeatedly converted Claude/Lara session sprawl into inspectable state: what was fixed, what was still broken, what was only assumed, and what evidence remained.

Avoid:

> Codex fully fixed every Lara/OpenClaw issue.

Avoid unless separately proven:

> Every Claude model failed.

