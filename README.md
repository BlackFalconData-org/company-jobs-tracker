# Company Jobs Tracker

Track new and removed job listings per company across 18+ European job portals.

**[StepStone Company Hiring Tracker - DE on Apify →](https://apify.com/blackfalcondata/company-jobs-tracker?fpr=1h3gvi)**

---

## Key features






**Proxy support** — Route traffic through Apify Proxy or your own proxy group to avoid regional blocks and rate limits.

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases






**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from stepstone.de on a schedule. Export to CSV, JSON, or directly to your database.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from stepstone.de.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

---

## Quick start

```json
"{\"companies\":[{\"name\":\"SAP\",\"geo\":\"DE\"},{\"name\":\"Siemens\",\"geo\":\"DE\"}],\"maxResultsPerCompany\":50}"
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `companies` | array | — | List of companies to track (max 200) |
| `includeDetails` | boolean | `false` | Fetch full job descriptions (slower, more expensive) |
| `maxResultsPerCompany` | integer | `50` | Max jobs to fetch per company per run (hard ceiling: 100) |
| `calibrateOnly` | boolean | `false` | Run this first to validate company name matching before enabling tracking. No state is written. |
| `maxTotalRequests` | integer | `500` | Hard cap on total HTTP requests across all companies |
| `maxCompanies` | integer | `200` | Hard cap on companies processed per run |
| `removedConfirmationRuns` | integer | `1` | Job must be missing for N+1 consecutive successful runs before marked removed. Default 1 = two-run confirmation. |
| `proxyConfiguration` | object | `{"useApifyProxy":true}` | Apify proxy configuration |

---

## FAQ

<!-- WRITE: 4-6 Q&A pairs relevant to this product -->

**How does incremental mode work?**
Each listing gets a content hash. On subsequent runs, only new or changed listings are emitted — saving time, compute, and storage.

---

## Known limitations

<!-- WRITE: 4-6 honest limitations -->

- <!-- WRITE: limitation 1 -->
- <!-- WRITE: limitation 2 -->


## Output fields

Every listing returns the same 17-field schema. Missing values are `null` — never omitted.

- `company`
- `geo`
- `matchMode`
- `scrapeOutcome`
- `runAt`
- `previousRunAt`
- `isFirstRun`
- `counts`
- `serpCount`
- `processedCount`
- `matchedCount`
- `anonymousSkippedCount`
- `costGuardTriggered`
- `warnings`
- `error`
- `newJobs`
- `removedJobs`


## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "company": "Siemens",
  "geo": "DE",
  "matchMode": "strict_normalized",
  "scrapeOutcome": "success",
  "runAt": "2026-03-28T09:08:50.222Z",
  "previousRunAt": "2026-03-27T09:00:00.000Z",
  "isFirstRun": false,
  "counts": {
    "new": 2,
    "removed": 0,
    "unchanged": 23,
    "total": 25
  },
  "serpCount": 25,
  "processedCount": 25,
  "matchedCount": 25,
  "anonymousSkippedCount": 0
}
```

*Truncated — full records contain 17 fields. See Output fields for the complete schema.*


**[Try StepStone Company Hiring Tracker - DE now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/stepstone-company-hiring-tracker?fpr=1h3gvi)**


## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Actor Start | $0.01 |
| Result | $0.002 |

See the [actor on Apify](https://apify.com/blackfalcondata/stepstone-company-hiring-tracker?fpr=1h3gvi) for current pricing.

---

## Related products by Black Falcon Data






- [StepStone Scraper](https://apify.com/blackfalcondata/stepstone-scraper?fpr=1h3gvi) — Job listings from 18 European portals
- [Indeed Job Scraper](https://apify.com/blackfalcondata/indeed-job-scraper?fpr=1h3gvi) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://apify.com/blackfalcondata/glassdoor-job-scraper?fpr=1h3gvi) — Glassdoor listings with company ratings
- [Arbeitsagentur Scraper](https://apify.com/blackfalcondata/arbeitsagentur-scraper?fpr=1h3gvi) — Germany's official job portal (1M+ listings)
- [SEEK Scraper](https://apify.com/blackfalcondata/seek-scraper?fpr=1h3gvi) — Australia & NZ's largest job board
- [Naukri Scraper](https://apify.com/blackfalcondata/naukri-scraper?fpr=1h3gvi) — India's largest job portal

---


## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---

## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. [Sign up free](https://console.apify.com/sign-up?fpr=1h3gvi) — $5 credit included
2. Open the actor and paste your input
3. Click Start — results download as JSON, CSV, or Excel

Need more volume? [See pricing](https://apify.com/pricing?fpr=1h3gvi).

---

---

*Last updated: 2026 03*
