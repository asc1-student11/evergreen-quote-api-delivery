# Delivery Review: Evergreen Quote

## Slide 1: Delivery goal & did we hit it?

- **Goal:** Deliver the assembled Evergreen Quote API—with REST and GraphQL access to MongoDB-backed, validated quotes—tested, containerized, demonstrated on a local Kubernetes cluster, and merged to `main` through a reviewed pull request with green CI.
- **Hit?** ☒ Yes  ☐ Partially  ☐ No
- **Why:** The API was assembled, tested, containerized, and demonstrated on the local Kubernetes cluster. The reviewed pull request was merged to `main` with green CI.

## Slide 2: What shipped

- **REST:** The health, list, lookup, create, and validation requests were checked.
- **GraphQL:** The module was wired into the service and verified through the explorer. _[Add any specific query/mutation results if you want to show them.]_
- **Tests:** All eight local tests passed, including the missing-coverage-amount test.
- **Container:** The `evergreen-quote-api:1.0` image built and ran.
- **Kubernetes:** Three API replicas ran behind the Service with MongoDB. A quote was created through the Service and returned the expected premium of 2700.
- **CI:** The GitHub Actions run on `delivery/lead` was green. https://github.com/asc1-student11/evergreen-quote-api-delivery/actions/runs/43277710070
- **Pull request:** https://github.com/asc1-student11/evergreen-quote-api-delivery/pull/12
- **Merge to `main`:** https://github.com/asc1-student11/evergreen-quote-api-delivery/actions/runs/43277962237

## Slide 3: Two key decisions

- **Decision 1 — Defer renters coverage.** The request affected several parts of the product and needed an approved rate, so I kept it out of this week’s delivery and recorded it as follow-up work.
- **Decision 2 — Proceed this week with the current base image and document the CVE.** The platform team described the finding as moderate, said the API was not internet-exposed this week, and expected the patched tag next week.

## Slide 4: Risks & injects

- **Top risk:** A successful-looking response can still contain an incorrect premium. The test suite caught the route defect that returned 0.35 instead of the expected amount.
- **Inject #1:** A partner requested renters coverage, and the platform team reported a moderate CVE in the base image. I deferred renters and recommended proceeding with the current image this week, with the risk documented and the patched tag to be revisited next week.
- **Inject #2:** Support reported quote requests returning 400, while the simulated CI run on `main` was red at the test step. I routed the investigation to the engineering/deployment owner to confirm what was actually deployed and whether any change bypassed the CI gate.
- **Go/no-go:** I will not merge onto a red `main`. I will proceed when the required CI checks are green and the deployed version has been clarified.

## Slide 5: What I’d do differently next round

- Confirm repository paths, configuration files, and running services earlier so setup issues take less time.
- Verify behavior in the exact runtime being demonstrated, including configuration and premium calculations.
- Keep the board current with owners, acceptance criteria, risks, and evidence links so delivery status is easy to understand.

## Q&A prep: likely questions

- **Why didn’t you add renters coverage?** It required an approved rate and coordinated changes across validation, premium calculation, seed data, tests, GraphQL, and the website.
- **Why does a red test matter if a demo looked successful?** A successful HTTP response does not prove the premium is correct. The test suite caught a calculation defect that the demo could have missed.
- **Why didn’t you merge while `main` was red?** The merge decision requires green CI. The incident also raised a separate question about what version customers were actually using.
- **What remains before calling the goal complete?** Finish PR review, confirm green CI on the PR, merge to `main`, and verify the service on `main`.