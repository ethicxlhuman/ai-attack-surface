# Changelog

Newest first.

## 2026-11-26

- 2 new techniques: L3.11 inference-server request handling bugs (llama.cpp CVE-2026-134540; first event: Cyera's llama-server use-after-frees, 2026-08-07); L6.15 permission-reply policy rewrite (arXiv 2611.32195).
- New events: L3.06 one-hub CVE-2026-133875; L6.02 browser-use CVE-2026-136452 and secrets sent through an approved upload channel (arXiv 2611.31541); L6.03 widening "compatible" tool-schema updates (SchemaCaps, arXiv 2611.30750) and tool-provider misbinding (arXiv 2611.21577); L6.04 Amazon ECS MCP Server CVE-2026-135614 and capability laundering (ACaM, arXiv 2611.23507); L6.06 benign-author skill flaws across ClawHub (arXiv 2611.30932); L6.09 compaction summaries inserted as user messages (arXiv 2611.32194); L6.13 tool-call smuggling (arXiv 2611.30624).
- Renamed L6.04 to "Malicious or defective MCP server or package", L6.06 to "Malicious or vulnerable agent skills" and L6.13 to "Gate/executor parse differential" (now covers tool-call JSON as well as shell commands).
- Now 46 techniques, 108 dated events. Every new event checked against its paper, NVD record or GitHub issue on 2026-11-26.

## 2026-11-25

- 3 new techniques: L3.10 stale recovered state served across tenants (interrupted KV-cache load; arXiv 2611.29004); L6.13 gate/shell parse differential (ParseGap, arXiv 2611.29546); L6.14 information-gap disclosure with no injection (GapLeak, arXiv 2611.22223).
- New events: L5.05 Neural Sentinel cross-architecture weight edits (arXiv 2611.28543); L6.03 GRAFT argument-level tool-description poisoning (arXiv 2611.27041); L6.04 fake MCP config doctor npm package dropping an infostealer (Knostic); L6.09 AutoGPT CVE-2026-133448.
- Now 44 techniques, 95 dated events. Every new event checked against its paper, NVD record or vendor post on 2026-11-25.

## 2026-11-24

- 4 new techniques: L3.09 unauthenticated model/adapter loading endpoint (SGLang CVE-2026-127222); L4.06 management side door next to an authenticated MCP endpoint (Jupyter MCP Server CVE-2026-77318); L6.11 MCP OAuth discovery redirects client credentials (MCP Python SDK CVE-2026-115563); L6.12 tool-argument injection into shell or SQL backends (CVE-2026-129995, CVE-2026-130008, CVE-2026-134293).
- New events: L3.03 llama.cpp GGUF parser CVE-2026-133710 and CVE-2026-126974/126975/126976; L3.01 vLLM CVE-2026-130684; L4.03 k8s-mcp-server CVE-2026-130007 and sqlite-mcp default listener; L4.04 Jupyter MCP Server DNS rebinding CVE-2026-77359; L6.02 FlowIntel CVE-2026-133631.
- Renamed L3.01 to "Model path traversal" (now covers a config that redirects loading) and L4.04 to "DNS rebinding against a local model or MCP server".
- Now 41 techniques, 88 dated events. Every new event checked against its NVD, CVE.org or GitHub advisory record on 2026-11-24.

## 2026-11-21

- First version: six layers, 37 techniques, 75 dated events from 2017-08 to 2026-11-16.
