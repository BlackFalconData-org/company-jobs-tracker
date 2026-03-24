# Company Jobs Tracker

Track new and removed job listings per company across 18+ European job portals.

**[Run on Apify →](https://apify.com/blackfalcondata/company-jobs-tracker)**

---

## Key features

📄 **Detail enrichment**

Fetch full job descriptions, salary data, employer profiles, and contact information for each listing.

📊 **Structured data**

Clean JSON output with consistent field naming. All fields always present — null when unavailable, never omitted.

---

## Use cases

**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from the source on a schedule. Export to CSV, JSON, or directly to your database.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from the source.

**AI and LLM workflows**
Use compact mode and description truncation to feed data into AI agents, MCP servers, and LLM pipelines without exceeding token budgets.

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

| Product | Description |
|:--------|:------------|
| [StepStone Jobs API](https://github.com/BlackFalconData-org/stepstone-jobs-api) | Job listings from 18 European portals |
| [Company Jobs Tracker](https://github.com/BlackFalconData-org/company-jobs-tracker-api) | Track new/removed jobs per company |
| [Indeed Jobs Feed](https://github.com/BlackFalconData-org/indeed-jobs-feed) | Indeed job listings with salary data |
| [Glassdoor Jobs Feed](https://github.com/BlackFalconData-org/glassdoor-jobs-feed) | Glassdoor listings with company ratings |
| [Arbeitsagentur Jobs Feed](https://github.com/BlackFalconData-org/arbeitsagentur-jobs-feed) | Germany's federal job portal (1M+ listings) |
| [Naukri Jobs Feed](https://github.com/BlackFalconData-org/naukri-jobs-feed) | India's largest job portal |
| [Bilbasen Scraper](https://github.com/BlackFalconData-org/bilbasen-scraper) | Denmark's largest car marketplace |

---

*Last updated: 2026 03*
