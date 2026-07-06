---
name: data-hygiene
description: Keep CRM data clean — dedup strategy, required-field enforcement, enrichment tools, and quarterly audits. Use when the user mentions data hygiene, duplicate records, data quality, required fields, enrichment, or CRM cleanup.
---

# Data Hygiene

Keep CRM data clean and trustworthy through deliberate dedup rules, required-field enforcement, and a recurring audit cadence.

## Dedup Strategy

- **Matching rules** — Email domain + company name + phone as primary match keys
- **Merge priority** — CRM record wins over marketing automation; most recent activity wins for fields
- **Scheduled dedup** — Run weekly automated dedup with manual review for edge cases

## Required Fields Enforcement

- Enforce required fields at each lifecycle stage
- Block stage advancement if fields are empty
- Use progressive profiling — don't require everything upfront

## Enrichment Tools

| Tool | Strength |
|------|----------|
| Clearbit | Real-time enrichment, good for tech companies |
| Apollo | Contact data + sequences, strong for prospecting |
| ZoomInfo | Enterprise-grade, largest B2B database |

## Quarterly Audit Checklist

- Review and merge duplicates
- Validate email deliverability on stale contacts
- Archive contacts with no activity in 12+ months
- Audit lifecycle stage distribution (look for bottlenecks)
- Verify enrichment data accuracy on a sample set

## Related skills
Part of RevOS. See also the other capability skills and the `revops` router.
