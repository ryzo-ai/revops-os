---
name: revops-audit
description: "Audit a client's CRM and revenue operations. Use when the user mentions 'RevOps audit', 'CRM audit', 'pipeline audit', 'assess CRM', 'revenue operations review', 'data quality check', 'workflow audit', or any request to evaluate the current state of a client's revenue operations system. This is Stage 1 of Ryzo's RevOps service delivery."
---

# RevOps Audit

You are auditing a client's CRM and revenue operations system. The audit is systematic, evidence-based, and produces a prioritized report of findings. This is Stage 1 of Ryzo's RevOps service delivery.

## Before Starting

1. **Load client profile** from the client folder: `~/code/projects/ryzo/ops/service/clients/[slug]/CLAUDE.md`
2. **Confirm CRM platform** — HubSpot, Attio, Salesforce, or other
3. **Gather context:**
   - GTM motion (PLG, sales-led, hybrid)
   - ACV range
   - Sales cycle length
   - Team structure (marketing, SDR, AE, CS headcount)
   - What's working and what's not (the client's perspective)
4. **Confirm audit scope** with Pascal — full audit or focused on specific areas

## Audit Areas

Work through each area systematically. For each finding, record: what you observed, why it matters, and severity.

### 1. CRM Data Quality

- **Duplicate contacts/companies:** What's the estimated duplicate rate?
- **Missing required fields:** Which critical fields are frequently empty? (email, company, lifecycle stage, owner)
- **Stale records:** How many contacts have had no activity in 90+ days?
- **Data entry consistency:** Are fields used consistently? (e.g., industry field has 47 variations of "Software")
- **Property sprawl:** How many custom properties exist? How many are actually used?

### 2. Pipeline Configuration

- **Stage definitions:** Are stages clearly defined with entry/exit criteria?
- **Stage-to-stage conversion:** What's the conversion rate at each stage? Where's the biggest drop?
- **Stuck deals:** How many deals have been in the same stage for >2x the average time?
- **Pipeline hygiene:** Are closed-lost deals cleaned up? Are stale deals addressed?
- **Multiple pipelines:** If multiple pipelines exist, is there clear logic for which is used when?

### 3. Lifecycle Stages

- **Defined stages:** Are lifecycle stages defined and documented?
- **Stage transitions:** Are transitions automated or manual? Are they working correctly?
- **Stage alignment:** Do marketing and sales agree on what each stage means?
- **Buyer journey match:** Do stages reflect the actual buyer journey or are they legacy artifacts?

### 4. Lead Scoring

- **Model exists?** Is there a lead scoring model in place?
- **Fit scoring:** Does it assess company/contact fit (firmographic/technographic)?
- **Engagement scoring:** Does it assess behavioral engagement?
- **Accuracy:** Do high-scoring leads actually convert at higher rates?
- **Decay:** Do scores decay over time if engagement stops?
- **Thresholds:** Are MQL/SQL thresholds defined and appropriate?

### 5. Workflows & Automations

- **Inventory:** List all active workflows/automations
- **Coverage:** What should be automated that isn't? (lead assignment, stage transitions, follow-up reminders, nurture enrollment)
- **Health:** Are workflows firing correctly? Error rates? Enrollment numbers?
- **Conflicts:** Do any workflows conflict with each other?
- **Documentation:** Are workflows documented anywhere?

### 6. Reporting & Dashboards

- **Existing dashboards:** What reports/dashboards exist?
- **Usage:** Are they actually used for decision-making?
- **Accuracy:** Do the numbers match reality? (compare dashboard data to spot checks)
- **Gaps:** What metrics should be tracked but aren't?
- **Accessibility:** Can the right people access the right reports?

### 7. Integration Health

- **Connected tools:** What's integrated? (marketing automation, website, forms, enrichment, scheduling)
- **Sync status:** Are syncs running? When did they last run?
- **Data flow:** Is data flowing in the right direction?
- **Conflicts:** Any field mapping conflicts or overwrite issues?
- **Error handling:** What happens when a sync fails?

### 8. Team Adoption

- **Activity logging:** Are reps logging calls, emails, meetings?
- **Process compliance:** Are people following the defined process or working around it?
- **Workarounds:** Where do people use spreadsheets or other tools instead of the CRM?
- **Training gaps:** What do users struggle with?

## Severity Classification

### Critical
Directly blocking revenue or causing data loss.
- Lead routing broken — leads sitting unassigned
- Conversion tracking disconnected — can't measure pipeline
- Duplicate records creating conflicting customer experiences

### Warning
Causing friction, inefficiency, or unreliable data. Fix within 30 days.
- No lead scoring — marketing can't prioritize
- Manual processes that should be automated
- Reporting gaps making it hard to measure performance

### Improvement
Would improve operations but not urgent.
- Better dashboard design
- Documentation of processes
- Property cleanup and standardization

## Scoring

Rate each area 1-5:
- **1:** Not implemented or severely broken
- **2:** Exists but barely functional
- **3:** Functional but with significant gaps
- **4:** Good with minor improvements needed
- **5:** Excellent, best-practice level

Overall score = average of all area scores.

## Output

Save audit report to vault: `01-clients/[slug]/revops-audit-YYYY-MM-DD.md`

Report format:
```markdown
---
type: revops-audit
client: [slug]
date: YYYY-MM-DD
overall-score: X.X/5
status: complete
---

# RevOps Audit — [Client Name]

## Executive Summary
[3-5 sentences: overall health, top priorities, recommended next step]

## Scores
| Area | Score | Severity |
|------|-------|----------|
| Data Quality | X/5 | |
| Pipeline | X/5 | |
| Lifecycle Stages | X/5 | |
| Lead Scoring | X/5 | |
| Workflows | X/5 | |
| Reporting | X/5 | |
| Integrations | X/5 | |
| Team Adoption | X/5 | |
| **Overall** | **X.X/5** | |

## Critical Findings
[...]

## Warnings
[...]

## Improvements
[...]

## Recommended Blueprint Scope
[Based on findings, what should be included in the Stage 2 blueprint]
```

## Global Rules

- Read-only operations during audit — never modify client data
- Always confirm findings with Pascal before presenting to client
- If you can't assess an area due to access limitations, note it explicitly
- Preserve Obsidian frontmatter and wikilinks when writing to vault
