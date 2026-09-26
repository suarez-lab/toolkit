# Toolkit

**English** · [Español](README.es.md)

What we actually build with, counted from dependency manifests across our active
codebases — not from memory, and not from a list of things we once read about.

**Method.** Each figure is the number of distinct projects whose `package.json` or
`requirements.txt` declares that dependency, out of **19 projects that contain code**
(projects that are documentation or proposals only are excluded). Counting manifests
rather than mentions means a technology we integrated once and abandoned does not inflate
the number, and a technology we discuss in a design document but never shipped scores zero.

## Runtime and framework

| | Projects (of 19) |
| --- | --- |
| Node.js / TypeScript | 13 |
| Express | 9 |
| Python | 6 |
| FastAPI | 3 |
| Cloud Functions Gen2 (`functions-framework`) | 3 |
| Next.js | 3 |
| React Native / Expo | 1 |

## Google Cloud

| | Projects (of 19) |
| --- | --- |
| Firestore (`firebase-admin`) | 11 |
| Firestore (`google-cloud-firestore`, Python) | 4 |
| Cloud Storage | 5 |
| BigQuery | 2 |
| Secret Manager (SDK; most access is via ADC, not the SDK) | 1 |

Compute is Cloud Run and Cloud Functions Gen2 throughout, scale-to-zero by default.

## AI / LLM

| | Projects (of 19) |
| --- | --- |
| Gemini, `@google/generative-ai` (legacy SDK) | 6 |
| Gemini, `@google/genai` (current SDK) | 3 |
| Gemini, `google-generativeai` (Python) | 3 |

The two JavaScript SDKs coexist because a migration is in progress and we do it
incrementally rather than as a single cutover. We state that rather than hide it: a
codebase with one SDK everywhere and no migration history is usually a codebase that has
only ever been written once.

## Data and payments

| | Projects (of 19) |
| --- | --- |
| MySQL (`mysql2`, incl. AWS RDS Aurora over a VPC connector) | 2 |
| Stripe | 1 |

## Third-party platforms

WhatsApp gateways, Meta Graph / Instagram, Telegram (operational alerting), EspoCRM,
SendGrid and Resend (transactional email), plus market-data providers in the trading
domain. These integrate over HTTP rather than through a vendor SDK in most cases, so they
do not appear in a dependency manifest and we do not give them a count here — that would
be a number we did not measure.
