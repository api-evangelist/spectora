# Spectora (spectora)

Spectora is home inspection software used by more than 10,000 inspectors to build inspection reports, schedule jobs, manage clients and agents, run a website, take payments, and automate follow-up.

**Access model (important):** Spectora does **not** publish a public, self-serve developer REST API. As of this writing there is no developer portal, no API reference, no OpenAPI, no base URL, and no self-serve API keys for third-party programmatic access. This entry is an honest stub that documents the integration surface Spectora actually offers rather than fabricating endpoints.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/spectora/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/spectora/refs/heads/main/apis.yml)

## How you integrate with Spectora

There is no callable public API. Outside connectivity is delivered three ways, all of them configuration-time and (for events) one-way outbound:

1. **Zapier integration** — requires the paid **Spectora Advanced** add-on. Documented triggers are contact-oriented only: *Agent contacts created/updated* and *Client contacts created/updated*. It pushes new/updated contact data from Spectora out to other Zapier-connected apps. Auth is a Spectora-account connect flow inside Zapier, not a developer API key.
2. **Outbound webhooks (Advanced Actions)** — configure an action that fires on an event (e.g. an inspection scheduled by a first-time client) and POSTs data to a URL you supply (Zapier, Make, or your own endpoint). Outbound, one-way, no published payload schema.
3. **Named partner integrations** — a fixed, vendor-built catalog: QuickBooks Online, Google Calendar, Google Drive, Mailchimp, HomeBinder, RecallChek, Repair Pricer, Blipp Reviews, InterNACHI BuyBack, and call-center partners (Inspector Call Center, America's Call Center). These are built by Spectora/its partners, not exposed as an open API.

None of these use WebSocket (ws:// or wss://). See [review.yml](review.yml) for the full assessment.

## Tags

- Home Inspection
- Inspection Reports
- Field Services
- Real Estate
- Scheduling
- Webhooks
- Zapier
- No Public API

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## APIs

None documented. Spectora exposes no public, self-serve developer API, so no APIs are listed in `apis.yml`. If Spectora publishes a developer API in the future, this entry should be updated with real endpoints, an OpenAPI definition, and a base URL.

## Pricing

Spectora is a **per-inspector subscription**, not a metered API. See [plans/spectora-plans-pricing.yml](plans/spectora-plans-pricing.yml).

- **Base (first inspector):** ~$109/month (~$1,099/year annual) — templates, mobile app, website, scheduling, payments, support; no per-inspection fee, no contract.
- **Additional inspector:** ~$89/month (~$828/year) per seat.
- **Spectora Advanced (add-on):** ~$3-4 per published inspection — automation, CRM, business insights, and the Zapier/webhook integration surface.
- **Free trial:** no credit card required.

## Common Properties

- [Website](https://www.spectora.com/)
- [LinkedIn](https://www.linkedin.com/company/spectora-home-inspection-software)
- [Documentation (Integrations)](https://support.spectora.com/en/collections/903201-integrations)
- [Zapier](https://support.spectora.com/en/articles/5949874-using-the-zapier-integration)
- [Webhooks (Advanced Actions)](https://support.spectora.com/en/articles/6723168-advanced-actions-choose-an-action-and-add-details)
- [Plans](plans/spectora-plans-pricing.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
