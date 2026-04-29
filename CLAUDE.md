# open-multi-agent-fork

> Read `INTENT.md` before acting. It governs all work in this repo.

## Overview
Production-grade multi-agent orchestration framework. Supports auto task decomposition, team collaboration, and dependency scheduling. Model-agnostic (Claude, GPT, Ollama). Runs in single Node.js process.

## Language & Stack
- Primary: TypeScript
- Runtime: Node.js
- Key files: `src/`, `examples/`, `DECISIONS.md`

## Session Start Protocol
If Qdrant is available (localhost:6333), query `feedback_events` and `fact_registry` for context before producing output.

## Agent rules
- Do not commit .env or secret files
- This is a fork — preserve upstream compatibility where possible
- See `DECISIONS.md` for architectural choices
- 27 source files with minimal dependencies — keep it lean
