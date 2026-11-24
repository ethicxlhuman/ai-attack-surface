# Changelog

Newest first.

## 2026-11-24

- 4 new techniques: L3.09 unauthenticated model/adapter loading endpoint (SGLang CVE-2026-127222); L4.06 management side door next to an authenticated MCP endpoint (Jupyter MCP Server CVE-2026-77318); L6.11 MCP OAuth discovery redirects client credentials (MCP Python SDK CVE-2026-115563); L6.12 tool-argument injection into shell or SQL backends (CVE-2026-129995, CVE-2026-130008, CVE-2026-134293).
- New events: L3.03 llama.cpp GGUF parser CVE-2026-133710 and CVE-2026-126974/126975/126976; L3.01 vLLM CVE-2026-130684; L4.03 k8s-mcp-server CVE-2026-130007 and sqlite-mcp default listener; L4.04 Jupyter MCP Server DNS rebinding CVE-2026-77359; L6.02 FlowIntel CVE-2026-133631.
- Renamed L3.01 to "Model path traversal" (now covers a config that redirects loading) and L4.04 to "DNS rebinding against a local model or MCP server".
- Now 41 techniques, 88 dated events. Every new event checked against its NVD, CVE.org or GitHub advisory record on 2026-11-24.

## 2026-11-21

- First version: six layers, 37 techniques, 75 dated events from 2017-08 to 2026-11-16.
