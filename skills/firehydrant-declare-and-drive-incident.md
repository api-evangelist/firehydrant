---
name: Declare and drive a FireHydrant incident
description: >-
  Open an incident with the right severity, services and team, keep it current as it moves through
  milestones, and close it out — using only operations that exist in the published FireHydrant
  OpenAPI.
api: openapi/firehydrant-api-openapi.yml
operations:
  - listSeverities
  - listPriorities
  - listServices
  - listTeams
  - createIncident
  - getIncident
  - updateIncident
  - createIncidentNote
  - listIncidentMilestones
  - listIncidentTasks
  - createIncidentTask
  - listIncidentEvents
  - archiveIncident
  - unarchiveIncident
---

# Declare and drive a FireHydrant incident

## Before you call anything

- Base URL is `https://api.firehydrant.io/v1`. Every request needs
  `Authorization: Bearer fhb-...`. There is no test key prefix and no sandbox host — **the key you
  are holding points at a live organization.**
- If you only need to read, use `https://api-read.firehydrant.io/v1` instead. It rejects every write
  method and can lag the primary by up to 30 seconds. Prefer it for any list/get step.
- The account rate limit is **50 requests per 10 seconds, shared across every API key on the org**.
  On `429` the body is `{"error": "rate limit exceeded"}`; honor `Retry-After` (seconds). There is
  no remaining/reset header, so you cannot pace proactively — react to the 429.
- There is **no `Idempotency-Key`**. If a `createIncident` call times out, do **not** blindly retry:
  call `listIncidents` and match on `name` first, or you will declare the same incident twice.

## Steps

1. **Resolve the vocabulary first.** Severity and priority are org-defined, not fixed enum values.
   Call `listSeverities` and `listPriorities` and pick a real `slug` (commonly `SEV1`…`SEV5`,
   `P1`…`P4`, but never assume). Call `listServices` and `listTeams` to resolve names to UUIDs.
2. **Declare.** `createIncident` with `name`, `severity`, `priority`, and the impacted
   `services` / `environments` / `functionalities`. Keep the name human-readable — it becomes the
   Slack/Teams channel name.
3. **Confirm.** `getIncident` on the returned `id`. IDs are bare UUIDs with no type prefix, so hold
   onto the whole response, not just the id.
4. **Keep it current.** `updateIncident` to change milestone, summary, severity or custom fields as
   the response develops. `createIncidentNote` for timeline narration. `createIncidentTask` for work
   items; `listIncidentTasks` to check what is outstanding.
5. **Read the history.** `listIncidentMilestones` gives the milestone timeline with durations;
   `listIncidentEvents` gives the full activity stream.
6. **Wrong call?** `archiveIncident` (a `DELETE` on the incident) soft-deletes it, and
   `unarchiveIncident` brings it back. This is the only true undo pair in the API and it has no
   published expiry. Use it rather than editing an incident into meaninglessness.

## What to do on errors

- `401` → `{"error":"This endpoint requires you to be authenticated."}` — the Bearer header is
  missing or the key is revoked. Every endpoint is authenticated except `/v1/noauth/ping`.
- `400` → `ErrorEntity` with `code`, `detail`, `messages[]`, `meta`. Match on `code`, which
  FireHydrant documents as stable. Note that only 12 of 373 operations declare a 400 in the spec, so
  treat any 4xx as possible even where the spec is silent.
- `409 Already Added` — you are re-attaching something already attached. Not a failure to retry.

## Do not

- Do not invent severity or priority slugs; read them.
- Do not retry a write on timeout without checking whether it landed.
- Do not use `https://api-read.firehydrant.io` for any step from 2 onward — it rejects writes.
