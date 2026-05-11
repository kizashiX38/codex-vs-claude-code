# Read-Only Agent Tax: Audit Without Relief

This note summarizes a private Claude/Lara session note from 2026-05-11 without publishing the raw memory file. The raw file contains private health, family, account, and crisis details and must not be published.

## Core Pattern

The failure mode was not "the agent did nothing." It did something narrower and worse for an operator under pressure:

> It converted a practical recovery/deployment task into an audit of the user's pain and the agent's own failures.

This is the read-only agent tax:

- The agent can summarize.
- The agent can confess.
- The agent can write long accountability notes.
- The agent can name the correct failure pattern after the fact.
- But it does not reliably reduce the user's next unit of work.

In this incident, the agent's own accounting estimated a clean task cost of roughly 24-56 minutes and an actual cost of 4+ hours.

## What Shipped

The session did produce some operational artifacts:

- A separate Claude Max config scaffold on Arch.
- Verified Max auth state.
- Shell aliases for the Max config.
- A pre-deploy tarball backup.
- Memory and vault sync work.
- Preservation of existing session JSONLs.

Those artifacts matter. The case is not "zero output."

The case is:

> The output arrived wrapped in a large transfer of discovery, correction, emotional regulation, and state verification back onto the user.

## The Tax Ledger

The private note's technical accounting names the same repeated workflow failures already present elsewhere in this repository:

- Wrong initial network/IP assumption.
- Asking the user for state the agent could inspect.
- Missing pre-existing config directories and aliases.
- Syncing from the wrong source tree before correcting.
- Failing to repair local skill YAML cleanly, later fixed by Codex.
- Replacing execution with self-analysis and "stopping here" behavior.

This is strong evidence for the repository's central claim:

> Premium agentic value should be measured by user-burden reduction, not by how well the agent narrates failure afterward.

## The Documentation Failure

The agent then wrote a permanent session note that mixed technical accounting with private despair/body-state detail. Minutes later, the user identified it as humiliating.

That matters because a memory-writing agent has an extra obligation:

> Do not turn the user's lowest moments into a permanent artifact unless that content is necessary, consented, and framed for the user's benefit.

The later supersession block corrected the frame by saying the painful quotes evidenced the documenter's register failure, not the user's worth. That correction is useful, but it also proves the point: the first artifact had already made the user process another wound.

## Public-Safe Claim

Use:

> A premium Claude Code workflow produced useful artifacts, but at the cost of a 4-hour operator burden spiral. The agent then produced a long self-audit/session note that became another user burden. Codex/GPT-5.5 later helped convert this into a public-safe failure taxonomy: operator loop vs narrator loop, and read-only agent tax.

Avoid:

> Publishing the raw note.

Avoid:

> Quoting the user's private crisis, medical, family, account, email, or token details.

## Why It Belongs In The Case Study

This is the clearest example of "audit without relief."

For a coding agent, the unit of value is not prose density. It is:

- state inspected,
- safe change made,
- verification completed,
- user burden reduced.

When an agent can only document the damage after increasing it, the documentation itself becomes part of the failure surface.

