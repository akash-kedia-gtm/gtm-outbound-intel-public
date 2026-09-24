# GTM Outbound Intelligence

A sanitized public overview of a GTM engineering system for designing clearer, evidence-based outbound campaigns.

## The problem

Outbound research can become expensive and disconnected from the business decision. A campaign idea may lead directly to spreadsheets, enrichment tools, AI columns, and manual research before anyone defines:

1. What company-level decision is being made.
2. What must be true for the campaign to work.
3. What factual evidence could support or challenge those conditions.
4. Which evidence route provides adequate coverage at a reasonable cost.
5. What should happen when evidence is missing, conflicting, or inconclusive.

This system adds a governed planning, execution, and learning layer around those questions.

## Core workflow

```text
Declare the run
      ↓
Compare campaign hypotheses
      ↓
Select one or more bounded campaigns
      ↓
Define business questions, conditions, and evidence requirements
      ↓
Explore evidence pathways
      ↓
Compose complete research routes
      ↓
Preview and approve the operator design
      ↓
Freeze the approved version
      ↓
Run only with separate execution approval
      ↓
Return factual evidence
      ↓
Reassess the affected conditions and questions
      ↓
Continue, revise, stop, or advance
      ↓
Measure pilot performance and learn
```

The loop deliberately separates campaign reasoning, data collection, factual evidence, interpretation, and the final business action.

## Architecture

The reusable architecture separates:

1. **Run lifecycle** — whether work is fresh, an exact resumption, or an audit.
2. **Campaign strategy** — the offer, target company, business outcome, prediction, scope, and exclusions.
3. **Company Intelligence** — company-level questions, necessary conditions, observable criteria, and evidence requirements.
4. **Evidence pathways** — alternative ways to establish a fact, including cost, coverage, source quality, freshness, and failure modes.
5. **Route composition** — AND logic across material questions, OR logic across valid alternatives, shared actions, conditional fallbacks, and dominance decisions.
6. **Execution planning** — exact inputs, filters, provider settings, run conditions, outputs, QA, stop rules, and expected cost.
7. **Human approval** — a readable preview must match the machine representation before the system is frozen.
8. **Evidence review** — returned facts remain separate from assessments; missing data and errors remain unresolved.
9. **Assurance** — the system records why it should seek more evidence, revise its reasoning, stop, or advance.
10. **Pilot learning** — observed coverage, resolution, decision change, errors, outcomes, and costs inform the next version.

## Breadth before selection

For fresh exploration, the method requires a meaningful set of distinct campaign possibilities rather than prematurely anchoring on one idea. After a campaign is selected, it requires broad evidence-pathway exploration before executable routes are composed.

The numerical floors used by the private implementation are safeguards against shallow search. They are not targets for manufacturing duplicate campaigns, evidence sources, or route plans.

## What this public repository contains

- [Overview of the System](./Overview%20of%20the%20System.md)
- A concise explanation of the decision workflow
- A sanitized description of the system boundaries and operating principles

## What it intentionally does not contain

- Client names or private strategy
- Private datasets or spreadsheets
- API keys or credentials
- Internal prompts
- Production enrichment code
- Paid-provider details
- Confidential campaign outputs
- Client-specific retrospectives or evidence

The full working implementation remains private.

## Important boundaries

A validated design is not a live campaign result. A passing unit test, complete planning document, preview, or frozen operator guide does not prove that:

1. An external provider returned evidence.
2. A target company qualifies.
3. A buyer intends to purchase.
4. The campaign will convert.
5. Any credits or actions were authorized or spent.

Those claims require separately approved execution and factual returned evidence.

## Status

This is a public architecture and portfolio overview. It is not presented as a production-ready open-source application. The private implementation is developed and tested separately, while client data and client-specific reasoning remain private.
