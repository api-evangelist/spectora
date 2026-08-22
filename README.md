# Spectora (spectora)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
