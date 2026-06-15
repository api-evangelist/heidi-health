# Heidi Health (heidi-health)

Heidi Health is a Melbourne, Australia-founded AI care partner for clinicians, founded in 2019 by Dr. Tom Kelly (CEO), Waleed Mussa (CFO), and Yu Liu (CTO). The product began as an ambient AI medical scribe and now spans four capability surfaces: Scribe (real-time clinical documentation from audio), Evidence (clinical decision support and literature lookup with citations), Remote (a 21-gram wearable microphone with on-device encryption for offline ambient capture), and Comms (clinical communications). The platform is used by more than one million clinicians across 50+ countries spanning family medicine, specialists, nursing, mental health, allied health, dentistry, veterinary medicine, and trainees, and claims to have returned over 18 million hours of clinician time to date. Heidi exposes a public Heidi API and embeddable Heidi Widget that EHR vendors, telehealth platforms, and partners use to embed ambient documentation into their own workflows; documented integrations include Epic (Hyperspace/Hyperdrive/Haiku), Oracle Cerner (PowerChart/FirstNet), Athenahealth, eClinicalWorks (via Vim), Best Practice, Medical Director, Gentu, Cliniko, Halaxy, MediRecords, and many others. Heidi holds SOC 2, ISO 27001, ISO 42001, HIPAA, GDPR, APP, PIPEDA, NHS, Cyber Essentials+, UKCA, and Swiss FDPA attestations, has raised approximately $80M across Seed, Series A (Blackbird), and a $65M Series B led by Point72 Private Investments with Blackbird, Headline, and Latitude, and recently announced a strategic partnership with R1 RCM to embed Heidi into US revenue cycle management workflows.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/heidi-health/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/heidi-health/refs/heads/main/apis.yml)

## Scope

- **Position:** Provider
- **Access:** 3rd-Party

## Tags

- Healthcare
- Health Tech
- AI Medical Scribe
- Ambient AI
- Clinical Documentation
- Clinical Decision Support
- Artificial Intelligence
- Speech To Text
- Transcription
- EHR Integration
- Electronic Health Records
- Telehealth
- Clinical Coding
- ICD-10
- SNOMED
- HIPAA
- GDPR
- SOC 2
- ISO 27001
- ISO 42001
- Wearables
- Voice
- Audio
- Australia
- Melbourne

## Timestamps

- **Created:** 2026-05-24
- **Modified:** 2026-05-24

## APIs

### Heidi Authentication API

Exchange a tenant-scoped Heidi API key for a short-lived bearer JWT bound to an EHR user (identified by email plus third-party internal ID). The token is returned with its ISO 8601 expiration_time and used in the Authorization header on every subsequent Heidi API call.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/authentication](https://www.heidihealth.com/developers/heidi-api/authentication)

#### Tags

- Authentication
- Authorization
- JWT
- API Keys

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/authentication)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Example](examples/heidi-health-get-jwt-example.json)

### Heidi Templates API

List consult-note templates available to the authenticated API user, including Heidi-authored templates, organisation-shared templates, and private clinician templates, with their structure, category, HTML rendering, and authoring metadata.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/templates](https://www.heidihealth.com/developers/heidi-api/templates)

#### Tags

- Templates
- Consult Notes
- Documentation

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/templates)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Heidi Patient Profiles API

Manage longitudinal patient profiles independent of any single session, including create, update, list, retrieve, batch-delete, and link-sessions operations. Profiles can carry EHR patient identifiers and provider context so sessions inherit patient history.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/patient-profiles](https://www.heidihealth.com/developers/heidi-api/patient-profiles)

#### Tags

- Patients
- Patient Profiles
- EHR

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/patient-profiles)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/heidi-health-patient-profile-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Heidi Sessions API

Create, update, retrieve, and list clinical sessions — the central object that ties together transcription, consult notes, documents, clinician notes, language settings, EHR identifiers, consent state, and linked context sessions.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/sessions/overview](https://www.heidihealth.com/developers/heidi-api/sessions/overview)

#### Tags

- Sessions
- Clinical Encounters

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/sessions/overview)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/heidi-health-session-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Structure](json-structure/heidi-health-session-structure.json)
- [Example](examples/heidi-health-create-session-example.json)

### Heidi Session Context API

Attach contextual material to a session — free-text or Markdown clinician notes, links to prior patient sessions, and uploaded context documents (PDF, JPG, PNG, DOCX, DOC) — so Heidi's generation grounds the consult note in the relevant patient background.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/sessions/context](https://www.heidihealth.com/developers/heidi-api/sessions/context)

#### Tags

- Sessions
- Context
- Attachments
- Documents

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/sessions/context)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Heidi Session Coding API

Generate clinical codes for a session across ICD-10, ICD-10-CM, ICD-9, ICD-9-CM, SNOMED, SNOMED-CT, OPCS-410, ACHI-13, and CPT-2025, returning a primary code, similar candidate codes, and citation references back to the transcript and consult-note text.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/sessions/coding](https://www.heidihealth.com/developers/heidi-api/sessions/coding)

#### Tags

- Clinical Coding
- ICD-10
- SNOMED
- CPT
- Billing

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/sessions/coding)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/heidi-health-clinical-code-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/heidi-health-get-clinical-codes-example.json)

### Heidi Transcription API

Submit consultation audio either as a single uploaded file (lazy transcription on next GET) or in 45-second to 1-minute chunks for live ambient capture, and retrieve either the finalised transcript or a live chunked transcript stream with per-chunk status and source provenance.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/transcription](https://www.heidihealth.com/developers/heidi-api/transcription)

#### Tags

- Transcription
- Audio
- Speech To Text
- Streaming
- Ambient AI

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/transcription)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/heidi-health-transcript-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Heidi Consult Notes API

Generate streamed consult notes from a session's transcript and context, using either a Heidi or organisation template or a custom client-supplied JSON template, with voice-style controls (Goldilocks/Detailed/Brief/Super-Detailed/My Voice), brain selection (Left/Right), and Markdown or HTML output.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/consult-notes](https://www.heidihealth.com/developers/heidi-api/consult-notes)

#### Tags

- Consult Notes
- Generation
- Templates
- Streaming

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/consult-notes)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/heidi-health-consult-note-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/heidi-health-generate-consult-note-example.json)

### Heidi Documents API

Create and retrieve auxiliary template-driven documents associated with a session (referral letters, patient handouts, billing summaries, etc.) using the same voice-style, brain, and content-type controls as consult notes.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/documents](https://www.heidihealth.com/developers/heidi-api/documents)

#### Tags

- Documents
- Generation
- Templates

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/documents)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/heidi-health-document-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Heidi Ask Heidi API

Stream AI-assistant responses scoped to a specific session, taking a free-form instruction, contextual content (Markdown or HTML), and returning the generated reply as a sequence of JSON data chunks suitable for incremental UI rendering.

- **Human URL:** [https://www.heidihealth.com/developers/heidi-api/ask-heidi](https://www.heidihealth.com/developers/heidi-api/ask-heidi)

#### Tags

- Ask Heidi
- Assistant
- Streaming
- LLM

#### Properties

- [Documentation](https://www.heidihealth.com/developers/heidi-api/ask-heidi)
- [OpenAPI](openapi/heidi-health-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Heidi Widget SDK

Embeddable JavaScript widget for dropping Heidi's ambient documentation experience directly into a web-based EHR or clinical workflow with minimal engineering, with documented initialisation options, methods/callbacks, patient-information parameters, and TypeScript types.

- **Human URL:** [https://www.heidihealth.com/developers/widget/overview](https://www.heidihealth.com/developers/widget/overview)

#### Tags

- Widget
- SDK
- Embed
- JavaScript
- EHR Integration

#### Properties

- [Documentation](https://www.heidihealth.com/developers/widget/overview)
- [Documentation](https://www.heidihealth.com/developers/widget/install-the-widget)
- [Documentation](https://www.heidihealth.com/developers/widget/sdk-specification/initialisation-options)
- [Documentation](https://www.heidihealth.com/developers/widget/sdk-specification/methods-and-callbacks)
- [Documentation](https://www.heidihealth.com/developers/widget/sdk-specification/patient-information)
- [Documentation](https://www.heidihealth.com/developers/widget/sdk-specification/types)
- [Postman Collection](collections/heidi-health.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/heidi-health.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.heidihealth.com)
- [Portal](https://www.heidihealth.com/developers)
- [Documentation](https://www.heidihealth.com/developers/heidi-api/overview)
- [Documentation](https://www.heidihealth.com/developers/faq)
- [Sign Up](https://scribe.heidihealth.com/register)
- [Login](https://scribe.heidihealth.com/login)
- [Pricing](https://www.heidihealth.com/pricing)
- [Blog](https://www.heidihealth.com/blog)
- [Changelog](https://www.heidihealth.com/changelog)
- [Status Page](https://status.heidihealth.com)
- [Trust Center](https://trust.heidihealth.com)
- [Support](https://support.heidihealth.com)
- [Privacy Policy](https://www.heidihealth.com/legal/privacy-policy)
- [Terms of Service](https://www.heidihealth.com/legal/terms-of-service)
- [Acceptable Use](https://www.heidihealth.com/legal/usage-policy)
- [Compliance](https://www.heidihealth.com/compliance/hipaa)
- [Compliance](https://www.heidihealth.com/compliance/gdpr)
- [Compliance](https://www.heidihealth.com/compliance/uk)
- [Compliance](https://www.heidihealth.com/compliance/canada)
- [Compliance](https://www.heidihealth.com/compliance/au-nz)
- [Safety](https://www.heidihealth.com/safety)
- [Company](https://www.heidihealth.com/company)
- [Customers](https://www.heidihealth.com/customer-stories)
- [Press](https://www.heidihealth.com/media)
- [Careers](https://www.heidihealth.com/careers)
- [Contact](https://www.heidihealth.com/contact)
- [Contact](https://www.heidihealth.com/contact-sales)
- [Partners](https://www.heidihealth.com/partners)
- [Integrations](https://www.heidihealth.com/integrations)
- [Downloads](https://www.heidihealth.com/downloads)
- [System Requirements](https://www.heidihealth.com/system-requirements)
- [Templates](https://www.heidihealth.com/template-community)
- [R O I Calculator](https://www.heidihealth.com/roi-calculator)
- [Plans](plans/heidi-health-plans-pricing.yml)
- [Rate Limits](rate-limits/heidi-health-rate-limits.yml)
- [Fin Ops](finops/heidi-health-finops.yml)
- [JSON-LD](json-ld/heidi-health-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Vocabulary](vocabulary/heidi-health-vocabulary.yml)
- [Spectral Rules](rules/heidi-health-rules.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
