# MCP Knowledge-Sharing Session Notes

## What is MCP?

The Model Context Protocol (MCP) is an open standard and open-source framework introduced by Anthropic in November 2024 to standardize the way artificial intelligence (AI) systems like large language models (LLMs) integrate and share data with external tools, systems, and data sources. MCP provides a standardized interface for reading files, executing functions, and handling contextual prompts. Following its announcement, the protocol was adopted by major AI providers, including OpenAI and Google DeepMind. In December 2025, Anthropic donated MCP to the Agentic AI Foundation, a fund under the Linux Foundation.

Source: [Model Context Protocol — Wikipedia](https://en.wikipedia.org/wiki/Model_Context_Protocol)

## Reading List

Three shortlisted papers from a recent arXiv survey of work on the Model Context Protocol:

1. **[Understanding the Hierarchical Structure and Functional Landscape of the Model Context Protocol Ecosystem](https://arxiv.org/abs/2610.05319)** — Tang, Chen & Xiao (Oct 2026). A large-scale, tool-level map of the MCP ecosystem ("MCPacific"): 368,754 server listings covering 124,267 unique servers across 17 marketplaces, organized into a hierarchical taxonomy of 58,915 capabilities. Great for grounding discussion on what the ecosystem actually looks like and how to pick between functionally equivalent tools.

2. **[COPEX: Benchmarking LLM Robustness to Adversarial Context Across Model Context Protocol (MCP) Layers](https://arxiv.org/abs/2610.04378)** — Birhan et al. (Oct 2026). A controlled benchmark isolating the model as an MCP client across 25 attack types and 125 scenarios, spanning model/agent, client, server/tool, and transport surfaces. Mean attack success rate of 64.4% — useful for the security portion of the session.

3. **[Bridging LLM Agents and Data Spaces: An Architectural Mediation Approach using the Model Context Protocol](https://arxiv.org/abs/2609.30341)** — Ruiz et al. (Sep 2026). An architectural mediation layer (the Eunomia Agent) that exposes governed data-space capabilities to LLM agents as structured MCP tools while preserving governance constraints. A good enterprise-integration example.

## Live Demo — Kubernetes Deployment

The demo runs in the dev cluster:

| Field | Value |
|---|---|
| Namespace | `mcp-demo` |
| Deployment | `mcp-demo-web` |
| Image | `nginx` |
| Final replica count | 3 |

The deployment was created with a single replica and then scaled to one replica per shortlisted paper (3 papers → 3 replicas). All 3 replicas are available and ready.
