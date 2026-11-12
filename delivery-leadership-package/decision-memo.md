# Decision Memo:

**Date:** Tuesday, November 9, 2026  
**Author:** Samuel Ogunyemi  
**Decision area:** Scope tradeoff after Inject #1

## Context

A partner aggregator asked us to make renters coverage quotable through the API by Thursday. It sounds like one more dropdown choice, but our morning checks showed that the API rejects unsupported quote types. Supporting renters would mean more than changing the dropdown: we would need an approved rate and updates to validation, seed data, tests, GraphQL, and the website. Adding that work now could put the agreed delivery goal at risk.

## Options considered

1. **Add renters coverage this week.** This could meet the partner’s request sooner. But the work crosses several parts of the product, the renters rate has not been approved, and we would need to reduce or delay other planned work to make room.

2. **Keep this week’s scope and plan renters for a later delivery.** This protects the current goal and gives us time to agree on the rate and plan the related changes. The tradeoff is that the partner will not be able to quote renters coverage this Thursday.

## Recommendation

I recommend keeping renters coverage out of this week’s delivery and recording it as a prioritized follow-up. We should finish and verify the agreed API delivery first, then schedule renters once the sponsor confirms the rate and the team can plan the full set of changes.

## Why

A quote is only useful if its premium is approved and consistent across the API, GraphQL, and customer-facing site. Adding an unapproved rate to meet a date could give the partner an answer that looks complete but is not trustworthy. Protecting quote accuracy and the delivery goal is more important than treating this as a small dropdown change.

## What would change my mind

I would reconsider if the sponsor approves a renters rate and confirms by Wednesday morning which planned work should move to make room—without compromising the required tests, CI, or Thursday delivery review.

## Copilot test review

Copilot suggested a test for a quote request that leaves out `coverageAmount`. I reviewed the suggestion, added it to the existing test file, and ran the suite. All eight tests passed, including the new check that the API returns a 400 response. The suggestion fit the existing test pattern and checked a clear outcome. I’d keep this test, while still confirming that the expected response matches the product rules. AI output should not be trusted just because it looks reasonable: the test run gave me evidence that the test works with this service, and CI will run the suite again when changes are pushed.