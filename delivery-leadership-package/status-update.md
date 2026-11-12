# Stakeholder Status Update: Evergreen Quote

**To:** Priya Ramanathan, Project Sponsor  
**From:** Samuel Ogunyemi  
**Date:** November 9, 2026

## What shipped today

- The REST quote routes are assembled. I applied the provided premium-calculation fix, and all seven local tests pass.
- I checked the REST endpoints for listing, retrieving, creating, and rejecting invalid quotes.

## What slipped (and why)

- Renters coverage is deferred to a follow-up delivery. It is more than a dropdown change: it needs an approved rate and coordinated updates across validation, premium calculation, seed data, tests, GraphQL, and the website.
- GraphQL wiring and verification are still in progress.

## What's next (tomorrow)

- Finish wiring and verifying GraphQL, then continue with the container and CI work.
- Check the CI result before treating the delivery as ready to merge.

## What I need from you

Please confirm that renters coverage should be planned for a follow-up delivery, and identify when you’d like to review the proposed priority and approve a renters rate. I recommend proceeding this week with the current `node:22-alpine` base image: the finding is moderate, the API is not internet-exposed this week, and the patched tag is expected next week. We’ll document the risk and revisit the patched tag when it is available.