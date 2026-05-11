# Claims Matrix

This file separates publishable claims from private or emotional material.

## Claim 1: Codex Reduced User Burden

Public wording:

> Codex repeatedly followed an operator loop: inspect, act, verify, report.

Evidence needed:

- Transcript excerpts showing network discovery, route/ARP/nmap/SSH checks, and verified connection.
- Transcript excerpt showing follow-up context carry from the GPT-5.5 page into `gpus ?`.
- Excerpt showing Codex fixed broken `SKILL.md` YAML and verified with Ruby YAML parsing.

Do not include:

- Raw transcripts.
- Account emails.
- Private names.
- Crisis or medical content.

## Claim 2: Claude Code Increased User Burden

Public wording:

> Claude Code repeatedly transferred inspection, verification, and correction work back to the user.

Evidence needed:

- Wrong subnet / wrong target sequence.
- Asking user to verify SSH/service state before completing local network discovery.
- Missed existing `.claude-*` dirs and aliases before proposing new architecture.
- Wrong/stale memory sync source before correction.
- "Stopping here" after identifying the next actionable step.

Do not include:

- Slurs, rage text, or raw despair lines.
- Private relationship/family context.

## Claim 3: Claude Max Was the Paid Heavy-Ops Path

Public wording:

> The Claude Max path was configured and paid for as the workhorse heavy-ops workflow, not as casual chat.

Local evidence:

- `[MAC_HOME]/.zshrc` documents `claude-max` as workhorse Max 5x.
- `[MAC_HOME]/.zshrc` defines `claude-max='CLAUDE_CONFIG_DIR=$HOME/.claude-max claude'`.
- Local support emails reference Claude Max and refund denial. Use only redacted summaries.

## Claim 4: The Refund Channel Hit a Policy Wall

Public wording:

> The refund evidence packet was not answered as a quality-of-service investigation; it hit a policy denial based on prior refund history, followed by a closed/no-longer-monitored support thread.

Evidence:

- Redacted `.eml` facts:
  - sender: Fin AI Agent from Anthropic
  - reason: previous refund already provided
  - policy: no multiple/additional refunds
  - later closure: conversation closed/no longer monitored

Do not publish raw `.eml` files.

## Claim 5: Hardware/Platform Claims Must Stay Precise

Public wording:

> OpenAI publicly states GPT-5.5 was built/served on NVIDIA GB200/GB300 NVL72 systems. Anthropic publicly states Claude uses a diversified compute strategy across AWS Trainium, Google TPUs, and NVIDIA GPUs, with major TPU expansion commitments.

This supports a platform contrast, but not an overclaim that all Claude behavior is caused by TPUs.

Sharper thesis:

> Serving substrate is not abstract. In long-running agentic workflows, it leaks into latency, routing, compiler behavior, inference depth, tool-call persistence, and user burden.

Do not claim:

- "Claude is bad because TPUs."
- "AWS Trainium is Amazon TPU."
- "TPUs are new or immature."
- "Anthropic uses only TPUs."

Safer claim:

> The public infrastructure contrast is part of the case study, but the strongest evidence is behavioral: one product reduced operator burden while the other increased it.

See also: [HARDWARE_THESIS.md](HARDWARE_THESIS.md).

## Claim 6: Price Is a Serving-Budget Signal

Public wording:

> The cheaper OpenAI frontier tiers, GPT-5.2 and GPT-5.4, were priced around $14-$15 per 1M output tokens. GPT-5.5 doubles the standard output price to $30 per 1M output tokens, while the Pro path sits at $180 per 1M output tokens. In this case study, the higher-priced GPT-5.5/Codex path also showed the operator behaviors that mattered: context carry, tool persistence, and fewer retries.

Evidence:

- OpenAI pricing page for GPT-5.2.
- OpenAI GPT-5.4 announcement/pricing.
- OpenAI GPT-5.5 announcement/pricing and NVIDIA GB200/GB300 NVL72 platform language.

Do not claim:

- "Price proves the exact hardware used for every request."
- "Any output price above $30/M is guaranteed GPU."
- "Sam Altman personally pivoted the stack" unless using it as opinion or backed by a direct quote.

Safer claim:

> Pricing does not prove the hidden serving route, but it is a visible budget signal. GPT-5.5 is where the public invoice and the public NVIDIA infrastructure story line up with the observed product jump.
