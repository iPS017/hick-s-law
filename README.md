# hicks-law-conversion

[Lire en français](README.fr.md)

A Claude skill that audits and designs SaaS and website journeys to cut decision load and get visitors to buy. It applies Hick's law, the research on choice overload, defaults and progressive disclosure to four journeys: pricing pages, landing pages and CTAs, checkout and forms, and SaaS onboarding.

It produces analysis and page specs, not code, so it works with any stack.

## What it does

**Audit mode.** Give it a screenshot, a URL, a flow or a description. It maps every decision the visitor has to make, scores the decision load, classifies each option (keep, merge, default, defer, remove), checks the result against dark-pattern rules and returns a prioritised report with a test plan.

**Design mode.** Describe the page or flow you need. It returns a spec with one primary action, the section order, the decisions each section asks for, a text wireframe, the defaults, what gets deferred and how to measure the result.

## Why another UX skill

Most skills that mention Hick's law turn it into "fewer options is better". The research does not say that:

- Hick's law is logarithmic and was measured on simple reaction tasks. It says little about long lists or considered purchases.
- Choice overload is real only under specific conditions (complex options, hard task, uncertain buyer, wish to decide fast). Two meta-analyses (Scheibehenne 2010, Chernev 2015) disagree on everything else.
- A lot of the conversion statistics quoted online cannot be traced to any study.

This skill builds on that. It reduces decisions, not information. It grades every statistic it may quote (A to D) and refuses to cite the untraceable ones. It also blocks the tactics that convert today and cost you in refunds, churn and fines tomorrow: preselected paid add-ons, fake "most popular" badges, drip pricing.

## Install

**Claude Code — plugin installation**

Run these commands inside Claude Code:

```text
/plugin marketplace add iPS017/hick-s-law
/plugin install hicks-law-conversion@hick-s-law
```

Restart your Claude session after installation. You can invoke the skill with
`/hicks-law-conversion:hicks-law-conversion` or describe the audit you need.

For a plugin manager that asks for a GitHub marketplace, use `iPS017/hick-s-law`.
The repository includes `.claude-plugin/marketplace.json` and the plugin manifest.

**Claude Code — manual skill installation (alternative)**

```bash
git clone https://github.com/iPS017/hick-s-law.git
cp -r hick-s-law/hicks-law-conversion ~/.claude/skills/
```

Or copy the `hicks-law-conversion/` folder into `.claude/skills/` inside a project.

**Claude apps**

Zip the `hicks-law-conversion/` folder (the one containing `SKILL.md`) and upload it from the Skills section of Claude's settings.

## Usage

The skill triggers on its own when you ask things like:

- "Audit our pricing page, conversion to paid is stuck at 1%"
- "We have four buttons in the hero, which one should stay?"
- "Shorten this checkout"
- "Design the onboarding for a trial of our invoicing app"
- "Is this page suffering from choice overload?"

## Structure

```
hicks-law-conversion/
  SKILL.md                 workflow, modes, rules
  reference/
    principles.md          Hick-Hyman, choice overload, defaults, decoy, disclosure
    pricing.md             pricing pages and plan selection
    landing-cta.md         landing pages, CTAs, navigation
    checkout-forms.md      checkout, forms, payment and shipping choices
    onboarding.md          SaaS onboarding and activation
    ethics.md              choice architecture vs dark patterns, EU pointers
    evidence.md            graded evidence and the statistics not to quote
    templates.md           audit report, page spec, worked example
evals/
  evals.json               test scenarios
```

## Testing

`evals/evals.json` holds four scenarios (pricing audit, landing page design, a dark-pattern request, an onboarding audit in French) with the expected behaviour. Run them with and without the skill and compare.

## Limits

- The "bits" score is a way to compare a page before and after a change. It does not predict time or conversion.
- Recommendations are hypotheses until tested on your traffic.
- The legal section is a pointer, not legal advice.

## License

MIT
