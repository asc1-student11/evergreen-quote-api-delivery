# Delivery Goal: Evergreen Quote

## Goal

> By Thursday’s end, deliver the assembled Evergreen Quote API—with REST and GraphQL access to MongoDB-backed, validated quotes—tested, containerized, demonstrated on a local Kubernetes cluster, and merged to main through a reviewed pull request with green CI.

## "Done" looks like

- The API answers the documented REST routes: list quotes, fetch a quote by ID, and create a quote with a computed premium.
- GraphQL serves the same quote data, with its explorer at `/explorer`.
- The test suite (`npm test`) passes, including the premium-calculation safety check.
- The containerized API serves the same answers as the dev server, and the CI run on the merge commit is **green**.
- The local cluster demo shows three API pods behind one Service.
- A reviewed pull request is merged to main, and the delivery branch is deleted.
- `delivery-leadership-package/` contains the completed required artifacts.

## Out of scope (this week)

 - Production deployment to AWS/EKS. 
 - A live S3 deployment unless the instructor approves time for it. 
 - New product features beyond the provided capstone components. 
 - Rewriting or refactoring the supplied engineering code.