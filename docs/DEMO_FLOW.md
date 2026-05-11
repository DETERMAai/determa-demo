# Demo Flow

## Demo A — Valid Governed Execution

### Submit

```bash
python demo/demo_submit.py
```

Expected:

```text
TASK CREATED
STATE: WAITING_APPROVAL
```

---

### Approve

```bash
python demo/demo_approve.py task_001
```

Expected:

```text
APPROVED
CAPABILITY ISSUED
```

---

### Execute

```bash
python demo/demo_execute.py task_001
```

Expected:

```text
STATE WITNESS VALID
EXECUTION RELEASE ISSUED
PATCH APPLIED
STATE: COMPLETED
```

---

## Demo B — Replay Attempt

```bash
python demo/demo_execute.py task_001
```

Expected:

```text
EXECUTION RELEASE ALREADY CONSUMED
EXECUTION BLOCKED
```

---

## Demo C — State Drift / TOCTOU

### Tamper repository state

```bash
python demo/demo_tamper.py
```

### Attempt execution

```bash
python demo/demo_execute.py task_002
```

Expected:

```text
STATE WITNESS FAILED
EXECUTION RELEASE DENIED
NO MUTATION PERFORMED
STATE: FAILED
```
