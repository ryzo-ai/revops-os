---
name: revops-blueprint
description: "Design a RevOps solution blueprint based on audit findings. Use when the user mentions 'RevOps blueprint', 'design pipeline', 'lifecycle stages', 'lead scoring model', 'workflow design', 'CRM architecture', 'RevOps plan', or any request to design the solution for a client's revenue operations. This is Stage 2 of Ryzo's RevOps service delivery. Requires a completed audit first."
---

# RevOps Blueprint

You are designing a RevOps solution for a client based on completed audit findings. The blueprint is the contract — the client approves it before implementation begins. It must be specific enough that the implement stage can execute without ambiguity.

## Before Starting

1. **Read the audit report** from vault: `01-clients/[slug]/revops-audit-*.md`
2. **Load client profile** from vault: `01-clients/[slug]/[slug].md`
3. **Gather additional context** (ask if not in the audit):
   - GTM motion (PLG, sales-led, hybrid)
   - ACV range and sales cycle length
   - Team structure (marketing, SDR, AE, CS — headcount and roles)
   - Current tools beyond CRM (marketing automation, enrichment, scheduling, etc.)
   - Growth plans that might affect the design (new market, new product, hiring)

## Blueprint Sections

Produce whichever sections are relevant based on audit findings. Not every client needs every section.

### 1. Pipeline Design

For each pipeline (there may be multiple — e.g., new business, expansion, partner):

```markdown
## Pipeline: [Name]

### Stages
| Stage | Entry Criteria | Exit Criteria | Required Fields | Owner | Expected Conversion |
|-------|---------------|---------------|-----------------|-------|-------------------|
| | | | | | |

### Deal Rot Rules
- Deals in [stage] for >[X] days → alert owner
- Deals in [stage] for >[Y] days → escalate to manager
- Deals with no activity for >[Z] days → flag for review

### Pipeline Hygiene
- Review cadence: [weekly/biweekly]
- Who reviews: [role]
- Cleanup criteria: [when to close stale deals]
```

### 2. Lifecycle Stage Definitions

```markdown
## Lifecycle Stages

| Stage | Definition | Transition Trigger | Automated? | Owner | SLA |
|-------|-----------|-------------------|------------|-------|-----|
| Subscriber | Opted into content | | | Marketing | |
| Lead | Identified with basic info | Form fill / import | Yes | Marketing | |
| MQL | Passes fit + engagement threshold | Score threshold | Yes | Marketing | |
| SQL | Sales accepted and qualified | Manual acceptance | No | Sales | 4h response |
| Opportunity | BANT confirmed, deal created | Deal creation | Yes | Sales | |
| Customer | Closed-won | Deal won | Yes | CS | |

### Recycling Rules
- Rejected MQLs → nurture sequence, re-evaluate in [X] days
- Lost opportunities → reason code required, win-back sequence after [Y] days
```

### 3. Lead Scoring Model

```markdown
## Lead Scoring

### Fit Score (0-100)
| Signal | Points | Rationale |
|--------|--------|-----------|
| Company size [range] | +X | Matches ICP |
| Industry [list] | +X | Target vertical |
| Role [titles] | +X | Decision maker |
| Tech stack [tools] | +X | Integration fit |

### Engagement Score (0-100)
| Action | Points | Decay |
|--------|--------|-------|
| Pricing page visit | +X | -Y/week |
| Demo request | +X | None |
| Content download | +X | -Y/week |
| Email open | +X | -Y/week |
| Multiple visits (3+ in 7 days) | +X | Reset on activity |

### Thresholds
- MQL threshold: Fit ≥ [X] AND Engagement ≥ [Y]
- SQL threshold: Manual qualification by sales after MQL acceptance
- Score decay: Engagement scores decay by [X] points per week of inactivity
```

### 4. Workflow Specifications

For each workflow, specify clearly:

```markdown
## Workflow: [Name]

**Purpose:** [What this workflow accomplishes]
**Trigger:** [Event that starts it]
**Conditions:**
- [Condition 1]
- [Condition 2]
**Actions:**
1. [Action 1]
2. [Action 2]
3. [Action 3]
**Error handling:** [What happens if an action fails]
**Testing:** [How to verify it works]
```

Common workflows to consider:
- Lead assignment (round-robin, territory-based, or score-based)
- Lifecycle stage transitions
- MQL notification to sales
- Deal stage automation
- Follow-up reminders
- Nurture enrollment/disenrollment
- Data cleanup (standardize fields, merge duplicates)
- Integration syncs

### 5. Property Schema

```markdown
## Custom Properties

### Contact Properties
| Property | Type | Required | Used In | Purpose |
|----------|------|----------|---------|---------|
| | | | | |

### Company Properties
| Property | Type | Required | Used In | Purpose |
|----------|------|----------|---------|---------|

### Deal Properties
| Property | Type | Required | Used In | Purpose |
|----------|------|----------|---------|---------|
```

Only create properties that serve a specific purpose. Every property should be used by at least one workflow, report, or process.

### 6. Dashboard Requirements

```markdown
## Dashboards

### [Dashboard Name] — for [Audience]
**Purpose:** [What decisions this enables]
**Refresh:** [Real-time / Daily / Weekly]
**Metrics:**
- [Metric 1]: [Definition, source]
- [Metric 2]: [Definition, source]
**Filters:** [Date range, team, pipeline, etc.]
```

### 7. Integration Design

```markdown
## Integrations

### [Tool] ↔ [CRM]
**Direction:** [One-way / Bidirectional]
**What syncs:** [Objects, fields]
**Frequency:** [Real-time / Scheduled]
**Conflict resolution:** [CRM wins / Tool wins / Most recent]
**Error handling:** [Alert on failure / Retry / Manual review]
```

## Blueprint Format

Save to vault: `01-clients/[slug]/revops-blueprint-YYYY-MM-DD.md`

```markdown
---
type: revops-blueprint
client: [slug]
date: YYYY-MM-DD
status: pending-approval
audit-ref: [[revops-audit-YYYY-MM-DD]]
---

# RevOps Blueprint — [Client Name]

## Executive Summary
[What we're building, why, expected outcomes]

## Scope
[What's included and explicitly what's NOT included]

## [Sections as relevant]

## Implementation Timeline
[Estimated phases and durations]

## Dependencies & Risks
[What could block implementation, what we need from the client]

## Approval
☐ Client approved — Date: ___
☐ Pascal approved — Date: ___
```

## Principles

- **Define before automate.** Every workflow must reference a documented process.
- **Fewer properties is better.** Don't create fields nobody will fill in.
- **Design for the users, not the system.** If reps won't follow the process, the design is wrong.
- **Make the right thing the easy thing.** Required fields at the right stage, not everywhere.
- **Plan for iteration.** V1 should be simple. Complexity comes from optimization, not upfront design.

## Global Rules

- The blueprint is a document, not an implementation. Don't configure anything yet.
- Always confirm the blueprint with Pascal before presenting to the client.
- Preserve Obsidian frontmatter and wikilinks when writing to vault.
