# Output templates

## Contents
- Audit report
- Page spec
- Worked example (pricing audit, short)

Use the user's language for the content. Keep the section order.

## Audit report

```markdown
# Decision-load audit: [page or flow name]

## Context
- Goal: [one conversion goal]
- Audience: [who, traffic source, new or returning]
- Inputs used: [screenshot / URL / description / numbers]
- Assumptions: [anything not confirmed]

## Summary
[3 to 5 sentences: the main decision bottlenecks, total decision load before vs after, top 3 fixes.]

## Decision-load table (current)
| # | Step | Decision point | Options shown | Equal-weight | Default? | Needed before payment? | Bits |
|---|---|---|---|---|---|---|---|
Total bits on the path: [x]

## Findings
For each finding:
### [n]. [Short title]
- What happens: [observable fact]
- Why it costs conversions: [link to the principle, with evidence grade if a number is used]
- Fix: [Keep / Merge / Default / Defer / Remove + concrete change]
- Priority: [High / Medium / Low]

## Decision-load table (proposed)
[same table after fixes] Total bits: [y]

## Ethics check
[Confirm no change relies on misunderstanding. List any rejected idea and why.]

## Test plan
| Fix | Metric | Test | Guardrail metric |
|---|---|---|---|

## Open questions
[What data would change the recommendations.]
```

## Page spec

```markdown
# Page spec: [page or flow name]

## Goal and primary action
- Conversion goal: [...]
- Primary action: [verb + object, exact CTA copy]
- Secondary action (if any): [copy + why it serves a distinct intent]

## Audience and assumptions
[...]

## Structure
For each section, top to bottom:
### [Section name]
- Purpose: [what uncertainty it removes]
- Content: [headline, key lines, proof]
- Decisions asked: [none / list with options and default]

## Text wireframe
[Block layout using plain characters, e.g.]
+--------------------------------------------------+
| Logo                                  [Pricing]  |
+--------------------------------------------------+
| Headline                                          |
| Subline                                           |
| [ Primary CTA ]   secondary text link             |
| microline: no card required, cancel anytime       |
+--------------------------------------------------+

## Defaults and recommendations
| Decision | Default or recommended option | Why it serves most visitors | How to change it |
|---|---|---|---|

## Deferred options
| Option | Moved to | Who needs it |
|---|---|---|

## Decision-load table
[for the spec, per step] Total bits: [x]

## Ethics check
[...]

## Measurement
- Primary metric: [...]
- Guardrails: [refunds, support tickets, plan mix, churn]
- First test to run: [...]
```

## Worked example (pricing audit, short)

Input: SaaS invoicing tool, pricing page with 5 plans (Free, Starter, Basic, Pro, Business), monthly/annual toggle defaulting to monthly, 3 add-ons with checkboxes under the grid, a 40-row comparison table always open, "Contact sales" on Business. Goal: paid signups from freelancers.

Decision-load table (current):

| # | Decision point | Options | Equal-weight | Default? | Needed before payment? | Bits |
|---|---|---|---|---|---|---|
| 1 | Plan | 5 | 5 | No | Yes | 2.58 |
| 2 | Billing period | 2 | 1 (preselected) | Monthly | Yes | 1.00 |
| 3 | Add-ons | 3 checkboxes | 3 | None | No | 2.00 |
| 4 | Comparison table | 40 rows | n/a, linear scan | none | No | n/a |
| Total | | | | | | 5.58 |

Key fixes:
1. Merge Starter and Basic (one-line difference is a limit of 10 vs 15 invoices). Keep Free as an entry path, recommend the merged plan "Freelancer". Move Business to a "Teams" link below the grid. Plan decision: 3 options, one recommended.
2. Defer add-ons to after signup, offered when the user hits the related limit.
3. Collapse the comparison table behind "Compare all features".
4. Billing toggle: test annual default with total billed shown, monthly one click away.

Decision-load table (proposed): plan, 3 options with one clearly recommended (1 equal-weight, 1.00 bit); billing period, preselected (1.00); add-ons removed from the page. Total 2.00, down from 5.58. The bigger win is qualitative: the visitor now reads one recommendation instead of comparing five near-identical plans.

Test plan: grid change first (metric: paid signups per visitor; guardrail: revenue per visitor, downgrades in 30 days).
