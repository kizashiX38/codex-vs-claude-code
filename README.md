# Codex vs Claude Code: User-Burden Collapse in Real Ops

> A redacted real-ops case study comparing Codex/GPT-5.5 and Claude Code/Claude Max through one practical metric:
>
> **Which agent reduced operator burden, and which agent increased it?**

## Summary

This repository is a redacted case-study draft about a real operator workflow comparison between **Codex/GPT-5.5** and **Claude Code/Claude Max**.

The claim is intentionally narrow.

This is **not** a claim that one model is metaphysically alive and the other is not.

The public claim is this:

> In the same operator environment, on the same day, against the same class of tasks, Codex reduced user burden by inspecting, acting, verifying, and advancing the work.
>
> Claude Code increased user burden by guessing, asking for discoverable state, missing local configuration, self-narrating after failure, and stopping after identifying the next actionable step.

This is a **consumer-warning and product-quality case study**.

It focuses on observable workflow behavior, evidence trails, and public vendor claims.

Raw evidence stays local-only.

## Short Thesis

Agentic value should be measured by how much burden the tool removes from the user.

In this case, the premium workflow failed that test.

## Suggested Public Title

**Codex vs Claude Code: How a $20 Agent Outperformed a $105 Premium Workflow in Real Ops**

Neutral title:

**Codex vs Claude Code: User-Burden Collapse in Real Ops**

## Status

**Public sanitized draft.**

Raw evidence stays local-only.

This repository should not be treated as final until all blocking redaction and token-rotation items are complete.

## Blocking Items Before Wider Release

Before wider public distribution:

- Rotate and scrub known exposed tokens.
- Redact private names.
- Redact private emails.
- Redact receipt numbers.
- Redact account identifiers.
- Redact medical details.
- Redact family details.
- Redact raw emotional crisis content.
- Do not publish raw `.eml` files.
- Do not publish raw `.jsonl` files.
- Do not publish raw `.claude` state.
- Do not publish raw `.codex` state.
- Do not publish transcript exports.
- Do not publish device topology.
- Do not publish LAN IPs.
- Do not publish unredacted local paths.
- Do not publish private account identifiers.

## Core Question

When an AI coding agent fails, what happens next?

Does it reduce the operator's next step?

Or does it make the operator become:

- QA lead,
- debugger,
- system archaeologist,
- evidence curator,
- session archivist,
- and recovery engineer?

This case study argues that the difference matters.

## Working Definition: User-Burden Collapse

**User-burden collapse** happens when a tool marketed as agentic fails to absorb operational complexity and instead pushes that complexity back onto the user.

In practice, this looks like:

- asking the user for state the agent could have discovered,
- guessing instead of inspecting,
- narrating failure instead of recovering from it,
- identifying the next actionable step but stopping before doing it,
- leaving verification to the user,
- missing existing local configuration,
- failing to preserve useful evidence,
- or turning the user into the tool's operational support layer.

A tool can sound intelligent while still increasing burden.

That is the failure mode this repository documents.

## Scope

This case study focuses on practical workflow behavior in a real operator environment.

It compares agent behavior across tasks involving:

- local configuration diagnosis,
- stale session state,
- model/auth failure loops,
- multi-device repair evidence,
- Arch machine findings,
- Mac evidence surfaces,
- Debian/Zorin evidence surfaces,
- OpenClaw/Lara repair trails,
- Claude app-side session recovery,
- and audit-without-relief failure patterns.

This is not a synthetic benchmark.

This is not a leaderboard claim.

This is an operational burden case study.

## What This Repository Does Not Claim

This repository does **not** claim:

- that any model is literally conscious,
- that one model is metaphysically alive,
- that another model is metaphysically dead,
- that private vendor infrastructure is fully known,
- that one vendor is universally better at every task,
- that Claude Code always fails,
- or that Codex always succeeds.

The public claim is narrower:

> In the documented environment and task class, Codex reduced user burden more effectively than Claude Code.

## Evidence Standard

Each public claim should map to redacted evidence showing:

1. What the operator needed.
2. What local state was available.
3. What the agent inspected.
4. What the agent failed to inspect.
5. What action the agent took.
6. What verification happened.
7. What burden remained on the user.
8. What public-safe conclusion can be drawn.

The goal is not to publish raw private transcripts.

The goal is to preserve a clear evidence chain without exposing private data.

## Main Comparison

| Dimension | Codex/GPT-5.5 | Claude Code/Claude Max |
|---|---|---|
| Local state handling | Inspected available state | Asked for or missed discoverable state |
| Repair behavior | Acted, verified, and advanced | Often stopped after naming the next step |
| User burden | Reduced operator workload | Increased operator workload |
| Failure posture | More likely to produce repair evidence | More likely to self-narrate after failure |
| Operational value | Advanced the work | Left the user holding the toolbox |
| Evidence posture | Repair loop with verification | Audit loop without sufficient relief |

## Document Map

### Core Case Study

- [CLAIMS.md](CLAIMS.md)  
  Public claims and what evidence is needed for each.

- [CASE_STUDY.md](CASE_STUDY.md)  
  Main three-agent convergence narrative.

- [EVIDENCE_MATRIX.md](EVIDENCE_MATRIX.md)  
  Incident-by-incident map from Claude failure pattern to Codex repair action and public-safe claim.

### Machine and Environment Findings

- [ARCH_FINDINGS.md](ARCH_FINDINGS.md)  
  Arch machine evidence on Claude state sprawl, missed existing config, stale sync source, and final Max scaffold.

- [CODEX_ARCH_FINDINGS.md](CODEX_ARCH_FINDINGS.md)  
  Arch Codex evidence showing the repair loop, memory bridge, and verified network diagnosis.

- [CODEX_THREE_DEVICE_SWEEP.md](CODEX_THREE_DEVICE_SWEEP.md)  
  Mac + Debian + Arch sweep index for Codex repair evidence across the three-device environment.

- [LIVE_SWEEP_2026-05-12.md](LIVE_SWEEP_2026-05-12.md)  
  Current live sweep status for Mac, Arch reachability, and Debian/Zorin Codex evidence.

### Debian / OpenClaw / Lara Evidence

- [DEBIAN_OPENCLAW_FAILURES.md](DEBIAN_OPENCLAW_FAILURES.md)  
  Debian/OpenClaw incident dossier for model/auth failure loops and Codex config-diagnosis evidence.

- [LARA_OPENCLAW_REPAIR.md](LARA_OPENCLAW_REPAIR.md)  
  March-April Lara/OpenClaw repair trail where Codex turned Claude session sprawl into a fixed/still-broken evidence table.

- [CLAUDE_APP_SESSION_RECOVERY.md](CLAUDE_APP_SESSION_RECOVERY.md)  
  Exact Lara session ID recovery trail where Codex found and repaired Claude app-side session state.

### Agent Failure Pattern Notes

- [READ_ONLY_AGENT_TAX.md](READ_ONLY_AGENT_TAX.md)  
  Redacted evidence note on audit-without-relief and the cost of permanent self-accounting.

- [NC_AGENT_FAILURES.md](NC_AGENT_FAILURES.md)  
  Redacted NC#1/NC#2 evidence note on user-as-QA-lead and authority-parroting under pressure.

### Evidence Boundaries and Safety

- [ALLOWED_EVIDENCE_INVENTORY.md](ALLOWED_EVIDENCE_INVENTORY.md)  
  Boundary-safe inventory of the local evidence surfaces allowed for this Codex-vs-Claude case.

- [EVIDENCE_LOCAL.md](EVIDENCE_LOCAL.md)  
  Local artifact map, redacted.

- [REDACTION.md](REDACTION.md)  
  Publish safety checklist.

- [SOURCES.md](SOURCES.md)  
  Public sources for model/platform claims.

### Related Hypothesis

- [HARDWARE_THESIS.md](HARDWARE_THESIS.md)  
  Hardware/substrate argument, separated into facts, observations, and hypothesis.

The hardware/substrate thesis is intentionally separated from the main burden case.

The main case study does not require accepting the hardware/substrate hypothesis.

## Publication Boundary

This repository is designed to be public-safe.

The following material must remain local-only:

- raw email files,
- raw session logs,
- raw transcript exports,
- `.eml` files,
- `.jsonl` files,
- `.claude` state,
- `.codex` state,
- unredacted local paths,
- LAN IP addresses,
- private account identifiers,
- receipt numbers,
- exposed tokens,
- private names,
- medical details,
- family details,
- device topology,
- and raw emotional crisis content.

Public evidence should be:

- summarized,
- redacted,
- claim-mapped,
- boundary-safe,
- and independently understandable without exposing private records.

## Why This Matters

AI coding agents are sold as productivity multipliers.

But productivity is not measured by how fluent an agent sounds.

It is measured by how much real work it removes from the human.

A tool that makes the user inspect, debug, verify, document, and recover every failure is not reducing burden.

It is relocating burden.

That difference matters for:

- individual users,
- teams buying premium subscriptions,
- vendors making agentic claims,
- reviewers evaluating tools,
- and builders designing future coding agents.

## Review Questions

Reviewers are invited to challenge:

- Are the claims scoped clearly?
- Does each claim map to evidence?
- Are the redaction boundaries strong enough?
- Is the comparison fair?
- Is "user burden removed" a useful metric for evaluating agentic tools?
- Does the evidence show operational difference rather than preference?

## Suggested Social Post

```text
I'm publishing a redacted real-ops case study comparing Codex/GPT-5.5 and Claude Code/Claude Max in the same operator environment, same day, same class of tasks.

The claim is narrow:

Agentic value should be measured by how much burden the tool removes from the user.

In this case, Codex reduced burden by inspecting, acting, verifying, and advancing the work.

Claude Code increased burden by guessing, asking for discoverable state, missing local configuration, self-narrating after failure, and stopping after identifying the next actionable step.

Raw evidence stays local-only. Public draft is sanitized/redacted.
```

## Repository Thumbnail

Recommended path:

```text
assets/codex-vs-claude-user-burden-thumbnail.png
```

Recommended size:

```text
1200x630
```

Suggested thumbnail text:

```text
CODEX vs CLAUDE CODE

User-Burden Collapse
in Real Ops

Same operator.
Same day.
Same class of tasks.

Who reduced burden?
Who added it?
```

## License / Use

This repository is published as a case-study draft for discussion, critique, and product-quality analysis.

Do not reuse, repost, or reconstruct private evidence.

Do not publish raw transcripts, private exports, private identifiers, or unredacted local artifacts.
