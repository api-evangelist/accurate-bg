# Accurate Background (accurate-bg)

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
