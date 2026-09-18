# Overview of the System

This is the repeatable operator sequence for Company Intelligence v1. It
applies to every client campaign, including a campaign the user selects
directly. A Git commit only saves a file version; it does not invent a plan,
approve a campaign, execute an enrichment, or decide a company's fit.

## Roles

- **User / campaign owner:** supplies or chooses the campaign, reviews the
  business definition and plan tradeoffs, chooses a plan, and explicitly
  approves any credit-consuming test.
- **Codex / planning agent:** reads the canonical framework and the saved
  client context; turns the chosen campaign into a complete, auditable plan;
  identifies assumptions, costs, failure modes, and exact operator actions.
- **Local code and SQLite:** validate contract shapes, order, identities,
  versions, cost caps, run state, and audit history. They do not invent
  business strategy or assess whether a claim is true merely because it fits
  a schema.
- **Clay / data provider:** supplies approved external facts when a plan
  requires them. It does not define the campaign or approve a conclusion.

## Before asking for a named company or running Clay

When the user states that a campaign is selected, do **not** restart campaign
selection or treat a synthetic unit test as the requested real pilot. Prepare
one complete campaign-to-test plan first, covering all of the following:

1. Exact campaign name, client/offer, hypothesis, company decision,
   prediction target, scope and exclusions. Separate confirmed choices from
   provisional assumptions; do not silently inherit constraints from another
   campaign.
2. Canonical Steps 0–5: customer outcome, necessary conditions, observable
   definitions with limitations, and facts needed before naming a vendor.
3. How Steps 6–9 will work for each named company: baseline known facts,
   requirement-by-requirement subtraction, entity/URL validation, and the
   few remaining material questions and alternative evidence pathways.
4. At least two comparable preliminary execution plans, including exact
   capability or manual route, run condition, coverage, estimated Data
   Credits **and** Clay Actions, expected failure modes, and a recommended
   pilot route. Unknown prices must be marked unknown, not rounded to zero.
5. Formula versus AI rule. Use formulas for deterministic operations. If AI
   is proposed, include the exact model, input columns, run condition,
   copy-ready prompt, output schema, QA rule, and incremental cost. AI may
   interpret supplied evidence; it may not invent missing evidence.
6. Clay operator steps and column mapping, a small-batch test matrix
   (positive, negative, boundary, missing, source error), inspection rules,
   stop rules, and the decision labels to return.
7. Approval boundaries: what can be done locally without credits, what the
   user must choose, what needs the real company list, and the separate
   explicit permission needed before paid execution.

Give the user the entire plan and an honest statement of what the code can
currently enforce. A complete plan may still contain owner decisions; label
them visibly instead of disguising them as settled facts. Ask for the real
company file only after the plan is presented. A company is required for
Steps 6–11, not for selecting or planning the campaign.

## Before saying "test passed" or "ready for a pilot"

Inspect the **current code and saved artifacts**, not memory of prior chat or
the existence of a Git commit. Trace the whole route and record the status of
each link:

| Link | Evidence to check |
| --- | --- |
| Campaign selection | The user's exact selected hypothesis is saved under the correct client and version. |
| Complete plan | Steps 0–11, alternative routes, costs, assumptions, stop rules, and approval boundaries are presented together. |
| Plan choice | The user has selected a particular route; that choice is bound to the campaign rather than inferred from a document title. |
| Campaign frame | Steps 0–5 match the selected campaign and have explicit approval. |
| Company case | Steps 6–9 use a named, identity-checked company and subtract already-known facts. |
| Operator plan | Step 10 covers only unresolved facts, with exact inputs, conditions, cost, and QA. |
| Execution | External actions occurred only with specific approval; actual source results and spend are recorded. |
| Decision | Step 11 separates observations from assessment and records the reasoned action. |

For each link, say whether it is **implemented**, **exercised with real data**,
**synthetic only**, **manual only**, or **missing**. A unit test proves a small
piece of code; a synthetic workflow check proves a simulated route; a dry run
checks instructions without spending credits; a live company pilot uses
approved real evidence. Use the narrowest accurate label. Do not use an
unqualified "tested" or "passed" when a required link was not exercised.

If the full route has not been inspected, say so before giving a readiness
verdict. If a critical transition is only written in this protocol and not
enforced in code, disclose that gap explicitly. No number of passing unit
tests closes an unimplemented workflow gate.

## After the user reviews the plan

1. Save the directly selected campaign (when the owner already chose it)
   without inventing alternative campaign options.
2. Save the chosen preliminary plan in SQLite, linked to that exact campaign
   version. A plan choice is not permission to run
   Clay for every company.
3. Approve campaign-specific Steps 0–5 as a versioned frame after owner review.
4. Start one named-company case under both approved records. Work through
   Steps 6–9 and audit the ledger before Step 10.
5. Adapt the selected plan to that company's remaining unknowns and render
   an operator plan. Reconfirm live prices and approval before any paid call.
6. Record factual results, assess them separately, and choose one of the
   four Step 11 actions. Preserve source, cost, limitations, and history.

The current CLI exposes these gates as separate commands; it does not yet
contain a single orchestration command that generates the whole plan. This
protocol is the planning handoff that Codex must follow consistently. The
`company-start` entrypoint now checks for a persisted selected plan as well as
an approved campaign frame; it does not judge whether the owner made a wise
choice or authorize credit use.
