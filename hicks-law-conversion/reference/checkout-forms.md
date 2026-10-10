# Checkout and forms

## Contents
- Benchmarks worth knowing
- Rules for fields
- Rules for choices inside the checkout
- Upsells and add-ons
- Audit questions
- Test ideas

## Benchmarks worth knowing

From Baymard Institute's checkout research (large-scale usability testing plus a benchmark of live sites):

- The average US checkout shows 23.48 form elements by default (14.88 counting only form fields).
- An ideal checkout can get down to about 12 form elements (about 7 fields, 2 checkboxes, 2 dropdowns, 1 radio group).
- The average large e-commerce site could gain about 35% in conversion rate from checkout design improvements alone.
- In Baymard's abandonment survey, a checkout that is too long or complicated is one of the main reasons given, in the high teens as a percentage of shoppers who abandoned for reasons other than browsing. Forced account creation and extra costs are other top reasons.

Use these as orders of magnitude, and check baymard.com for the latest figures before quoting them in a deliverable.

## Rules for fields

1. **Count fields, not pages.** A multi-step checkout with few fields beats a one-page checkout with many. Splitting into steps does not reduce the number of decisions.
2. **For every field ask: if it is missing, can we still deliver and bill?** If yes, remove it or move it after purchase.
3. **Billing address = shipping address by default,** with a checkbox to change it.
4. **One name field** where the market allows it, autocomplete on address, country and city inferred from postcode where reliable.
5. **Optional fields: remove them, or mark them clearly.** Each optional field still costs a decision ("should I fill this?").
6. **Guest checkout as the most prominent option** when you sell to consumers. Offer account creation after payment (password only).
7. **Inline validation** and clear error messages so the visitor does not decide what went wrong.
8. **Coupon field collapsed** behind a link ("Have a promo code?"). A visible empty coupon field sends visitors to search for codes.

## Rules for choices inside the checkout

- **Shipping:** preselect the option that fits most buyers (often the cheapest or the free threshold) and show delivery dates, not only method names. Two or three options are usually enough.
- **Payment:** show the most used methods first (cards and the one or two wallets your audience uses). Group the rest behind "More payment methods". Too few methods also causes abandonment, so defer rather than remove.
- **Plan or variant changes in checkout:** avoid. If the visitor can change plan in checkout, show it as a summary with an "Edit" link, not as a new grid.
- **Totals:** show the full price, taxes and fees from the first step. Costs revealed late are both a top abandonment reason and drip pricing.

## Upsells and add-ons

- At most one upsell, relevant to what is in the cart, and never preselected.
- Prefer the post-purchase moment (thank-you page, onboarding) over the payment step.
- The decline option is a plain "No thanks", not a guilt-trip line.

## Audit questions

- How many form elements are shown by default from cart to confirmation?
- Which fields are not needed to deliver and bill?
- Is guest checkout the most prominent path?
- How many payment and shipping options are shown with equal weight? Is there a sensible default?
- When does the visitor first see the final total?
- Are there checkboxes preselected? Which ones add cost or consent?

## Test ideas

- Remove or defer the two least necessary fields.
- Collapse the coupon field.
- Preselected recommended shipping vs no preselection.
- Payment methods: top three plus "More" vs full list.
- Upsell at payment step vs on thank-you page.
