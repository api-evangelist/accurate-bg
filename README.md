# Accurate Background (accurate-bg)

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

Accurate Background is an employment background screening and workforce compliance company. Its **Accurate API (v3)** lets HR platforms, ATS/HRIS vendors, and staffing tools embed background checks - criminal searches, SSN trace, employment and education verification, drug and health screening, driving records, identity and work authorization (Form I-9, E-Verify), and international screening - directly into their own web and mobile applications.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/accurate-bg/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/accurate-bg/refs/heads/main/apis.yml)

## Access Model

This is a **real, documented public API** - not a fully gated partner API. Development is self-serve:

- **Free developer account + sandbox** — sign up at [developer.accuratebackground.com](https://developer.accuratebackground.com/) and test the API immediately without contacting sales.
- **Authentication** — API credentials are a `ClientID` / `ClientSecret` pair issued from the developer portal, exchanged (HTTP Basic) for an access token that authorizes requests (OAuth2 client-credentials style). The `/alive` connectivity check needs no auth.
- **Production** — running real background checks is provisioned under a screening services agreement (contact sales). Billing is **per screening** (per package plus pass-through court/verification fees); Accurate does not publish public list pricing.

- **Base URL:** `https://api.accuratebackground.com/v3`
- **API reference:** [accurate.readme.io/reference](https://accurate.readme.io/reference) (endpoint index at `accurate.readme.io/llms.txt`)

The endpoints below are drawn from Accurate's own published documentation. The bundled OpenAPI (`openapi/accurate-bg-openapi.yml`) was authored by API Evangelist from that documentation: paths and HTTP methods reflect the documented endpoints, while request/response schemas are summarized rather than exhaustively modeled.

## Tags

- Background Checks
- Employment Screening
- Identity Verification
- Compliance
- HR Tech
- Screening

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Accurate Candidates API

Create, retrieve, list, and update the candidates (screening subjects) that background checks are run against. A candidate is created first and then referenced in an order-creation payload; candidate updates apply to future orders only.

- **Base URL:** `https://api.accuratebackground.com/v3`
- [Documentation](https://developer.accuratebackground.com/) · [API Reference](https://accurate.readme.io/reference) · [OpenAPI](openapi/accurate-bg-openapi.yml)

### Accurate Orders API

Place and manage background-check orders against a candidate - create an order for a chosen package, list and retrieve orders, check estimated completion time (ETA), review order changes, reinitiate cancelled interactive orders, and resend candidate invitations.

- **Base URL:** `https://api.accuratebackground.com/v3`
- [Documentation](https://developer.accuratebackground.com/) · [API Reference](https://accurate.readme.io/reference) · [OpenAPI](openapi/accurate-bg-openapi.yml)

### Accurate Packages API

List the active screening packages configured on an account and retrieve a package by type. Packages bundle the individual searches (criminal, verification, drug, MVR, international, etc.) that an order runs; integrators can use preset or account-configured custom packages.

- **Base URL:** `https://api.accuratebackground.com/v3`
- [Documentation](https://developer.accuratebackground.com/) · [API Reference](https://accurate.readme.io/reference) · [OpenAPI](openapi/accurate-bg-openapi.yml)

### Accurate Reports API

Retrieve completed screening results. The report endpoint returns the finished background-check report for an order as a PDF or base64-encoded HTML once the order is complete, and exposes the candidate invitation link for interactive orders.

- **Base URL:** `https://api.accuratebackground.com/v3`
- [Documentation](https://developer.accuratebackground.com/) · [API Reference](https://accurate.readme.io/reference) · [OpenAPI](openapi/accurate-bg-openapi.yml)

### Accurate Documents API

Attach and manage supporting documents on an order - upload PDF, JPG, PNG, DOC, or DOCX files (up to 15MB), list an order's documents, and get, download, or delete an individual document.

- **Base URL:** `https://api.accuratebackground.com/v3`
- [Documentation](https://developer.accuratebackground.com/) · [API Reference](https://accurate.readme.io/reference) · [OpenAPI](openapi/accurate-bg-openapi.yml)

### Accurate Adjudication API

Programmatically make an adjudication decision (pass/fail) on a completed order without logging into the portal, reassess an adjudication where jurisdiction rules require it, and update the position/job location that drives compliant decisioning.

- **Base URL:** `https://api.accuratebackground.com/v3`
- [Documentation](https://developer.accuratebackground.com/) · [API Reference](https://accurate.readme.io/reference) · [OpenAPI](openapi/accurate-bg-openapi.yml)

### Accurate Verifications API

Retrieve the history of employment and education verification attempts for an order, giving integrators visibility into outreach progress on verification-heavy screenings.

- **Base URL:** `https://api.accuratebackground.com/v3`
- [Documentation](https://developer.accuratebackground.com/) · [API Reference](https://accurate.readme.io/reference) · [OpenAPI](openapi/accurate-bg-openapi.yml)

### Accurate Notifications API

Trigger candidate-facing notifications, such as sending the screening subject a copy of their completed report, supporting compliant candidate communication workflows.

- **Base URL:** `https://api.accuratebackground.com/v3`
- [Documentation](https://developer.accuratebackground.com/) · [API Reference](https://accurate.readme.io/reference) · [OpenAPI](openapi/accurate-bg-openapi.yml)

### Accurate Webhooks

Webhook event notifications configured in the Accurate developer portal deliver order and report status updates (for example when an order completes) to a consumer-hosted HTTPS endpoint, so integrators do not have to poll for status. These are server-to-endpoint HTTP callbacks, configured per environment (sandbox and production) - not a WebSocket.

- **Base URL:** `https://api.accuratebackground.com/v3`
- [Documentation](https://developer.accuratebackground.com/) · [API Reference](https://accurate.readme.io/reference)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/accurate-background)
- [Website](https://www.accurate.com/)
- [Documentation](https://developer.accuratebackground.com/)
- [API Reference](https://accurate.readme.io/reference)
- [Sign Up](https://developer.accuratebackground.com/)
- [Plans](plans/accurate-bg-plans-pricing.yml)
- [Rate Limits](rate-limits/accurate-bg-rate-limits.yml)
- [Fin Ops](finops/accurate-bg-finops.yml)

## Review

Does Accurate Background expose a documented public WebSocket API? **No.** The Accurate API (v3) is request/response REST over HTTPS; asynchronous order/report status is delivered via webhook HTTP callbacks, not a WebSocket. See [`review.yml`](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
