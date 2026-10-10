# Principles

## Contents
- Hick-Hyman law: what it says
- What it does not say
- Choice overload: when it happens
- Defaults
- Recommendation and the decoy effect
- Progressive and staged disclosure
- Putting it together: the decision-load model

## Hick-Hyman law: what it says

Hick (1952) and Hyman (1953) measured choice reaction time in lab tasks where a light came on and the subject pressed the matching key.

```
RT = a + b * log2(n + 1)
```

- `n`: number of equally likely alternatives. The `+1` accounts for the uncertainty of whether to respond at all.
- `a`, `b`: constants measured per task and person.
- Hyman showed the real driver is information (entropy): `H = sum(p_i * log2(1/p_i))`. When options are not equally likely, uncertainty drops.

Consequences for design:

- The curve is logarithmic. Going from 1 to 3 options costs as much extra time as going from 3 to 7, then from 7 to 15. Cuts matter most on small sets.
- Making one option much more likely (recommended, preselected, visually dominant) lowers entropy without removing anything. This is the mechanism behind "highlight one plan".

## What it does not say

- It does not say "less is always better". Liu, Gori, Rioul, Beaudouin-Lafon and Guiard (CHI 2020) argue the law speaks against that slogan: the marginal cost of an extra option shrinks as the set grows, and most interface tasks are dominated by visual search and deliberation, not by the reaction-time component Hick measured.
- It does not apply to long unordered lists. Scanning is roughly linear there. Order, group, add search or filters.
- It does not apply to considered purchases where the buyer researches and compares attributes. Those are governed by decision difficulty, preference uncertainty and trust, which is where choice-overload research is more useful.
- It does not justify burying content. Moving items from a top menu into deeper levels can make them harder to find.

Use Hick's law as a lens ("how many equal-weight choices am I asking for here?"), not as a calculator of conversion.

## Choice overload: when it happens

- Iyengar and Lepper (2000): a tasting booth with 24 jams drew more stoppers (about 60%) than one with 6 (about 40%), but about 3% of stoppers at 24 bought versus about 30% at 6. The sample was small (roughly 35 purchases in total) and conditions were not randomised per shopper. Treat it as a famous illustration, not as proof.
- Scheibehenne, Greifeneder and Todd (2010), meta-analysis of 63 conditions (N = 5,036): mean effect close to zero, with large variance between studies.
- Chernev, Bockenholt and Goodman (2015), meta-analysis of 99 observations (N = 7,202): the effect is real and significant once four moderators are accounted for:
  1. Choice set complexity (options hard to compare, no dominant option)
  2. Decision task difficulty (time pressure, many attributes, unclear presentation)
  3. Preference uncertainty (buyer does not know what they want, low expertise)
  4. Decision goal (wanting to decide quickly with low effort)

Practical reading: the conversion path of most SaaS and e-commerce sites scores high on all four for first-time visitors (complex plans, unfamiliar product, wish to decide fast). That is where reducing and structuring choice pays off. Expert repeat buyers tolerate, and sometimes want, more options.

Measures of overload that move together: lower satisfaction or confidence, more regret, deferral ("I'll decide later"), and switching.

## Defaults

- Johnson and Goldstein (2003, Science): countries with opt-out organ donation had far higher consent than opt-in countries; in their online experiment, consent was about 82% with opt-out, about 79% with a forced choice, and about 42% with opt-in. Replications confirm the direction with smaller effects.
- Three mechanisms (Dinner, Johnson, Goldstein and Liu, 2011): effort (changing costs work), implied endorsement (the default looks recommended), reference point (the default becomes the norm).

Design rules:
- A default is a recommendation. Only preselect what most visitors would pick with full information.
- The alternative must be one click away and clearly visible.
- In the EU, preselecting an extra paid option is not allowed (see ethics.md).

## Recommendation and the decoy effect

- Huber, Payne and Puto (1982): adding an option that is clearly worse than one target option (asymmetrically dominated) raises the target's share.
- The famous Economist subscription example comes from Dan Ariely's classroom test with about 100 students, not from a published field test by The Economist. Later replication work found the effect weaker and less reliable in realistic, multi-attribute choices.

Design rules:
- Prefer an honest "Recommended for X" label on a plan that is genuinely the best fit for most visitors.
- A third plan should exist because a real segment needs it, not only to make another plan look good. A plan nobody is meant to buy is a manipulation risk.

## Progressive and staged disclosure

Nielsen Norman Group definition: show the primary options by default and defer advanced or rarely used ones to a secondary screen or a disclosure control. Benefits: learnability, efficiency, fewer errors. What appears first signals importance.

Rules:
- Get the split right. Use data (what most people use) to decide what is primary.
- Make the secondary options easy to find with one clear control ("More options", "Compare all features").
- Avoid more than one level of disclosure.
- Staged disclosure (wizards) shows one step at a time. Use it for sequential decisions, not to split a short form into many pages.

## Putting it together: the decision-load model

For each step of the journey:

1. List the decisions the visitor must make.
2. For each, count equal-weight options. Compute bits = log2(n + 1) for comparison only.
3. Ask, in order:
   - Can this decision be removed? (Nobody needs it.)
   - Can it be made for them? (A default that serves most.)
   - Can it be made later? (After purchase, in settings, at renewal.)
   - Can the options be merged or made clearly different?
   - Can one option be recommended honestly?
4. Keep information that reduces uncertainty (price, what is included, proof, guarantees, FAQ). Information is not a decision.
