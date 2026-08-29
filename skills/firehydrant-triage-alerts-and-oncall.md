---
name: Triage FireHydrant Signals alerts and find who is on call
description: >-
  Read the alert stream, inspect a single alert and its processing log, see which alerts are already
  attached to an incident, and resolve the current on-call responder before escalating.
api: openapi/firehydrant-api-openapi.yml
operations:
  - listAlerts
  - getAlert
  - listIncidentAlerts
  - listSignalsOnCall
  - listSignalEventSources
  - listTeams
---

# Triage FireHydrant Signals alerts and find who is on call

## Steps

1. **Read the stream.** `listAlerts` (`GET /v1/alerts`) returns both Signals alerts and third-party
   alerts FireHydrant has ingested. Page with `page`/`per_page`.
2. **Inspect one.** `getAlert` for the full alert. If you need to know why an alert did or did not
   fire a rule, the processing log for that alert is the record to read.
3. **Check for existing coverage.** `listIncidentAlerts` on a candidate incident tells you whether
   this alert is already attached — do not open a duplicate incident for an alert someone else is
   already working.
4. **Find the responder.** `listSignalsOnCall` (`GET /v1/signals_on_call`) is the authoritative
   current on-call view across schedules and escalation policies. `listTeams` maps team UUIDs to
   names.
5. **Understand the source.** `listSignalEventSources` tells you which integration fed the alert —
   Datadog, Grafana, Alertmanager, CloudWatch, Sentry, a generic webhook, and 15 more.

## Escalation is irreversible — stop here

FireHydrant documents an endpoint that **pages** a user, team, on-call schedule or escalation policy
(`create_signals_page` in the API reference). It dispatches a real push, SMS or voice call to a human
being at whatever hour it is where they are, and **there is no un-page operation**.

- It is not present in the published OpenAPI captured in this repo, so no operationId is claimed for
  it here.
- Treat paging as requiring human confirmation. Reading the on-call rota (step 4) is safe;
  ringing the person on it is not.

## Conventions

- Read-only work belongs on `https://api-read.firehydrant.io/v1`. Every step above is a GET, so pin
  this whole skill to the read host and the risk of an accidental write drops to zero.
- 50 requests per 10 seconds per account, shared. Alert streams are the easiest way to burn that
  budget — set `per_page` high (max 200) rather than paging in small increments.
