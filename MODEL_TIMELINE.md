# Model / Platform Timeline

This timeline captures the public-source backbone for the case study.

## September 2025: Claude Quality Degradation / TPU Compiler Evidence

Source:

- https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues

Verified:

- Anthropic published a postmortem on Sep 17, 2025.
- The postmortem says three infrastructure bugs intermittently degraded Claude response quality between August and early September 2025.
- It says an XLA:TPU compiler bug affected requests to Claude Haiku 3.5.
- It says incorrect routing affected some Google Cloud Vertex AI requests between Aug 27 and Sep 16.
- It says Anthropic does not intentionally reduce model quality due to demand, time of day, or server load.

Careful wording:

> Anthropic has publicly acknowledged that infrastructure bugs, including an XLA:TPU compiler bug, degraded some Claude responses in August/September 2025.

Do not claim from this source alone:

> Anthropic diverted training to GPUs and user inference to TPUs.

That may be your lived hypothesis, but this repo needs a direct source before making it a public factual claim.

## GPT-5.1 / GPT-5.1-Codex-Max

Sources:

- https://openai.com/index/gpt-5-1-for-developers/
- https://openai.com/index/gpt-5-1-codex-max/

Verified:

- GPT-5.1 improved coding personality, code quality, preambles during tool-call sequences, and frontend work.
- GPT-5.1-Codex-Max was trained on real-world software engineering tasks such as PR creation, code review, frontend coding, and Q&A.
- OpenAI says GPT-5.1-Codex-Max improved collaboration inside the Codex CLI.

Case-study angle:

> GPT-5.1/GPT-5.1-Codex-Max is the baseline for the user's "daily shipping" memory: a model family explicitly optimized for coding collaboration and terminal/agent workflows.

## GPT-5.2 / GPT-5.2-Codex

Source:

- https://openai.com/index/introducing-gpt-5-2-codex/

Verified:

- GPT-5.2-Codex was released in Codex surfaces for paid ChatGPT users.
- OpenAI says it was optimized for agentic coding.
- It builds on GPT-5.2 professional work and GPT-5.1-Codex-Max terminal/coding capabilities.
- OpenAI highlights long-context understanding, reliable tool calling, factuality, native compaction, token efficiency, and long-running coding tasks.

## GPT-5.4

Source:

- https://openai.com/index/introducing-gpt-5-4/

Verified:

- GPT-5.4 was released in ChatGPT, API, and Codex.
- OpenAI says GPT-5.4 brings GPT-5.3-Codex coding capabilities into a general frontier model.
- OpenAI says GPT-5.4 supports long-horizon agent work, larger tool ecosystems, improved web search, computer use, and up to 1M token context in Codex/API contexts.
- GPT-5.4 was framed as using fewer tokens than GPT-5.2 for many tasks, with faster workflows and lower total burden in tool-heavy settings.

## GPT-5.5

Source:

- https://openai.com/index/introducing-gpt-5-5/

Verified:

- GPT-5.5 is framed as a model for real work: code, research, data, documents, spreadsheets, computer use, tool use, and long-running tasks.
- OpenAI says GPT-5.5 can plan, use tools, check its work, navigate ambiguity, and keep going.
- OpenAI says GPT-5.5 was built and served on NVIDIA GB200 NVL72 systems; localized versions and snippets also state co-designed/trained/served with NVIDIA GB200 and GB300 NVL72 systems.
- OpenAI's public table lists GPT-5.5 above GPT-5.4 and Claude Opus 4.7 on Terminal-Bench 2.0 and BrowseComp, while Claude Opus 4.7 is ahead on SWE-Bench Pro.

Case-study angle:

> GPT-5.5/Codex is the comparison point because the user observed the operator loop directly: inspect, act, verify, report, with less manual correction.

## Anthropic Compute Position

Sources:

- https://blog.google/innovation-and-ai/infrastructure-and-cloud/google-cloud/eighth-generation-tpu-agentic-era/
- https://www.anthropic.com/news/expanding-our-use-of-google-cloud-tpus-and-services
- https://www.anthropic.com/news/google-broadcom-partnership-compute
- https://www.anthropic.com/news/anthropic-amazon-compute
- https://www.anthropic.com/news/microsoft-nvidia-anthropic-announce-strategic-partnerships

Verified:

- Anthropic publicly describes a diversified compute strategy across Google TPUs, AWS Trainium, and NVIDIA GPUs.
- Google publicly announced TPU 8t and TPU 8i at Cloud Next 2026, splitting its 8th generation TPU architecture into purpose-built training and inference chips.
- Google says TPU 8t targets massive training workloads, while TPU 8i targets latency-sensitive inference workloads needed for agents.
- Anthropic expanded Google TPU capacity in Oct 2025, with up to one million TPUs and well over a gigawatt expected in 2026.
- Anthropic expanded Google/Broadcom next-generation TPU capacity in Apr 2026, expected starting in 2027.
- Anthropic expanded Amazon Trainium capacity in Apr 2026.
- Anthropic also announced NVIDIA/Azure partnerships in Nov 2025.

Careful wording:

> Anthropic publicly emphasizes a multi-chip strategy, with major TPU and Trainium commitments. OpenAI's GPT-5.5 announcement specifically foregrounds NVIDIA GB200/GB300 NVL72 systems. The case study should use hardware as context, while grounding the main argument in observed workflow behavior.

## Apr 23, 2026: Social Trail

Verified from indexed web search:

- Reddit posts on Apr 23 discussed Google's TPU 8t/8i split into training and inference hardware.
- Claude community Reddit threads discussed compute limits, pricing, and users moving to Codex.

Not yet verified:

- X/Twitter posts. Need direct URLs or screenshots because indexed search did not surface reliable X results.

Careful wording:

> Public discussion around Apr 23 connected Google's training/inference TPU split with the broader AI compute race and Claude/Anthropic capacity concerns. This supports the case-study context, but vendor-source claims should still come from Google/Anthropic/OpenAI pages.
