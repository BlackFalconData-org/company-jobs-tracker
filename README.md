# Company Jobs Tracker

Track new and removed job listings per company across 18+ European job portals.

**[StepStone Company Hiring Tracker on Apify →](https://apify.com/blackfalcondata/stepstone-company-hiring-tracker)**

---

## Key features



**Structured data** — 17 fields per listing. Clean JSON output with consistent field naming. All fields always present — null when unavailable, never omitted.

---

## Use cases



**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from stepstone.de on a schedule. Export to CSV, JSON, or directly to your database.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from stepstone.de.

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

---

## Related products by Black Falcon Data



- [StepStone Scraper](https://github.com/BlackFalconData-org/stepstone-scraper) — Job listings from 18 European portals
- [Indeed Job Scraper](https://github.com/BlackFalconData-org/indeed-job-scraper) — Indeed job listings with salary data
- [Glassdoor Job Scraper](https://github.com/BlackFalconData-org/glassdoor-job-scraper) — Glassdoor listings with company ratings

---

*Last updated: 2026 03*
