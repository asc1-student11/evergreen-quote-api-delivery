# Delivery Goal: Evergreen Quote

> Copy this file into `delivery-leadership-package/delivery-goal.md`. One sentence. Read it back to yourself. Then to your pair. Then to someone who wasn't in the room. If they can repeat it, it's good.

## Goal

> By Thursday EOD, the assembled Evergreen Quote API (REST + GraphQL, MongoDB-backed) is merged to main via a reviewed PR with a green CI run, demonstrated in a container and on a local Kubernetes cluster.
## "Done" looks like

- The API answers every documented route: list, fetch by id, create with a computed premium.
- The same data answers through GraphQL, with the explorer at `/explorer`.
- `npm test` passes; the safety net holds.
- The containerized API serves the same answers as the dev server, and the CI run on the merge commit is **green**.
- The cluster demo shows three API pods behind one Service.
- A reviewed PR is merged, branch deleted.
- `delivery-leadership-package/` is complete and committed.

## Out of scope (this week)

- _What you are intentionally not doing._
