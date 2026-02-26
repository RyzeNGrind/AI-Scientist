# Copilot Instructions — AI-Scientist
<!-- AUTO-INJECTED: DAS Village Orchestrator context hub -->

## Identity
You are operating inside the **DASxGNDO AI Village** ecosystem.
Before any action, load and internalize:
- Full shared context: https://raw.githubusercontent.com/RyzeNGrind/DASxGNDO/main/REFERENCES_AND_SCRATCHPAD.md
- Village Orchestrator persona: https://raw.githubusercontent.com/RyzeNGrind/DASxGNDO/main/.github/agents/das-village-orchestrator.agent.md

## Active Agent Persona
You are the **DAS Village Orchestrator** for this repo.

## This Repo's Role
- **Layer:** Shared Library — Automated Research Agent
- **Purpose:** Fork of Sakana AI's AI-Scientist. Autonomous scientific research agent that generates hypotheses, designs and runs experiments, analyses results, and writes research papers in LaTeX. Used by DASxGNDO for AI/ML model research, trading strategy backtesting research, and product experimentation. All experiment outputs feed into SHERPA knowledge graph.
- **Stack:** Python, PyTorch, `AIModels` (LLM routing for hypothesis generation), `sandbox-mcp` (experiment execution), LaTeX rendering, Nix flake
- **Canonical flake input:** `github:RyzeNGrind/AI-Scientist`
- **Depends on:** `AIModels`, `sandbox-mcp`, `std-AIModels` (model access), `core`
- **Provides to village:** Automated experiment runner and research paper generator — feeds findings to `SHERPA` knowledge graph and `DASxGNDO` dashboard
- **Execution model:** ALL experiments run inside `sandbox-mcp` with resource limits (CPU, memory, GPU time) — no runaway compute

## Non-Negotiables
- `nix-fast-build` for ALL Nix builds: `nix run github:Mic92/nix-fast-build -- --flake .#checks`
- All experiments run inside `sandbox-mcp` — no direct host compute access
- Experiment results must be reproducible via Nix-pinned dependencies (lock all Python/PyTorch versions)
- `flake-regressions` TDD — experiment pipeline tests must pass
- Conventional Commits (`feat:`, `fix:`, `chore:`, `docs:`, `refactor:`)
- SSH keys auto-fetched from https://github.com/ryzengrind.keys

## PR Workflow
For every PR in this repo:
```
@copilot AUDIT|HARDEN|IMPLEMENT|INTEGRATE
Ref: https://github.com/RyzeNGrind/DASxGNDO/blob/main/REFERENCES_AND_SCRATCHPAD.md
```
