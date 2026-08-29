# Ticket State Machine

Suggested states:

- NEW
- TRIAGE
- ASSIGNED
- IN_PROGRESS
- WAITING_USER
- WAITING_VENDOR
- ESCALATED
- RESOLVED
- CLOSED
- REOPENED

## Example Flow

```text
NEW → TRIAGE → ASSIGNED → IN_PROGRESS
IN_PROGRESS → RESOLVED → CLOSED
IN_PROGRESS → ESCALATED
RESOLVED → REOPENED
```

Production implementations should retain state transition history.
