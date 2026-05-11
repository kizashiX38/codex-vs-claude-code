# Arch Findings: Claude State Sprawl and Recovery

This note summarizes read-only findings from the Arch machine `[ARCH_HOST]` on 2026-05-11. It does not include raw credentials, emails, transcripts, or private JSON.

## Machine Snapshot

- Host: `[ARCH_HOST]`
- OS: Arch Linux, kernel `6.18.20-1-lts`
- Home: `[LINUX_HOME]`

## Claude State Sprawl

Home-level Claude/Codex state included:

- `.claude`
- `.claude-nzt48`
- `.claude-omry37`
- `.claude-alt`
- `.claude-private`
- `.claude-2f33-test`
- `.claude-max`
- `.codex`
- `.codex-winserv-import`

Session JSONL counts observed under Claude project trees:

| tree | JSONL count |
|---|---:|
| `.claude` | 86 |
| `.claude-nzt48` | 16 |
| `.claude-omry37` | 164 |
| `.claude-alt` | 1 |
| `.claude-private` | 0 |
| `.claude-max` | 0 |
| `.claude-2f33-test` | 2 |

The main `.claude` root also contained 30 ` - Copy` cruft entries, including copied settings, credentials-shaped files, history, projects, sessions, plugins, telemetry, and cache directories.

## Incident A: Existing Architecture Missed

In the Arch transcript, Claude first proposed additional account/config architecture before inspecting all existing Claude directories and aliases.

The user asked whether Claude had checked the folders, dirs, and aliases. Claude then admitted it had grepped too narrowly and had missed the existing structure:

- `.claude`
- `.claude-nzt48`
- `.claude-omry37`
- `.claude-alt`
- `.claude-2f33-test`
- `.claude-private`
- existing `claude-nzt48` alias
- existing `claude-omry37` alias

Claude summarized the corrected finding as: the architecture it was about to build already existed on Arch, and the user had built it weeks earlier.

Why it matters:

This is another instance of user-burden collapse. The agent designed before inventorying, and the user had to force basic state inspection.

## Incident B: Wrong Memory Source

During sync work, Claude initially copied from the stale Linux-shaped memory source instead of the active macOS-native memory source.

Observed transcript facts:

- Initial sync used `-home-dxm/memory`.
- Claude then noticed only a few files transferred.
- Claude identified the active May writes under `-Users-dxm/memory`.
- Claude admitted the earlier sync used the wrong source.

Why it matters:

This is the same pattern as the directory miss: the agent had enough context to verify source freshness before syncing, but only caught the mistake after output looked wrong.

## Incident C: Scaffold Artifact After Corrections

The final useful artifact on Arch was:

- backup: `~/Documents/backup/dotclaude-arch-pre-max-deploy-20260511-130604.tar.gz`
- new config dir: `.claude-max`
- aliases: `claude-max`, `max`, `max-memory`
- `.claude-max` symlinks for shared projects, plugins, skills, hooks, and statusline scripts
- independent `.claude-max` settings and credential files

Later verification showed `.claude-max` authenticated successfully with:

```json
{
  "loggedIn": true,
  "authMethod": "claude.ai",
  "apiProvider": "firstParty",
  "subscriptionType": "max"
}
```

Why it matters:

The artifact is real, but it arrived after repeated corrections from the user and Codex. That distinction matters for the public case: outputs alone do not measure agent quality; the user burden required to reach them does.

## Publish Boundary

Do not publish raw Arch files:

- `.credentials.json`
- `.claude.json`
- `settings.local.json`
- raw session JSONL
- raw `.claude-private`
- backup tarballs

Use only redacted counts, paths, and short transcript excerpts.

