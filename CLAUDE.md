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

## Data-First Protocol
When answering questions about data, facts, documents, conversations, or history:
1. **Query the vector DB first.** Use `devctl search "query"` or direct Qdrant search before answering from memory or general knowledge. The DB has 2M+ vectors across legal docs, chats, sessions, and facts.
2. **Cite the source.** Include collection name, confidence level, and date when referencing DB results.
3. **Distinguish confidence levels.** A bank statement (verified) is not the same as an email claim (asserted). Never present asserted facts as verified.
4. **Log new facts.** When you discover or confirm a fact during work, log it: `devctl log-fact --fact "..." --source-type X --confidence Y --domain Z`

## Agent rules
- Do not commit .env or secret files
- This is a fork — preserve upstream compatibility where possible
- See `DECISIONS.md` for architectural choices
- 27 source files with minimal dependencies — keep it lean
