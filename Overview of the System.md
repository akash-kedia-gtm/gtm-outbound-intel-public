# Overview of the System

This is the sanitized operator sequence for the current Company Intelligence architecture. It describes the decision system without exposing client strategy, private datasets, production code, provider configuration, or confidential evidence.

A saved document or Git commit records a version. It does not select a campaign, authorize paid work, produce external evidence, or decide that a company is qualified.

## 1. Roles

1. **Campaign owner**
   - Supplies the client and offer context.
   - Selects one or more exact campaign hypotheses.
   - Selects an executable route only after complete alternatives are available.
   - Reviews the plain-language preview.
   - Separately authorizes any live or paid execution.
   - Owns the final commercial decision.

2. **Planning agent**
   - Converts the business objective into bounded campaign hypotheses.
   - Derives company-level questions, necessary conditions, observable criteria, and evidence requirements.
   - Explores possible evidence pathways before choosing tools.
   - Composes complete routes with costs, fallbacks, QA, and stop rules.
   - Preserves the distinction between facts, assessment, uncertainty, and action.

3. **Validation and storage layer**
   - Enforces required structure, identities, versions, lifecycle state, cost arithmetic, and history.
   - Rejects incomplete, generic, mismatched, or stale artifacts.
   - Does not determine whether a semantic judgment is wise merely because its schema is valid.

4. **External research and data systems**
   - Return approved factual evidence.
   - Do not define the business question.
   - Do not decide what the evidence means.
   - Do not authorize spend or outreach.

## 2. Run lifecycle

Every run begins in one explicit mode:

1. **Fresh**
   - Starts new campaign exploration.
   - Cannot silently inherit a prior campaign or its assumptions.

2. **Resume exact version**
   - Continues only a previously stored campaign whose identity and version match exactly.
   - Does not recreate the campaign as a new version.

3. **Audit only**
   - Inspects existing artifacts and controls.
   - Does not create or execute a new campaign.

The campaign identity stays bound across review, selection, preview, freeze, evidence return, and later assessment. A material business change creates a new version rather than silently modifying the approved one.

## 3. Campaign exploration

A fresh run compares at least ten materially distinct company-level campaign hypotheses.

The comparison considers:

1. Outcome fit.
2. Evidence observability.
3. Repeatability.
4. Market breadth.
5. Sales friction.
6. Signal diversity.
7. Risk.

Ten is an exploration floor. It is not permission to create ten semantic duplicates. If the owner has already supplied an exact campaign, that campaign can be registered directly without manufacturing alternatives.

One reviewed set may produce multiple selected campaigns, but each selected campaign remains an independent version with its own reasoning, evidence pathways, routes, costs, and assurance history.

## 4. Business reasoning before tools

For each selected campaign, the system defines:

1. The business outcome.
2. The company-level decision.
3. The prediction being tested.
4. The material business questions.
5. The conditions that would need to hold.
6. The observable criteria that test those conditions.
7. The exact factual evidence requirements.
8. Scope, exclusions, freshness, qualification, rejection, and review rules.
9. Downstream use and QA expectations.

Each proposed condition receives a causal review. The system asks whether the customer outcome would meaningfully weaken if the condition were absent. Useful signals that are not necessary conditions remain labelled as proxies.

Only after the evidence requirements exist should the system select research capabilities. A familiar, inexpensive, or searchable capability is not automatically the right evidence source.

## 5. Evidence-pathway exploration

After the business reasoning is complete, the system documents at least fifteen distinct evidence-pathway candidates.

A pathway is one possible way to establish one or more evidence requirements. It is not yet a complete executable route.

Each pathway records:

1. The questions and requirements it can address.
2. Its source family and expected source quality.
3. Its coverage and freshness.
4. Its cost and manual effort.
5. Its likely failure mode.
6. Whether it is a candidate, included, infeasible, redundant, or outside scope.

The fifteen-pathway floor creates breadth. It does not require fifteen executable systems or repeated purchases of the same fact.

## 6. Route composition

Viable pathways are composed into complete execution routes.

Composition uses:

1. **AND logic** across material business questions or necessary requirements.
2. **OR logic** among valid alternative sources for the same requirement.
3. **Shared actions** when one factual result genuinely answers several requirements.
4. **Conditional fallbacks** that run only while an unresolved fact can still change the decision.
5. **Dominance decisions** that remove a route when another route provides equal or better evidence at lower cost or effort.
6. **Savings arithmetic** comparing independent pathway execution with the composite route.

At least two complete routes are compared when two materially distinct feasible routes exist. Every included route must already contain its full execution logic, not a promise to design it after selection.

## 7. Operational specificity

A route is not executable merely because every field contains text.

A complete action specifies:

1. Exact inputs and column mappings.
2. Literal filters and search terms where relevant.
3. Provider or capability settings.
4. Freshness and result limits.
5. Expected output fields.
6. Run conditions.
7. Cost assumptions.
8. Positive, negative, missing/error, and boundary QA cases.
9. Stop conditions and fallback behavior.
10. The evidence requirements the action can answer.

Unknown prices remain unknown. Missing evidence remains unresolved. A source error is not evidence that a company fails the campaign criteria.

## 8. Preview, approval, and freeze

After an exact route is selected:

1. The system renders a machine representation.
2. It renders a numbered, plain-language operator guide.
3. Automated checks compare identity, operations, costs, lifecycle state, and decision policy.
4. A human reviews the meaning of the design.
5. The approved matching version is frozen.

The preview is non-executing. The freeze is also pre-execution. Neither step authorizes paid research.

## 9. Factual evidence and assessment

After separately authorized execution, returned evidence is recorded with:

1. Entity identity.
2. Source and provenance.
3. Event and observation time.
4. Provider status.
5. Literal factual result.
6. Actual cost and actions.
7. Limitations.
8. The exact requirements and business questions affected.

Facts and interpretation remain separate. Every affected criterion and business question receives an explicit assessment. Alternate pathways remain visible so that one source failure does not become an unsupported negative conclusion.

## 10. Assurance loop

After assessment, the system records one explicit branch:

1. Seek another evidence source for the same question and condition.
2. Revise the pathway because the prior route no longer fits.
3. Add or revise a condition exposed by the evidence.
4. Add a genuinely new material business question.
5. Stop unresolved because no feasible route can resolve a material uncertainty.
6. Stop negative because usable evidence materially contradicts fit.
7. Stop with reasonable assurance because the material questions are sufficiently supported and more research has low expected decision value.

Reasonable assurance is not certainty and is not purchase intent. It means the remaining uncertainty is unlikely to change the defined company-level decision.

Every continuation records why another action can change the decision, what evidence is needed next, and the incremental cost.

## 11. Pilot learning

Observed pilot results are summarized using measures such as:

1. Evidence found rate.
2. Error and no-data rate.
3. Requirement-resolution yield.
4. Business-question resolution.
5. Decision-change yield.
6. False-positive rate when outcome labels exist.
7. Actual cost per useful resolution.
8. Action-level contribution.

Pilot metrics do not silently rewrite a frozen campaign. Material changes create a new reviewed version.

## 12. Status language

Each stage uses the narrowest accurate label:

| Status | Meaning |
| --- | --- |
| Planned | The business and evidence logic is documented. |
| Validated locally | Structural and synthetic checks passed. |
| Previewed | Human and machine representations were rendered but not frozen. |
| Approved for freeze | A human accepted the previewed meaning. |
| Frozen | The exact pre-execution design was persisted. |
| Executed | Approved external actions actually ran. |
| Evidence assessed | Returned facts were interpreted against the declared questions and criteria. |
| Reasonable assurance | The company-level decision is sufficiently supported after evidence review. |

A plan, unit test, preview, or freeze must never be presented as live execution or a qualified prospect.

## 13. Public and private boundary

This public repository explains the reusable architecture. It intentionally excludes:

1. Client names and offers.
2. Client-specific campaigns.
3. Private retrospectives.
4. Research datasets.
5. Exact provider configurations.
6. Production implementation.
7. Credentials and pricing details.
8. Returned evidence and company decisions.

Those materials remain in controlled private workspaces.
