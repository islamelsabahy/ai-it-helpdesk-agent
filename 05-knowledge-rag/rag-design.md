# Knowledge Retrieval / RAG Design

## Knowledge Sources

Possible sources:
- SOPs
- Helpdesk knowledge base
- Vendor manuals
- Internal runbooks
- Approved troubleshooting guides
- Service catalog
- Known error database
- Change records

## Retrieval Flow

```text
Ticket
→ Search Query
→ Retrieve Candidate Articles
→ Rank
→ Verify Relevance
→ Generate Grounded Guidance
```

## Guardrail

If no reliable source is found, the agent should say knowledge is insufficient rather than inventing a fix.
