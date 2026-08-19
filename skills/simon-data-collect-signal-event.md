---
name: Collect a Simon Signal event
description: >-
  Send a behavioural or transactional event into Simon Data's Simon Signal pipeline so it can drive segmentation,
  triggered flows and journeys. Covers the envelope every event needs, choosing the right event type, and the silent
  failure mode that loses events when debug mode is off.
api: openapi/simon-data-event-ingestion-openapi.yml
operations: [collectEvent]
generated: '2026-08-13'
method: generated
source: openapi/simon-data-event-ingestion-openapi.yml, https://docs.simondata.com/reference/event-ingestion-api
---

# Collect a Simon Signal event

One event per request. There is exactly one operation — `collectEvent`, `POST /events/v1/collect`.

## 1. Pick the environment

| Environment | Base |
|---|---|
| Production | `https://simonsignal.com/http/v1` |
| Staging | `https://staging.simonsignal.com/http/v1` |
| Development | `https://dev.simonsignal.com/http/v1` |

Build and verify against development or staging first. There are no test credentials — you use the same
`partnerId` and `partnerSecret` your Simon account was issued, pointed at a non-production host.

## 2. Build the envelope

Every payload, whatever the event type, carries the `core_event` fields:

- `partnerId` — required. Simon's identifier for your site.
- `partnerSecret` — required. The shared secret; this is the authentication. There is no `Authorization` header.
- `clientId` — required. Device identifier, or a session identifier if you have no stable device id. Max 45 characters.
- `sentAt` — required. Epoch **milliseconds**, not seconds.
- `type` — required. Either `track` or `identify`. Nothing else validates.
- `context` — required object. Set `context.debug` (see step 4), plus `name`/`version` for your client library and
  `page.url`, `userAgent`, `device.type` where you have them.
- `ipAddress`, `timezone` — optional.

## 3. Pick the event shape

`type: identify` resolves a person and carries `traits` (`email` is required inside `traits`).
`type: track` carries a behaviour. The fourteen published payload schemas are the `oneOf` branches of
`collectEvent`'s request body — read the exact fields from `components.schemas` in the spec:

`identify_event`, `authentication_event`, `registration_event`, `page_view_event`, `product_view_event`,
`search_event`, `favorite_event`, `waitlist_event`, `cart_event`, `add_to_cart_event`, `remove_from_cart_event`,
`update_cart_event`, `complete_transaction_event`, `custom_event`.

Cart-shaped events (`cart`, `add_to_cart`, `remove_from_cart`, `update_cart`, `complete_transaction`) carry
`cartitem_with_quantity` line items; `product_view` and `favorite` carry a single `cartitem`.

Reach for `custom_event` only when no published schema fits — custom events still have to be configured on the
Simon side before they can trigger anything.

## 4. Turn debug on before you trust a 200

This is the rule that matters most on this API. With `context.debug` false, **validation exceptions are silent**:
the request returns success and the event is discarded downstream. With `context.debug` true, a bad payload comes
back as `412` with a message such as `Unknown event type: collect.track`.

Never validate an integration against a non-debug 200.

## 5. Handle the responses

| Status | Meaning | What to do |
|---|---|---|
| 200 | Accepted. No JSON body. | Nothing — but see step 4 before believing it. |
| 400 | `Invalid JSON body` | Fix serialisation. |
| 401 | `Unauthorized` | Wrong or missing `partnerSecret`. |
| 403 | `Forbidden` | Credentials valid, call not permitted. |
| 412 | Validation failure (debug mode only) | Read the `error` string and fix the payload. |
| 500 | `Internal Server Error` | Retry with exponential backoff. |

Errors are a flat `{"error": "<message>"}` object — not RFC 9457 problem details, and with no machine-readable code.

## 6. Retries and size

- Events over **100 KB** are rejected.
- Simon documents **no idempotency key** and no dedupe window. A retried `collectEvent` is a second event. Retry only
  on `5xx`, and accept that a timeout may already have been recorded.
