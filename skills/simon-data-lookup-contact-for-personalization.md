---
name: Look up a Simon Data contact for personalisation
description: >-
  Fetch one contact profile from the Simon Audience API at request time to personalise content, and stay inside the
  organisation-wide rate limit while doing it.
api: openapi/simon-data-audience-api-openapi.yml
operations: [get-a-contact]
generated: '2026-08-13'
method: generated
source: openapi/simon-data-audience-api-openapi.yml, https://docs.simondata.com/reference/getting-started
---

# Look up a Simon Data contact for personalisation

One operation: `get-a-contact`, `GET https://api.simondata.com/audience/v2/contacts`.

## 1. Preconditions

The Audience API is an **optional premium feature**. Access, and the bearer token, come from a Simon Client Solutions
Manager — there is no self-serve key and no OAuth flow. Simon's own guidance:

- Call it from **server-side applications only**. Build a personalisation service other apps call; do not put the token
  in client code.
- Keep a small pool of tokens and rotate them on a schedule.
- Rotate or delete a token through a support ticket. Reference it by its last three digits — never paste a token into
  email or Slack.

## 2. Authenticate

```
Authorization: Bearer <YOUR_TOKEN>
Accept: application/json
```

## 3. Ask for a contact

Both parameters are required.

- `identity` — `identifier:id`. Supported identifiers: `simonid`, `email`, `email-hash`,
  `primary-subscriber-key` (Salesforce Marketing Cloud), `riid` (Responsys), `zendeskid` (Zendesk).
- `fields` — comma-separated list of contact fields to return, e.g. `first_name,flow_variant_membership`.

```
GET /audience/v2/contacts?identity=email:tom@hello.com&fields=first_name,flow_variant_membership
```

Exactly one contact comes back per call. There is no list endpoint, no pagination and no batch lookup — plan for
one request per person.

## 4. Read the response

```json
{"status": "success", "contact": {"email_address": "tom@hello.com", "first_name": "Tom", "flow_variant_membership": ["142309", "203850-Variant A"]}}
```

The keys are **tenant-specific**. A field is only returned if it is configured as *content* in that Simon account, so
do not hard-code an expected schema — request the fields you need and treat anything missing as absent.

## 5. Respect the rate limit

**50 requests per second across the whole organisation**, aggregated over every bearer token the organisation holds —
issuing more tokens does not buy more throughput. Exhaustion returns `429` with an empty body, and Simon publishes no
`RateLimit-*` or `Retry-After` headers, so you cannot read remaining budget from a response. Meter on your side:
cache hot profiles, coalesce duplicate lookups, and back off on `429`. A limit increase is a conversation with the
account manager, not a setting.

## 6. Handle the errors

`400` commonly means the contact does not exist. `403`, `429` and `500` return empty bodies. There is no error code
vocabulary and no request id to quote in support — log the identity, the fields requested and the timestamp yourself.
