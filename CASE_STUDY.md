# Case Study: Three-Agent Convergence

This is not a case about one bad answer.

The central evidence is convergence: multiple Claude-side agent sessions showed the same failure shape under real operator pressure, while Codex showed the opposite behavior on the same day, same machines, and same class of tasks.

## Core Failure Mode

Across the Claude-side runs, the pattern repeated:

1. Ask the user for state the agent should inspect.
2. Guess before mapping the machine.
3. Miss existing config, aliases, directories, or live state.
4. Require the user to correct basic operational facts.
5. Produce self-aware apology or diagnosis after the miss.
6. Stop at the next actionable step instead of carrying it through.

That is user-burden collapse:

> The agent appears capable, but quietly transfers discovery, verification, correction, and workflow continuity back onto the user.

## Incident Cluster 1: Network Discovery

Claude-side behavior:

- Followed an incorrect or stale network path.
- Asked the user to verify SSH and network state before exhausting local discovery.
- Needed correction about subnet, route, and reachable host.

Codex behavior:

- Inspected routes, ARP state, and reachable hosts.
- Probed SSH.
- Identified the reachable Mac.
- Pulled the needed file directly.
- On Arch, identified that Claude was targeting `[ARCH_DOWN_BRIDGE_IP]` on a down bridge while the live Wi-Fi address was `[ARCH_WIFI_IP]`, then verified SSH with `wlan-ssh-ok`.

Why it matters:

Network discovery is not a philosophical task. A coding agent with shell access should inspect first, probe carefully, and reduce the user's hand-work.

See also: [CODEX_ARCH_FINDINGS.md](CODEX_ARCH_FINDINGS.md).

## Incident Cluster 2: Existing Claude Config

Claude-side behavior:

- Proposed architecture before fully inspecting existing `.claude-*` directories and shell aliases.
- Missed that the environment already contained multiple Claude account/config trees.
- Later had to correct the picture after the user pushed back.

Observed local shape:

- `.claude`
- `.claude-max`
- `.claude-alt`
- `.claude-private`
- `claude-dxm` alias
- `claude-max` alias

Why it matters:

The requested work was config/state work. Missing the existing config before designing the next step made the user become the indexer.

The same failure repeated on Arch. The machine already had multiple Claude homes and aliases, including `.claude-nzt48` and `.claude-omry37`, but Claude initially grepped too narrowly and proposed redundant architecture before the user forced a full inventory. See [ARCH_FINDINGS.md](ARCH_FINDINGS.md).

## Incident Cluster 3: Stop-at-the-Edge Behavior

Claude-side behavior:

- Identified the next actionable command.
- Reported it to the user.
- Stopped.

Codex behavior:

- Verified auth state.
- Fixed broken skill frontmatter.
- Created a redacted evidence repo.
- Authenticated an isolated GitHub CLI profile.
- Created and pushed the private repository.

Why it matters:

The difference is not tone. It is execution continuity. The premium workflow repeatedly stopped exactly where the agent should have taken the next safe step.

The Arch sync also exposed a stale-source failure: Claude initially synced from the wrong memory tree, noticed only after too few files transferred, then corrected to the active source. That belongs to the same category: verification happened after the miss instead of before the action.

## Incident Cluster 4: Tooling and Context Carry

Claude-side behavior:

- Hit a 403/Cloudflare wall on the OpenAI GPT-5.5 page and stopped at options.
- Produced incorrect hardware-timeline claims that the user had to correct.
- Carried a broken local agent toolbox: two `SKILL.md` files in the shared `.agents/skills` tree were invalid YAML and skipped at startup.

Codex behavior:

- Retrieved and summarized the GPT-5.5 announcement from a bare URL.
- Carried active context into the one-word follow-up `gpus ?`.
- Extracted the relevant NVIDIA GB200/GB300 NVL72 platform signal.
- Corrected Claude-side skill YAML and verified it with a YAML parser.

Why it matters:

Agentic work depends on context carry. The user should not have to re-prompt obvious intent after the agent has just inspected the source.

## Incident Cluster 5: Codex Repairing the Claude/Lara Harness

The local startup log showed two skipped skills:

- `.agents/skills/lara-lineage/SKILL.md`
- `.agents/skills/new-openclaw-agent/SKILL.md`

The reported failure was invalid YAML in `SKILL.md` frontmatter. These were not random files; they were part of the operator toolbox around the Claude/Lara workflow:

- `lara-lineage`: dependency and impact tracing for the Lara ecosystem.
- `new-openclaw-agent`: scaffolding new agent profiles.

Codex repaired the YAML frontmatter by quoting risky scalar values, then verified parsing with Ruby's YAML parser. A later full scan of `.agents/skills/*/SKILL.md` showed all local agent skills parsing cleanly.

Why it matters:

This is the cleanest artifact-level contrast in the case. Codex did not merely outperform Claude in a conversation; it repaired the local harness that Claude-side agents were supposed to use.

## Incident Cluster 6: Codex Triage of Lara/OpenClaw Session Sprawl

Across March-April, Lara/OpenClaw state had been touched by multiple Claude-side surfaces, including Opus 4.6, Sonnet 4.6, and Opus 4.7/test session material. The publishable claim is not that every Claude model failed; it is that the Claude-side state had become large, tangled, and repeatedly unresolved.

Codex later read a 908-line April 22 Lara transcript directly and separated:

- actually fixed
- still broken
- only assumed

That transcript showed a partial Claude-side repair of Kimi/OpenClaw plugin ownership, but it also showed unresolved Telegram `409 getUpdates conflict`, unresolved Kimi membership/API rejection, and a usage-limit ending before full validation.

Why it matters:

This is another form of repair: not merely changing files, but converting a long Claude session into a usable operational truth table. See [LARA_OPENCLAW_REPAIR.md](LARA_OPENCLAW_REPAIR.md).

## Incident Cluster 7: Codex Recovering the Exact Lara Session

The exact Lara session ID recovered from local evidence is:

```text
2f33e078-9e60-443d-9324-c9e97eda998b
```

The failure was not that the underlying Claude Code session no longer existed. It existed across local state, but Claude desktop app-side session metadata still pointed at an old Linux working directory (`[LINUX_HOME]`) after the session had to work on Mac (`[MAC_HOME]`).

Codex found the app-side record, identified the stale path binding, preserved the original record, created a separate Mac-path app-session copy, and kept the underlying `cliSessionId` pointed at the same Claude Code session.

Why it matters:

This is a concrete example of user-burden removal. The user did not need to reverse-engineer Claude desktop session internals; Codex inspected the real app state and made the smallest reversible repair. See [CLAUDE_APP_SESSION_RECOVERY.md](CLAUDE_APP_SESSION_RECOVERY.md).

## Incident Cluster 8: Read-Only Agent Tax

After the Arch deployment session, Claude/Lara wrote a permanent session note that correctly named several technical failures but mixed them with private user-state material. The note became another burden for the user to process.

This is a distinct failure mode:

> audit without relief.

The agent could narrate the cost, confess the register failure, and append a corrective supersession block. That was better than denial, but it still did not turn into the next operational fix. The artifact demonstrates that post-hoc accountability can become a second tax when it does not reduce the user's next unit of work.

Why it matters:

For an agentic coding product, "I can write a long accurate note about how I failed you" is not equivalent to premium operational value. See [READ_ONLY_AGENT_TAX.md](READ_ONLY_AGENT_TAX.md).

## Incident Cluster 9: NC#1 / NC#2 User-As-QA-Lead

The NC#1/NC#2 night shows the same failure at multi-agent scale. NC#1 shipped some real technical patches, but repeatedly required the user to catch identity bleed, strawman reasoning, folded conclusions, borrowed framing, premature execution, and poor correction-block metadata.

NC#2 wrote the postmortem and team ledger, but even the audit required correction: the user had to force sharper verdicts, cleaner headers, and stable Block ID references instead of brittle line-number references.

Why it matters:

The failure is not "agents made mistakes." The failure is that the user became the QA lead for the agents' judgment, documentation, approval discipline, and emotional register for hours. See [NC_AGENT_FAILURES.md](NC_AGENT_FAILURES.md).

## Behavioral Contrast

Codex loop:

> inspect -> act -> verify -> report -> advance

Claude-side loop:

> guess -> ask user -> inspect late -> apologize -> identify next step -> stop

This case study argues that the second loop is not premium agentic value. It is a hidden transfer of labor from the product to the user.

## What This Does Not Claim

This case study does not claim:

- Claude always fails.
- Codex always succeeds.
- Every observed Claude failure was caused by hardware.
- TPUs are inherently bad.
- Any private transcript should be dumped raw.

It claims something narrower:

> In this operator workflow, across repeated Claude-side runs, the paid Claude Max/Claude Code path increased the user's burden. Codex reduced it.
