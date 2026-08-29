---
name: Provision FireHydrant users and teams over SCIM 2.0
description: >-
  Create and update FireHydrant users and teams through the SCIM 2.0 surface, so identity lifecycle
  is driven from the IdP rather than by hand.
api: openapi/firehydrant-api-openapi.yml
operations:
  - getScimUsers
  - createScimUser
  - getScimGroups
  - createScimGroup
---

# Provision FireHydrant users and teams over SCIM 2.0

SCIM is an **Enterprise-plan feature**. On Free and Pro these endpoints will not be available to you.

## What FireHydrant's SCIM actually is

- Paths are the standard shape: `/v1/scim/v2/Users`, `/v1/scim/v2/Users/{id}`,
  `/v1/scim/v2/Groups`, `/v1/scim/v2/Groups/{id}`.
- Request bodies use the `application/scim+json` media type — set the `Content-Type` accordingly,
  not `application/json`.
- A SCIM **Group is a FireHydrant Team**. The spec says so in as many words: "Colloquial for Group in
  the SCIM protocol". Group `members[].value` is the user's UUID.
- User updates use the RFC 7644 PATCH shape: an `Operations[]` array of `{op, path}` where `op` is
  `add`, `remove` or `replace`.

## Steps

1. `getScimUsers` to read the current population before writing anything.
2. `createScimUser` to provision. The spec notes this "will provision the User, which allows them to
   accept their account through their IDP or via the Forgot Password flow" — the user gets contacted.
3. `createScimGroup` with `displayName` and `members[]` to create a Team with its roster.
4. To change a team roster, `PUT /v1/scim/v2/Groups/{id}` — and read the warning in the spec first:
   **any member missing from the payload is removed from the team.** It is a full replace, not a
   merge. Send the complete intended roster every time.

## Where FireHydrant's SCIM stops short of the standard

- No `/ServiceProviderConfig`, `/Schemas` or `/ResourceTypes` discovery endpoints — a SCIM client
  that negotiates capability before provisioning has nothing to read.
- No `urn:ietf:params:scim:schemas:*` declarations in the request/response models.

Plan for a bespoke connector rather than pointing a strict SCIM client at it unconfigured. See
`conformance/firehydrant-conformance.yml`.
