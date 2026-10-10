---
name: hicks-law-conversion
description: Audits and designs SaaS and website journeys (pricing pages, landing pages and CTAs, checkout and forms, onboarding) to cut decision load and turn visitors into buyers, using Hick's law, choice-overload research, defaults and progressive disclosure, without dark patterns. Use when the user asks to improve conversion, simplify a pricing page, reduce plans or options, fix competing CTAs, shorten a checkout or form, streamline onboarding, review a page for choice overload or analysis paralysis, or mentions Hick's law, paradox of choice or too many options.
---

# Hick's Law for Conversion

Goal: fewer, clearer decisions between the visitor and the purchase. Not fewer features, not less information. The visitor should always know the one default next step.

Respond in the user's language. This skill produces analysis and specs, not code.

## The model in five lines

1. Hick-Hyman: choice reaction time grows with log2(n + 1) of equally likely options. Gains are biggest on small sets (4 options to 2 helps; 40 to 35 does almost nothing).
2. Hyman's extension: what counts is uncertainty, not raw count. A clearly recommended option lowers uncertainty even if the other options stay visible.
3. Long unordered lists are scanned linearly, so Hick's law does not apply there. Fix them with order, grouping, search or filters.
4. Choice overload is conditional. It shows up when options are complex and hard to compare, the task is hard, the buyer does not know what they want, and they want to decide fast. When those are low, more choice can be fine or even better.
5. Every decision the visitor must make before paying is a place to lose them. Remove, merge, default or defer it.

Full background, formulas and limits: [reference/principles.md](reference/principles.md).

## Pick the mode

- The user shares an existing page, screenshot, URL, flow or description and wants feedback: **Audit mode**.
- The user wants a new page or flow designed, or a rework spec: **Design mode**.
- Both (common): audit first, then design the fixed version.

Before either mode, get these inputs. Ask only for what is missing and cannot be inferred:

- Page or flow type (pricing, landing, checkout, onboarding, other)
- The one conversion goal (purchase, trial, demo, signup, activation event)
- Audience: new visitors or returning experts, B2B or B2C, traffic source
- Known numbers, if any (conversion rate, drop-off step, plan mix). Never invent them.

If the user is not available to answer, state the assumptions at the top and proceed.

## Audit mode

Copy this checklist and work through it:

```
Audit progress:
- [ ] 1. Inputs confirmed or assumptions stated
- [ ] 2. Decision points mapped (decision-load table)
- [ ] 3. Each option classified: Keep / Merge / Default / Defer / Remove
- [ ] 4. Journey rules applied (load the matching reference file)
- [ ] 5. Ethics check passed
- [ ] 6. Fixes prioritized and test plan written
- [ ] 7. Report written with the template
```

**Step 2. Map every decision point.** A decision point is any moment where the visitor must pick, compare or type something before progressing. Include the implicit ones: nav links on a paid landing page, several same-weight buttons, a billing toggle, a coupon field, an optional form field, an add-on checkbox, a plan grid.

Build the decision-load table:

| # | Decision point | Options shown | Equal-weight options | Default or recommendation? | Needed before payment? | Bits |
|---|---|---|---|---|---|---|

- Equal-weight options: options with the same visual prominence and no recommendation. When one option is clearly recommended or preselected and the others are visibly secondary, count 1. A primary button plus a text link counts as 1, not 2.
- Bits = log2(equal-weight + 1). Use it to compare before and after on the same page, never as a time prediction. Total bits per step is the "decision load".

**Step 3. Classify every option.**

- **Keep**: a distinct need a real segment has right now.
- **Merge**: two options a visitor cannot tell apart ("Starter" vs "Basic").
- **Default**: preselect the option most visitors should take, when it serves them and is easy to change.
- **Defer**: needed by some, not now. Move it after the conversion or behind one disclosure ("More payment methods", "Compare all features").
- **Remove**: nobody would miss it, or it only exists for internal reasons.

Never remove something that a meaningful segment needs to buy. Deferring is usually safer than removing.

**Step 4. Apply the journey rules.** Read only the file that matches:

- Pricing and plans: [reference/pricing.md](reference/pricing.md)
- Landing pages, CTAs, navigation: [reference/landing-cta.md](reference/landing-cta.md)
- Checkout and forms: [reference/checkout-forms.md](reference/checkout-forms.md)
- SaaS onboarding and activation: [reference/onboarding.md](reference/onboarding.md)

**Step 5. Ethics check.** Run every proposed change against [reference/ethics.md](reference/ethics.md). If a change only works because the visitor misunderstands something, drop it and say why.

**Step 6. Prioritize.** Rank fixes by expected impact (closer to the payment step and more visitors affected ranks higher) and effort. For each top fix, give the metric to watch and a simple A/B test or before/after plan.

**Step 7. Write the report** using [reference/templates.md](reference/templates.md), section "Audit report".

## Design mode

Copy this checklist:

```
Design progress:
- [ ] 1. Inputs confirmed or assumptions stated
- [ ] 2. One primary action defined for the page or each step
- [ ] 3. Section order written, with the decisions each section asks for
- [ ] 4. Defaults and recommendations chosen and justified
- [ ] 5. Deferred options listed with where they now live
- [ ] 6. Ethics check passed
- [ ] 7. Spec written with the template, decision-load table included
```

Rules for the design:

- One primary action per page or step. Secondary actions are visually quieter (text link, ghost button).
- Information can be rich; decisions must be few. Proof, FAQ and details reduce uncertainty and do not add choices.
- Ask for each decision at the moment it matters, one decision per step when the flow is sequential.
- Name options by outcome or by who they are for ("For solo freelancers"), not by internal jargon.
- Every option left on screen must be visibly different from its neighbours.
- Target: no step with more than 3 equal-weight choices on the conversion path. Above that, group, recommend or defer. This is a working heuristic, not a law.

Write the spec with [reference/templates.md](reference/templates.md), section "Page spec". Include a text wireframe, CTA copy, defaults, the deferred list and the measurement plan.

## Evidence rules

Many conversion statistics online are recycled, untraceable or from a single vendor test. Before quoting a number, check its grade in [reference/evidence.md](reference/evidence.md).

- Grade A or B: cite with the source.
- Grade C: present as "one case" or "one dataset", never as a rule.
- Grade D: do not quote. If the user quotes it, say it is not traceable.
- No source at all: do not give a number. Say the effect has to be measured on their traffic.

When the research disagrees (for example on the number of pricing tiers), say so and give the test to run instead of a verdict.

## Common mistakes to avoid

- Cutting options a real segment needs to buy, in the name of minimalism.
- Hiding information instead of decisions (removing the FAQ, the price, the feature list).
- Adding steps to "simplify". Fewer fields beats fewer pages.
- Treating every extra CTA as harmful. A second CTA is fine when it serves a distinct, validated intent and the default next step stays obvious.
- Using the jam study or a single A/B test as proof that fewer options always win.
- Recommending a plan, default or badge that is not true for most visitors.
