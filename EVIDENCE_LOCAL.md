# Local Evidence Map

This file summarizes local evidence without copying raw private artifacts.

Source map generated from:

- `[MAC_HOME]/agent-user-burden-collapse-evidence-map.md`
- `[MAC_HOME]/2026-05-11-140422-this-session-is-Lara369-macos.txt`
- `[MAC_HOME]/Downloads/ChatGPT-Codex Fixes Lara's Toolbox.txt`
- Anthropic support `.eml` exports in `[MAC_HOME]/Downloads`
- Local Claude config dirs under `[MAC_HOME]/.claude*`

## Claude Config Shape

Observed home-level Claude dirs:

- `[MAC_HOME]/.claude`: 1.6G, primary heavy tree.
- `[MAC_HOME]/.claude-max`: 7.5M config shell with symlinks back to `.claude`.
- `[MAC_HOME]/.claude-alt`: 4.6M.
- `[MAC_HOME]/.claude-private`: 219M.

Important finding:

`.claude-max/projects` symlinks to `.claude/projects`. That makes per-account session attribution lossy from JSONL path alone.

## Alias Evidence

Observed in `[MAC_HOME]/.zshrc`:

- `claude-dxm` documented as primary.
- `claude-max` documented as workhorse Max 5x.
- `claude-dxm` uses `CLAUDE_CONFIG_DIR=$HOME/.claude`.
- `claude-max` uses `CLAUDE_CONFIG_DIR=$HOME/.claude-max`.

## Security Finding

Read-only inspection found secret-shaped material in:

- `[MAC_HOME]/.claude/settings.local.json`
- `[MAC_HOME]/.claude-max/settings.local.json`

Those files appear to contain saved command/history entries with API-key, bearer-token, and GitHub-token shaped material.

Do not publish raw config. Rotate/scrub before public release.

## Support Email Evidence

Observed support chain in `[MAC_HOME]/Downloads`:

- Transfer/refund request emails.
- Quality-of-service complaint emails.
- Fin AI Agent replies.
- Refund denial based on prior refund history.
- Closed/no-longer-monitored support thread.

Do not publish raw `.eml`.

## High-Value Case Study Incidents

1. Network discovery:
   - Claude Code guessed and asked for user-side debugging.
   - Codex inspected and verified working SSH path.

2. Existing config:
   - Claude Code proposed architecture before checking existing `.claude-*` dirs/aliases.
   - Existing dirs/aliases were already present.

3. Sync source:
   - Claude Code initially used stale memory mirror, then corrected.

4. Harness/toolbox:
   - Broken agent skill YAML prevented skill loading.
   - Startup log identified:
     - `.agents/skills/lara-lineage/SKILL.md`
     - `.agents/skills/new-openclaw-agent/SKILL.md`
   - Both failed with invalid YAML in `SKILL.md` frontmatter.
   - Codex fixed the frontmatter and verified parsing with Ruby YAML.
   - Follow-up scan showed all local `.agents/skills/*/SKILL.md` files parse cleanly.

5. Public page/context carry:
   - Claude Code hit a 403/Cloudflare wall and stopped at options.
   - Codex retrieved the OpenAI GPT-5.5 page and answered `gpus ?` from context.
