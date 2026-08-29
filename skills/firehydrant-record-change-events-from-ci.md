---
name: Record change events from CI into FireHydrant
description: >-
  Push deploys, builds and image creations into FireHydrant's change tracking so an incident can be
  correlated to what shipped, using the REST change-event surface or the fhcli binary.
api: openapi/firehydrant-api-openapi.yml
operations:
  - listServices
  - listEnvironments
  - createChangeEvent
  - listChangeEvents
  - getChangeEvent
---

# Record change events from CI into FireHydrant

Change events are what make "what changed just before this broke?" answerable. This is the highest
value, lowest risk write in the whole API: it is additive, it touches no live incident, and a wrong
one can be removed with `deleteChangeEvent`.

## Steps

1. **Resolve the targets.** `listServices` and `listEnvironments` to turn names from your CI config
   into UUIDs. Cache these — they change rarely and the rate limit is tight.
2. **Write the event.** `createChangeEvent` (`POST /v1/changes/events`) with a summary, the
   `services` and `environments` it touched, and a `labels` map. Put the things you will want to
   pivot on in labels: `type=deployment`, `author=...`, the git SHA, the image URL.
3. **Verify.** `listChangeEvents` filtered to the service, or `getChangeEvent` on the returned id.
   Note the docs' own warning: **list responses omit attachments and related changes** — fetch the
   individual event when you need the whole object.

## The shortcut

If you are inside a CI job rather than an agent loop, FireHydrant ships `fhcli` for exactly this:

```
fhcli event "Deployed api v42" --labels type=deployment,author="ci" --environment production --service api
fhcli execute --service=api --identities "revision=$GIT_SHA,image=$IMAGE" -- docker build -t app .
```

It reads `FH_API_KEY` from the environment or `apiKey:` from `~/firehydrant.cfg`. See
`cli/firehydrant-cli.yml`.

## Conventions that bite here

- Pagination is `page` / `per_page` (default 20, max 200) with a `pagination` object carrying
  `count`, `page`, `items`, `pages`, `last`, `prev`, `next`.
- No idempotency key. A retried deploy notification creates a second change event; de-duplicate by
  listing on the service and matching your label before writing.
