# AI IT Helpdesk Agent

A public-safe reference architecture for an AI-powered IT helpdesk assistant.

The agent supports ticket intake, triage, priority classification, troubleshooting guidance, SLA awareness, knowledge retrieval, escalation, incident summarization, and helpdesk-ready resolution notes.

All examples and sample data are fictional.


## Try the triage / جرّب الفرز

**Live:** https://islamelsabahy.github.io/ai-it-helpdesk-agent/

The agent design in this repo now runs as a working triage tool:

- **Reads tickets as staff actually write them**, in Arabic or English ("النت فاصل في الشركة كلها", "أودو بيطلع error في الفاتورة"). Categories follow [`02-ticket-triage/category-model.md`](02-ticket-triage/category-model.md), with a confidence score; when confidence is low it uses *Needs Review* and asks one focused question instead of guessing.
- **Impact × urgency → priority** using the matrix in [`03-priority-sla/priority-model.md`](03-priority-sla/priority-model.md). Security incidents and data-loss risk are bumped.
- **SLA due times** from [`sla-model.md`](03-priority-sla/sla-model.md) on the **Egyptian working week (Sunday–Thursday, 9–5)**. P1 runs on clock time.
- **Escalation matrix** ([`06-escalation`](06-escalation)): incident owner, security, vendor/ISP, stop-and-escalate on data-loss risk, change approval for unsafe requests.
- **Knowledge article and a safe first response:** first steps in the user's language, with no invented diagnosis, no secrets, no bypassing of security controls, and no closing without validation ([`09-safety-privacy`](09-safety-privacy)).
- **Queue view:** paste or upload a ticket CSV to see first-response and resolution breaches, tickets at risk and security tickets, sorted for the team lead.
- **Executable evaluation:** the seven cases in [`tests/evaluation-cases.md`](tests/evaluation-cases.md) run in the page and in CI (`node tests/test_triage.js`).
- **Optional AI layer:** paste your own Anthropic API key to draft a friendlier reply and a technician handoff note from the deterministic triage (the key is never stored).

Engine: `docs/app/triage.js`.

## Core Capabilities

- Ticket intake normalization
- Category classification
- Priority/severity classification
- SLA awareness
- Troubleshooting guidance
- Knowledge retrieval / RAG-ready design
- Escalation recommendations
- Incident summaries
- Resolution note generation
- Next-best-action suggestions
- Human handoff
- Evaluation and guardrails

## Workflow

```text
User Request
   ↓
Intent Detection
   ↓
Ticket Normalization
   ↓
Category Classification
   ↓
Priority Assessment
   ↓
Knowledge Retrieval
   ↓
Troubleshooting Guidance
   ↓
Resolution OR Escalation
   ↓
Ticket Summary
   ↓
Resolution Notes
```

## Guiding Principles

1. Never fabricate a diagnosis.
2. Distinguish confirmed facts from hypotheses.
3. High-impact actions require human review.
4. Never expose credentials, secrets, internal topology, or private documentation.
5. Respect approved SLA and escalation rules.
6. Use knowledge sources when available.
7. Do not claim an issue is resolved without validation.
8. Public samples must use fictional data only.
9. Security incidents should be escalated according to policy.
10. The agent assists technicians; it does not replace change-control or approval processes.

## Roadmap

- [x] Agent architecture
- [x] Ticket triage
- [x] Priority/SLA model
- [x] Troubleshooting framework
- [x] Knowledge retrieval model
- [x] Escalation matrix
- [x] Incident summary format
- [x] Resolution notes
- [x] Guardrails
- [x] Evaluation cases
- [ ] Runnable Python agent
- [ ] Vector/RAG adapter
- [ ] API layer
- [ ] Web interface
- [ ] Helpdesk integration
- [ ] Automated metrics dashboard

## Author

Eng. Islam El-Sherbiny  
IT Management · AI · Infrastructure · Digital Transformation · Automation
