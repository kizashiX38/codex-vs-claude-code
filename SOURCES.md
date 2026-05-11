# Public Sources

Use public sources for model and hardware claims. Do not rely only on memory or transcript assertions.

## OpenAI: GPT-5.5

Source:

- https://openai.com/index/introducing-gpt-5-5/

Relevant public claims:

- GPT-5.5 is positioned for real work: coding, research, data, documents, spreadsheets, software operation, tool use, and long-running tasks.
- The announcement states GPT-5.5 was built and served on NVIDIA GB200 NVL72 systems.
- Other localized OpenAI pages and the same announcement state GPT-5.5 was co-designed/trained/served with NVIDIA GB200 and GB300 NVL72 systems.
- GPT-5.5 API pricing is listed at $5 per 1M input tokens and $30 per 1M output tokens.
- GPT-5.5 Pro API pricing is listed at $30 per 1M input tokens and $180 per 1M output tokens.
- Public eval table includes:
  - Terminal-Bench 2.0: GPT-5.5 at 82.7%, GPT-5.4 at 75.1%, Claude Opus 4.7 at 69.4%.
  - SWE-Bench Pro: GPT-5.5 at 58.6%, GPT-5.4 at 57.7%, Claude Opus 4.7 at 64.3%.
  - BrowseComp: GPT-5.5 at 84.4%, GPT-5.4 at 82.7%, Claude Opus 4.7 at 79.3%.

Use carefully:

- Do not cherry-pick only wins. The same OpenAI table shows Claude Opus 4.7 ahead on some metrics, including SWE-Bench Pro and some long-context subtests.
- The behavioral case is stronger than benchmark-only framing.

## OpenAI: GPT-5.4

Source:

- https://openai.com/index/introducing-gpt-5-4/

Relevant public claims:

- GPT-5.4 released in ChatGPT, API, and Codex.
- GPT-5.4 brought GPT-5.3-Codex coding capabilities into a general frontier model.
- GPT-5.4 supports up to 1M tokens in API/Codex contexts and improves tool use, web search, computer use, and token efficiency compared with GPT-5.2.
- GPT-5.4 pricing listed higher than GPT-5.2, with efficiency improvements as the offset.
- GPT-5.4 standard pricing is publicly listed around $2.50 per 1M input tokens and $15 per 1M output tokens.
- GPT-5.4 Pro pricing is publicly listed at $30 per 1M input tokens and $180 per 1M output tokens.

## OpenAI: GPT-5.2-Codex

Source:

- https://openai.com/index/introducing-gpt-5-2-codex/

Relevant public claims:

- GPT-5.2-Codex is optimized for agentic coding in Codex.
- It builds on GPT-5.2 professional work and GPT-5.1-Codex-Max terminal/coding capabilities.
- OpenAI highlights long-context understanding, tool calling, factuality, native compaction, and long-running coding tasks.
- OpenAI pricing lists GPT-5.2 at $1.75 per 1M input tokens and $14 per 1M output tokens.

## OpenAI: GPT-5.1 / GPT-5.1-Codex-Max

Sources:

- https://openai.com/index/gpt-5-1-for-developers/
- https://openai.com/index/gpt-5-1-codex-max/

Relevant public claims:

- GPT-5.1 improved coding personality, less overthinking, better code quality, better preambles during tool-call sequences, and frontend designs.
- GPT-5.1-Codex-Max was trained on real-world software-engineering tasks such as PR creation, code review, frontend coding, and Q&A.
- GPT-5.1-Codex-Max improved collaboration inside the Codex CLI.

## Anthropic: Compute / TPUs / Trainium / NVIDIA GPUs

Sources:

- https://www.anthropic.com/engineering/a-postmortem-of-three-recent-issues
- https://blog.google/innovation-and-ai/infrastructure-and-cloud/google-cloud/eighth-generation-tpu-agentic-era/
- https://www.anthropic.com/news/expanding-our-use-of-google-cloud-tpus-and-services
- https://www.anthropic.com/news/google-broadcom-partnership-compute
- https://www.anthropic.com/news/anthropic-amazon-compute
- https://www.anthropic.com/news/microsoft-nvidia-anthropic-announce-strategic-partnerships

Relevant public claims:

- On Sep 17, 2025, Anthropic published a postmortem saying three infrastructure bugs intermittently degraded Claude response quality between August and early September 2025.
- The Sep 17 postmortem identifies an XLA:TPU compiler bug affecting requests to Claude Haiku 3.5, and incorrect routing affecting a small share of Google Cloud Vertex AI requests between Aug 27 and Sep 16.
- On Apr 22/23, 2026, Google publicly announced TPU 8t and TPU 8i: separate purpose-built TPU architectures for training and inference in the agentic era.
- Google's TPU 8 post says TPU 8t is for massive training workloads and TPU 8i is designed for latency-sensitive inference workloads.
- Anthropic says its compute strategy uses Google TPUs, AWS Trainium, and NVIDIA GPUs.
- Anthropic announced an expansion of Google Cloud TPUs worth tens of billions of dollars, with up to one million TPUs and well over a gigawatt of capacity expected in 2026.
- Anthropic announced a Google/Broadcom agreement for multiple gigawatts of next-generation TPU capacity starting in 2027.
- Anthropic announced up to 5GW of Amazon capacity for training and deploying Claude, including Trainium2 and Trainium3 capacity.
- Anthropic also announced NVIDIA/Azure partnerships and future NVIDIA architecture work.

Use carefully:

- Do not say Claude is "only TPU."
- Do not call AWS Trainium "Amazon TPU"; Trainium is AWS's custom ML accelerator stack, while TPU is Google's accelerator.
- Do not say TPU is new or immature. Google TPU dates back roughly 2013-2016.
- Do not claim the Sep 2025 postmortem proves a general "training on GPUs, inference on TPUs" routing policy unless a source directly says that.
- Safer public language: Anthropic publicly emphasizes a multi-chip strategy; OpenAI's GPT-5.5 announcement specifically foregrounds NVIDIA GB200/GB300 NVL72 systems. The user-experienced difference should be argued from workflow evidence, not hardware determinism alone.

## Social / Community Evidence

Sources:

- Reddit: https://www.reddit.com/r/Agent_AI/comments/1sthudi/google_unveils_two_new_tpus_designed_for_the/
- Reddit: https://www.reddit.com/r/ClaudeCode/comments/1ssg7pz/anthropic_is_starting_to_feel_just_as_offputting/

Relevant public claims:

- Reddit discussion on Apr 23 echoed the Google TPU 8t/8i training/inference split.
- Reddit discussion in Claude communities raised compute-shortage and pricing/limit concerns, including users saying they moved to Codex.

Use carefully:

- Reddit is evidence of community perception, not vendor admission.
- X/Twitter evidence still needs a direct URL or screenshot; web search did not return reliable indexed X results.
