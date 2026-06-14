# FireHydrant GraphQL Schema

## Overview

FireHydrant is a reliability operations and incident management platform. This conceptual GraphQL schema models the core resources available through the FireHydrant REST API at https://developers.firehydrant.io/, translated into a GraphQL type system for query, mutation, and subscription patterns.

FireHydrant enables engineering teams to declare services and environments, define runbooks, manage on-call schedules, and coordinate incident response from detection through retrospective. The schema below captures incidents and their lifecycle, teams, users, integrations, alerting, status pages, and AI-powered retrospectives.

## Schema Source

- REST API Reference: https://developers.firehydrant.io/
- Developer Documentation: https://docs.firehydrant.io
- Provider Website: https://firehydrant.com

## Root Operations

### Query

- `incident(id: ID!)` — Fetch a single incident by ID.
- `incidents(filter: IncidentFilter, page: Int, perPage: Int)` — List incidents with optional filtering.
- `service(id: ID!)` — Fetch a service by ID.
- `services(page: Int, perPage: Int)` — List all services.
- `team(id: ID!)` — Fetch a team by ID.
- `teams(page: Int, perPage: Int)` — List all teams.
- `user(id: ID!)` — Fetch a user by ID.
- `users(page: Int, perPage: Int)` — List users.
- `runbook(id: ID!)` — Fetch a runbook by ID.
- `runbooks(page: Int, perPage: Int)` — List runbooks.
- `environment(id: ID!)` — Fetch an environment.
- `environments(page: Int, perPage: Int)` — List environments.
- `schedule(id: ID!)` — Fetch an on-call schedule.
- `schedules(page: Int, perPage: Int)` — List on-call schedules.
- `statusPage(id: ID!)` — Fetch a status page configuration.
- `statusPages(page: Int, perPage: Int)` — List status pages.
- `alert(id: ID!)` — Fetch an alert by ID.
- `alerts(page: Int, perPage: Int)` — List alerts.
- `retrospective(id: ID!)` — Fetch a retrospective.
- `webhook(id: ID!)` — Fetch a webhook.
- `webhooks(page: Int, perPage: Int)` — List webhooks.
- `integration(id: ID!)` — Fetch an integration.
- `integrations(page: Int, perPage: Int)` — List integrations.
- `changeEvent(id: ID!)` — Fetch a change event.
- `changeEvents(page: Int, perPage: Int)` — List change events.
- `functionality(id: ID!)` — Fetch a functionality.
- `functionalities(page: Int, perPage: Int)` — List functionalities.
- `apiKey(id: ID!)` — Fetch an API key.
- `apiKeys(page: Int, perPage: Int)` — List API keys.

### Mutation

- `createIncident(input: CreateIncidentInput!)` — Open a new incident.
- `updateIncident(id: ID!, input: UpdateIncidentInput!)` — Update incident details.
- `resolveIncident(id: ID!)` — Mark an incident resolved.
- `addIncidentUpdate(incidentId: ID!, input: IncidentUpdateInput!)` — Post an update to an incident.
- `createTask(incidentId: ID!, input: TaskInput!)` — Create a task on an incident.
- `updateTask(id: ID!, input: TaskInput!)` — Update a task.
- `createFollowUp(incidentId: ID!, input: FollowUpInput!)` — Log a follow-up action.
- `updateFollowUp(id: ID!, input: FollowUpInput!)` — Update a follow-up.
- `createRunbook(input: RunbookInput!)` — Create a runbook.
- `attachRunbook(incidentId: ID!, runbookId: ID!)` — Attach a runbook to an incident.
- `createService(input: ServiceInput!)` — Register a service.
- `updateService(id: ID!, input: ServiceInput!)` — Update a service.
- `createTeam(input: TeamInput!)` — Create a team.
- `addTeamMember(teamId: ID!, userId: ID!)` — Add a user to a team.
- `createWebhook(input: WebhookInput!)` — Register a webhook.
- `deleteWebhook(id: ID!)` — Remove a webhook.
- `createChangeEvent(input: ChangeEventInput!)` — Record a change event.
- `createSchedule(input: ScheduleInput!)` — Create an on-call schedule.
- `triggerAlert(input: AlertInput!)` — Trigger an alert.
- `createStatusPage(input: StatusPageInput!)` — Create a status page.
- `createRetrospective(incidentId: ID!)` — Initiate a retrospective for an incident.
- `createAPIKey(input: APIKeyInput!)` — Create a new API key.
- `revokeAPIKey(id: ID!)` — Revoke an API key.

### Subscription

- `incidentCreated` — Stream new incidents as they are opened.
- `incidentUpdated(id: ID!)` — Stream updates to a specific incident.
- `alertTriggered` — Stream incoming alerts.

## Type Summary

The schema defines 60 named types covering incidents, teams, services, runbooks, schedules, alerts, status pages, retrospectives, integrations, webhooks, change events, users, API keys, and FireHydrant AI features.
