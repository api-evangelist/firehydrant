---
name: Work a FireHydrant retrospective to publication
description: >-
  Find the retrospective report for an incident, fill its fields, and publish it — the after-action
  half of the incident lifecycle.
api: openapi/firehydrant-api-openapi.yml
operations:
  - listRetrospectiveReports
  - updateRetrospectiveField
  - publishRetrospectiveReport
  - listRetrospectiveQuestions
  - listRetrospectiveMetrics
  - getIncident
---

# Work a FireHydrant retrospective to publication

## Naming warning

FireHydrant calls these "retrospectives" everywhere in the product and the docs, but the API path is
`/v1/post_mortems/reports`. Searching the spec for "retrospective" finds the operationIds; searching
for the path finds `post_mortems`. Both are correct.

## Steps

1. **Find the report.** `listRetrospectiveReports` (`GET /v1/post_mortems/reports`), filtering to the
   incident you care about. Confirm the incident itself with `getIncident`.
2. **See what needs answering.** `listRetrospectiveQuestions` returns the org's configured
   questions; `listRetrospectiveMetrics` returns the computed timing metrics (MTTx) the report
   carries.
3. **Fill fields one at a time.** `updateRetrospectiveField`
   (`PATCH /v1/post_mortems/reports/{report_id}/fields/{field_id}`). Each field is addressed
   individually — there is no bulk-update operation.
4. **Publish.** `publishRetrospectiveReport`
   (`POST /v1/post_mortems/reports/{report_id}/publish`).

## Publish is one-way

There is **no unpublish operation** in the published spec. Once a retrospective is published it is
visible to whoever the org has granted access. Confirm the content with a human before step 4.

## The MCP shortcut, and its catch

FireHydrant's official MCP server (`npx firehydrant-mcp start --api-key ...`) exposes two
retrospective tools — `list-retros-by-incident` and `update-retrospective-field` — that are backed by
`/v1/incidents/{incident_id}/retrospectives...`, a path shape that does **not** appear in the
published OpenAPI. If you are driving MCP, you get the incident-nested route; if you are driving REST
from the spec, you get `/v1/post_mortems/reports`. They are the same data reached two ways. See
`mcp/firehydrant-tool-crosswalk.yml`.
