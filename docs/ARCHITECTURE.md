# DETERMA Architecture

## Execution Integrity Model

```text
AI
↓
Proposal Layer
↓
Authority Core
↓
WAITING_APPROVAL
↓
Human Approval
↓
Capability Grant
↓
State Witness Verification
↓
Execution Release
↓
Constrained Executor
↓
Verification
↓
Append-Only Audit
```

---

## Key Principle

Approval alone is insufficient.
Execution integrity must be revalidated immediately before mutation.

---

## Proposal Layer

The worker may:

- generate patch proposals
- generate specifications
- generate risk analysis

The worker may NOT:

- mutate repositories
- push changes
- deploy systems
- execute arbitrary shell commands

---

## WAITING_APPROVAL

WAITING_APPROVAL is a hard stop.

No execution may proceed while the task remains in this state.

---

## Capability Grant

Capabilities are:

- single-use
- short-lived
- scope-bound
- executor-bound

---

## State Witness

Before execution:

- repository state is verified
- file hashes are verified
- task state is verified
- replay conditions are checked

Execution halts if state no longer matches approval conditions.

---

## Constrained Executor

Executor authority is intentionally narrow.

The demo executor supports only:

```text
repo.apply_patch
```

---

## Fail-Closed Behavior

If verification fails:

```text
NO MUTATION OCCURS
```
