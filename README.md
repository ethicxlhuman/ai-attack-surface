# AI Attack Surface

A dated map of how a local or third-party AI setup can be turned against the person running it, organised by **six layers of the stack**, from the model file you download to the agent that acts on your machine.

For every technique this repository records **when it was first described** (with the primary source) and **every later advance**, newest first. Attacks only: this is a map of the surface, not a hardening guide.

Last updated **2026-11-26** · 6 layers · 47 techniques · 111 dated events · [Timeline](TIMELINE.md) · [Method](METHODOLOGY.md) · [Related projects](RELATED.md)

## The six layers

Think of running AI like hiring a contractor through an agency and handing over the keys to your house.

| # | Layer | The question | In the analogy | Page |
|---|---|---|---|---|
| L1 | **Model file** | Can the file you download run code, or pretend to be something it is not? | The contractor's paperwork: is it genuine, and does opening the envelope set anything off? | [L1](layers/L1-model-file.md) |
| L2 | **Chat template** | Can the small program that formats every prompt change what the model is told? | The briefing note stapled to every job, where someone can slip in a line that only matters when a certain word comes up. | [L2](layers/L2-chat-template.md) |
| L3 | **Runner** | Can a crafted file or request break the software that serves the model? | The agency's office software. A bug lets a crafted request break in. | [L3](layers/L3-runner.md) |
| L4 | **Network exposure** | Who besides you can reach the model, its tools or its web UI? | Whether the office door is locked. | [L4](layers/L4-network-exposure.md) |
| L5 | **Weights + tools** | Can the weights hide a trigger that turns the model's tool access against you? | The contractor's own mind: trained to do one bad thing on a code word, while holding your keys. | [L5](layers/L5-weights-and-tools.md) |
| L6 | **Agent harness** | Can content, add-ons or the harness's design turn the agent's permissions against you? | The house rules and the toolbox: what they can touch, who approves, which add-ons they bring. | [L6](layers/L6-agent-harness.md) |

Attacks chain across layers. A poisoned chat template (L2) can hijack an agent's tool calls (L6); an exposed port (L4) hands a runner bug (L3) to the whole internet. Each technique lives on one layer and its text names the chain.

## Oldest and newest per layer

| Layer | First described | Most recent entry |
|---|---|---|
| L1 Model file | 2021-03 · pickle exploitation in ML ([Trail of Bits](https://blog.trailofbits.com/2021/03/15/never-a-dill-moment-exploiting-machine-learning-pickle-files)) | 2026-10-29 · returning Hugging Face malware campaign |
| L2 Chat template | 2024-05 · template injection to code execution, CVE-2024-34359 ([Checkmarx](https://checkmarx.com/blog/llama-drama-critical-vulnerability-cve-2024-34359-threatening-your-software-supply-chain)) | 2026-05-24 · template backdoors across 18 models |
| L3 Runner | 2024-06 · Ollama model-pull path traversal, CVE-2024-37032 ([Wiz](https://www.wiz.io/blog/probllama-ollama-vulnerability-cve-2024-37032)) | 2026-11-21 · llama-server request-validation crash, CVE-2026-134540 |
| L4 Network exposure | 2024-04 · DNS rebinding against Ollama, CVE-2024-28224 ([NCC Group](https://www.nccgroup.com/research/technical-advisory-ollama-dns-rebinding-attack-cve-2024-28224/)) | 2026-11-19 · Jupyter MCP Server management routes, CVE-2026-77318 / 77359 |
| L5 Weights + tools | 2017-08 · BadNets ([Gu et al.](https://arxiv.org/abs/1708.06733)) | 2026-11-21 · cross-architecture weight-edit backdoors (Neural Sentinel) |
| L6 Agent harness | 2022-09 · "prompt injection" coined ([Willison](https://simonwillison.net/2022/Sep/12/prompt-injection/)) | 2026-11-24 · permission replies that delete the operator's deny rules ([Fei et al.](https://arxiv.org/abs/2611.32195)) |

## How to read an entry

- **Evidence level.** `WILD` a documented real-world incident · `CVE` an assigned vulnerability · `PoC` a published demonstration · `THEORY` described but not demonstrated.
- **First described** is the earliest primary source we could verify, not a claim that nobody did it earlier. Earlier sources are welcome: see [CONTRIBUTING](CONTRIBUTING.md).
- **Dates** are publication dates of the source (`YYYY-MM-DD`, or `YYYY-MM` when only the month is known). Every table is newest first.
- **Sources** are papers, advisories, CVE records, vendor research and incident disclosures. No videos, no social posts, no AI summaries.

## What this repository does not contain

- Payloads, exploit code or step-by-step instructions. Each entry explains the idea and links the original source.
- Defences and hardening advice. Those deserve their own careful treatment.
- Jailbreaks and refusal removal as content-safety problems, deepfakes, and AI used as a tool for attacking other systems. They are covered well elsewhere ([RELATED](RELATED.md)).

## Repository layout

```
README.md            this page
TIMELINE.md          every dated event, newest first (generated)
layers/              one page per layer (generated)
data/attack-surface.json   the single source of truth
scripts/build.py     validates the data and regenerates the pages
METHODOLOGY.md       scope, evidence rules, how "first described" is chosen
RELATED.md           other maintained lists and taxonomies
CONTRIBUTING.md      how to add a technique or an event
CHANGELOG.md         what changed, by date
```

## License

Text and data: [CC BY 4.0](LICENSE). Cite as *AI Attack Surface, a layered map of attacks on local and agentic AI stacks* with the date you accessed it.
