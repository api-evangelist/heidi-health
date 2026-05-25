# Heidi Health (heidi-health)

Heidi Health is a Melbourne, Australia-founded AI care partner for clinicians, founded in 2019 by Dr. Tom Kelly (CEO), Waleed Mussa (CFO), and Yu Liu (CTO). The product began as an ambient AI medical scribe and now spans four capability surfaces: **Scribe** (real-time consult notes from audio), **Evidence** (clinical decision support with citations and CPD/CME tracking), **Remote** (a 21-gram wearable microphone with on-device encryption for offline ambient capture), and **Comms** (clinical communications). Heidi is used by more than one million clinicians across 50+ countries and exposes a public **Heidi API** plus embeddable **Heidi Widget** for EHRs, telehealth platforms, and partner integrations.

**URL:** [Visit APIs.yml](https://raw.githubusercontent.com/api-evangelist/heidi-health/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-heidi-health&utm_content=repo)

## Tags

Healthcare, Health Tech, AI Medical Scribe, Ambient AI, Clinical Documentation, Clinical Decision Support, Artificial Intelligence, Speech To Text, Transcription, EHR Integration, Electronic Health Records, Telehealth, Clinical Coding, ICD-10, SNOMED, HIPAA, GDPR, SOC 2, ISO 27001, ISO 42001, Wearables, Voice, Audio, Australia, Melbourne

## Timestamps

- **Created:** 2026-05-24
- **Modified:** 2026-05-24

## Company

| Item | Value |
|---|---|
| Founded | 2019 |
| HQ | Melbourne, Australia (global operations) |
| Founders | Dr. Tom Kelly (CEO), Waleed Mussa (CFO), Yu Liu (CTO) |
| Clinicians | 1M+ globally |
| Reach | 50+ countries |
| Clinician hours returned | 18M+ to date |
| Funding | ~$80M (Seed + $10M Series A [Blackbird] + $65M Series B [Point72 PI, Blackbird, Headline, Latitude]) |
| Strategic partnership | R1 RCM (US revenue cycle management) |

## Compliance

SOC 2, ISO 27001, ISO 42001, HIPAA, GDPR, APP (Australia), PIPEDA (Canada), NHS (UK), Cyber Essentials+, UKCA, Swiss FDPA. Heidi does **not** train its models on clinician data.

## APIs

### Heidi Authentication API
Exchange a tenant Heidi API key for a short-lived bearer JWT bound to an EHR user (email + `third_party_internal_id`). Tokens carry an ISO 8601 `expiration_time` and are sent as `Authorization: Bearer <token>` on every subsequent call.

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/authentication](https://www.heidihealth.com/developers/heidi-api/authentication)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [Naftiko Capability](capabilities/authentication.yaml)
- [Example — Get JWT](examples/heidi-health-get-jwt-example.json)

### Heidi Templates API
List consult-note templates available to the authenticated API user (Heidi-authored, organisation-shared, or private).

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/templates](https://www.heidihealth.com/developers/heidi-api/templates)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [Naftiko Capability](capabilities/templates.yaml)

### Heidi Patient Profiles API
CRUD plus batch-delete and link-session operations for longitudinal patient records. Profiles can carry EHR patient identifiers and provider context so sessions inherit patient history.

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/patient-profiles](https://www.heidihealth.com/developers/heidi-api/patient-profiles)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [JSON Schema — Patient Profile](json-schema/heidi-health-patient-profile-schema.json)
- [Naftiko Capability](capabilities/patient-profiles.yaml)

### Heidi Sessions API
Create, retrieve, update, and list clinical sessions — the central object that ties together transcription, consult notes, documents, clinician notes, language settings, EHR identifiers, consent state, and linked context sessions.

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/sessions/overview](https://www.heidihealth.com/developers/heidi-api/sessions/overview)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [JSON Schema — Session](json-schema/heidi-health-session-schema.json)
- [JSON Structure — Session Aggregate](json-structure/heidi-health-session-structure.json)
- [Naftiko Capability](capabilities/sessions.yaml)
- [Example — Create Session](examples/heidi-health-create-session-example.json)

### Heidi Session Context API
Attach clinician notes, link prior sessions, and upload context documents (PDF, JPG, PNG, DOCX, DOC) so Heidi grounds generation in the relevant patient background.

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/sessions/context](https://www.heidihealth.com/developers/heidi-api/sessions/context)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [Naftiko Capability](capabilities/session-context.yaml)

### Heidi Session Coding API
Generate clinical codes for a session across **ICD-10, ICD-10-CM, ICD-9, ICD-9-CM, SNOMED, SNOMED-CT, OPCS-410, ACHI-13, CPT-2025**, with primary code, similar candidates, and citation references back to the transcript and consult-note text.

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/sessions/coding](https://www.heidihealth.com/developers/heidi-api/sessions/coding)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [JSON Schema — Clinical Code](json-schema/heidi-health-clinical-code-schema.json)
- [Naftiko Capability](capabilities/clinical-coding.yaml)
- [Example — Get Clinical Codes](examples/heidi-health-get-clinical-codes-example.json)

### Heidi Transcription API
Submit consultation audio as a single uploaded file (lazy transcription on the next `GET`) or in 45-second to 1-minute chunks for live ambient capture, then retrieve either the finalised transcript or a live chunked transcript with per-chunk status and source provenance.

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/transcription](https://www.heidihealth.com/developers/heidi-api/transcription)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [JSON Schema — Transcript](json-schema/heidi-health-transcript-schema.json)
- [Naftiko Capability](capabilities/transcription.yaml)

### Heidi Consult Notes API
Generate streamed consult notes against a Heidi or organisation template, or a custom client-supplied JSON template, with voice-style controls (`GOLDILOCKS`, `DETAILED`, `BRIEF`, `SUPER_DETAILED`, `MY_VOICE`), brain selection (`LEFT`/`RIGHT`), and Markdown or HTML output.

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/consult-notes](https://www.heidihealth.com/developers/heidi-api/consult-notes)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [JSON Schema — Consult Note](json-schema/heidi-health-consult-note-schema.json)
- [Naftiko Capability](capabilities/consult-notes.yaml)
- [Example — Generate Consult Note](examples/heidi-health-generate-consult-note-example.json)

### Heidi Documents API
Create and retrieve auxiliary template-driven documents associated with a session (referral letters, patient handouts, billing summaries), using the same voice-style, brain, and content-type controls as consult notes.

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/documents](https://www.heidihealth.com/developers/heidi-api/documents)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [JSON Schema — Document](json-schema/heidi-health-document-schema.json)
- [Naftiko Capability](capabilities/documents.yaml)

### Heidi Ask Heidi API
Stream AI-assistant responses scoped to a specific session, taking a free-form instruction, contextual content (Markdown or HTML), and returning the reply as a sequence of `{"data": "..."}` JSON chunks for incremental UI rendering.

**Human URL:** [https://www.heidihealth.com/developers/heidi-api/ask-heidi](https://www.heidihealth.com/developers/heidi-api/ask-heidi)

- [OpenAPI](openapi/heidi-health-openapi.yml)
- [Naftiko Capability](capabilities/ask-heidi.yaml)

### Heidi Widget SDK
Embeddable JavaScript widget for dropping Heidi's ambient documentation experience directly into any web-based EHR, with documented initialisation options, methods/callbacks, patient-information parameters, and TypeScript types.

**Human URL:** [https://www.heidihealth.com/developers/widget/overview](https://www.heidihealth.com/developers/widget/overview)

- [Overview](https://www.heidihealth.com/developers/widget/overview)
- [Install the widget](https://www.heidihealth.com/developers/widget/install-the-widget)
- [Initialisation options](https://www.heidihealth.com/developers/widget/sdk-specification/initialisation-options)
- [Methods and callbacks](https://www.heidihealth.com/developers/widget/sdk-specification/methods-and-callbacks)
- [Patient information](https://www.heidihealth.com/developers/widget/sdk-specification/patient-information)
- [Types](https://www.heidihealth.com/developers/widget/sdk-specification/types)

## Plans, Rate Limits & FinOps

- [Plans & Pricing](plans/heidi-health-plans-pricing.yml) — Free, Evidence Plus, Clinician, Enterprise (per-clinician/month; 14-day trials on paid tiers)
- [Rate Limits](rate-limits/heidi-health-rate-limits.yml) — Per-API-key throttling; JWT lifetimes; 45s–1min chunking guidance; lazy transcription; streamed generation; pagination
- [FinOps](finops/heidi-health-finops.yml) — FOCUS-aligned view of Heidi's subscription billing surface

## Artifacts

- [OpenAPI 3.1](openapi/heidi-health-openapi.yml)
- [JSON-LD Context](json-ld/heidi-health-context.jsonld)
- [JSON Structure — Session Aggregate](json-structure/heidi-health-session-structure.json)
- [Spectral Ruleset](rules/heidi-health-rules.yml)
- [Vocabulary](vocabulary/heidi-health-vocabulary.yml)

## Common Properties

- [Website](https://www.heidihealth.com)
- [Developers](https://www.heidihealth.com/developers)
- [Pricing](https://www.heidihealth.com/pricing)
- [Changelog](https://www.heidihealth.com/changelog)
- [Blog](https://www.heidihealth.com/blog)
- [Status](https://status.heidihealth.com)
- [Trust Center](https://trust.heidihealth.com)
- [Help](https://support.heidihealth.com)
- [Integrations](https://www.heidihealth.com/integrations)
- [Partners](https://www.heidihealth.com/partners)
- [Customer Stories](https://www.heidihealth.com/customer-stories)
- [Company](https://www.heidihealth.com/company)
- [Careers](https://www.heidihealth.com/careers)
- [Contact](https://www.heidihealth.com/contact)

## Maintainer

- **Kin Lane** — `kin@apievangelist.com`
