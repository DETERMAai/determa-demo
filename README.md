# DETERMA

## Deterministic Governed Execution for Autonomous AI

Modern AI systems can generate actions.
DETERMA focuses on governing whether those actions are allowed to mutate external systems.

This repository demonstrates a governed execution flow where:

- AI proposes mutations
- human approval is enforced
- execution authority is constrained
- replay attempts are blocked
- stale execution state is rejected
- mutation authority is revalidated at execution time

This is not an AI coding assistant.
This is an execution integrity system.

---

## Core Principle

```text
AI proposes.
Authority decides.
```

---

## Demo Highlights

The demo includes:

- Proposal-only AI worker
- WAITING_APPROVAL hard stop
- Single-use capability grants
- State witness verification
- Constrained patch executor
- Replay protection
- Append-only audit log
- Fail-closed execution semantics

---

## What The Demo Proves

The repository demonstrates:

✅ approved execution

✅ replay attempt blocking

✅ state drift / TOCTOU blocking

✅ immutable authority lineage

---

## Architectural Positioning

Most AI systems today follow this pattern:

```text
AI → API → System Mutation
```

DETERMA introduces an explicit authority layer:

```text
AI → Authority → Capability → Verification → Constrained Execution
```

---

## Current Scope

This repository demonstrates a governed execution kernel.
It does not yet claim:

- full multi-system authority coverage
- distributed authority federation
- production-scale infrastructure guarantees

The focus is deterministic mutation control under constrained conditions.
