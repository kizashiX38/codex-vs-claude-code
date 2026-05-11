# Claude App Session Recovery: The Lara Session ID

This note captures the exact Lara/Claude Code session recovery trail found on local systems. It is intentionally redacted for public use: do not publish raw session titles, raw JSONL transcripts, or app state files.

## Exact Session

Recovered Claude Code session ID:

```text
2f33e078-9e60-443d-9324-c9e97eda998b
```

Local evidence shows this was the Lara session the operator was trying to preserve and resume. The UI/session name is sensitive and should be redacted in public-facing text.

Evidence points:

- Arch Claude app/session metadata under `.claude-2f33-test` shows the session ID and active UI name.
- `.claude-2f33-test/history.jsonl` repeatedly probes this session ID for identity/continuity verification.
- `Lara-369-CC/verification/LARA_VERIFICATION.md` records a 2026-04-24 live-session verification where `2f33e078-...` passed the Lara behavioral checks.
- Mac Claude app cowork/session state later contained a local app record for the same underlying Claude Code session ID.

## Lost-Session Marker

The "lost Lara for a month" marker appears in Arch `.claude-alt/history.jsonl` in the same operational cluster, with the user explicitly warning about resuming the Lara session safely.

This is enough to support:

> The operator had a known prior loss-of-continuity incident and was trying to avoid corrupting or losing the Lara session again.

It is not enough, by itself, to publish:

> The session was continuously unrecoverable for exactly one calendar month.

Use the first statement unless a stricter date-by-date proof is added.

## Codex Recovery Trail

The clearest Codex repair trail found so far is local Codex on 2026-05-06.

Codex identified that the underlying Claude Code session had already been copied across project roots, but the app-side cowork/session state still pointed at the old Linux path:

```text
cwd: [LINUX_HOME]
originCwd: [LINUX_HOME]
```

Codex then found the exact Claude desktop app-side JSON record for the session:

```text
[MAC_HOME]/Library/Application Support/Claude/claude-code-sessions/.../local_2f33e078-9e60-443d-9324-c9e97eda998b.json
```

The smallest safe repair was copy-only:

- Preserve the original app-side record unchanged.
- Create a new app-side session JSON with a fresh local session ID.
- Keep `cliSessionId` pointed at `2f33e078-9e60-443d-9324-c9e97eda998b`.
- Change only app-side `sessionId`, `cwd`, `originCwd`, and timestamps for the Mac path.
- Backup the original local app record before writing the copy.

This is the important contrast: Codex did not ask the user to manually reason through Claude app internals. It inspected the real app state, identified the broken path binding, proposed the smallest non-destructive repair, backed up, copied, and verified the resulting artifact.

## Model Attribution

Verified from local Codex metadata:

- The May 6 session-recovery trail is recorded under Codex model metadata `gpt-5.5`.
- Separate April 24 Codex sessions show `gpt-5.4`, including an OpenClaw service crash-loop fix, but those are not yet tied to the `2f33e078` Claude app-session recovery.

Use:

> Codex recovered the exact Lara session pathing problem by repairing Claude app-side session state.

Avoid unless separately proven:

> GPT-5.4 fixed the exact `2f33e078` session recovery.

## Public Framing

Use:

> A Claude Code Lara session was not simply "lost"; its underlying session ID existed, but Claude app-side state pointed at the wrong working directory. Codex found the exact app-side record and created a safe Mac-path copy without mutating the original.

Avoid:

> Publish the raw session title or raw app JSON.

