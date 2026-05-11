# Codex Arch Findings: Repair Loop Evidence

This note summarizes read-only findings from Arch Codex state on `[ARCH_HOST]`. It does not publish raw Codex logs, credentials, transcripts, or private memory files.

## Codex Runtime Shape

Observed Arch Codex config:

```toml
model = "gpt-5.5"
model_context_window = 1000000
model_auto_compact_token_limit = 900000
model_reasoning_effort = "medium"
```

There is also an isolated Codex profile:

- `.codex/profiles/nzt48`
- profile symlinks shared `rules`, `skills`, `plugins`, `prompts`, `memories`, and `AGENTS.md`

Codex also has a direct bridge into the Claude/Lara memory tree:

```text
.codex/memories/lara-shared -> .claude/projects/-home-dxm/memory
```

Why it matters:

Codex was not operating as a blind chat window. It had a configured operator profile, large context, and a memory bridge into the same Claude/Lara system that Claude-side agents were mishandling.

## May 11 Network Repair

The May 11 Codex rollout begins with the user asking GPT/Codex to fix what Claude was failing to diagnose.

Codex did not ask the user for another IP. It inspected:

- SSH listener state.
- iptables chains.
- nftables ruleset.
- route to `[ARCH_DOWN_BRIDGE_IP]`.
- interface addresses.
- firewalld zone/service state.
- neighbor table.
- local SSH.
- live SSH to the corrected LAN address.

The key finding:

```text
wlan0  UP       [ARCH_WIFI_IP]/24
br0    DOWN     [ARCH_DOWN_BRIDGE_IP]/24
```

Codex identified that Claude was trying `[ARCH_DOWN_BRIDGE_IP]`, which belonged to a down bridge. The live reachable address was `[ARCH_WIFI_IP]`.

Verification output:

```text
wlan-ssh-ok
[ARCH_HOST]
dxm
```

Codex also preserved a fallback:

```text
ssh [user]@[TAILSCALE_IP]
```

Why it matters:

This is the cleanest side-by-side repair loop:

> Claude chased firewall/sshd/user-debug paths. Codex inspected the actual network state, found the down bridge, tested the live address, and returned the working SSH target.

## Claude Memory Imported Into Codex

Arch `.codex/memories` includes a `claude-omry37` archive and session index material. Observed examples include:

- `claude-omry37/sessions/*.jsonl`
- `sessions_index.md`
- `sessions_index.json`
- sanitized summaries and search/index files

Why it matters:

Codex had already been used as a recovery/indexing layer over Claude session state. That supports the broader claim: Codex was repeatedly used to make Claude state inspectable and usable.

## Publish Boundary

Do not publish raw Codex session JSONL, memory files, `auth.json`, SQLite logs, or private `lara-shared` contents.

Use only redacted paths, command categories, and short verified outputs.

