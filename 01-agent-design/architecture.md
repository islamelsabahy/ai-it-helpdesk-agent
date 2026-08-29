# Agent Architecture

## Components

1. Input Normalizer
2. Intent Classifier
3. Ticket Classifier
4. Priority Engine
5. SLA Engine
6. Knowledge Retriever
7. Troubleshooting Planner
8. Escalation Engine
9. Incident Summarizer
10. Resolution Note Generator
11. Guardrail Layer
12. Evaluation Layer

## Runtime Flow

```text
Message
→ Normalize
→ Identify Request Type
→ Extract Ticket Fields
→ Classify Category
→ Assess Impact/Urgency
→ Assign Priority
→ Retrieve Knowledge
→ Propose Safe Troubleshooting
→ Validate Outcome
→ Resolve or Escalate
→ Generate Ticket Notes
```

## LLM Responsibilities
- Understand natural language
- Summarize
- Extract fields
- Explain troubleshooting steps
- Draft notes

## Deterministic Responsibilities
- Priority calculation
- SLA timers
- escalation thresholds
- entitlement checks
- change approval requirements
