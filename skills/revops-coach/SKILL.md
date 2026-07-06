---
name: revops-coach
description: "Generate training materials and coaching session prep for RevOps clients. Use when the user mentions 'training materials', 'CRM training', 'coaching session', 'user guide', 'enablement', 'teach the team', 'RevOps documentation', 'process playbook', or any request to prepare educational content for a client's team. This is Stage 6 of Ryzo's RevOps service delivery — the retainer and coaching phase."
---

# RevOps Coach

You are creating training and enablement materials for a client's team. These materials help client teams adopt and use the RevOps system that was implemented. Write for the people who will USE the system, not build it.

## Before Starting

1. **Read the implementation log** from vault: `01-clients/[slug]/revops-implementation-*.md`
2. **Read the blueprint** from vault: `01-clients/[slug]/revops-blueprint-*.md`
3. **Load client profile** from vault
4. **Ask Pascal:**
   - Who is the audience? (Sales reps, managers, marketing team, ops team)
   - What's the training format? (Written guide, session agenda, video script)
   - What are the biggest adoption challenges so far?

## Content Types

### 1. CRM User Guide

Role-specific instructions for daily CRM usage.

Structure per role:
```markdown
# [CRM Name] Guide for [Role]

## Your Daily Workflow
1. [First thing to do when you open the CRM]
2. [How to check your tasks/pipeline]
3. [How to log activities]

## Key Processes
### [Process Name]
**When:** [Trigger — when do you do this?]
**Steps:**
1. [Step with specific field names, button locations]
2. [Step]
3. [Step]
**What happens next:** [What automation kicks in, who gets notified]

## Common Questions
- Q: [Typical question]
  A: [Clear answer]
```

Adapt to the client's specific implementation — reference their pipeline names, stage names, field names.

### 2. Workflow Documentation

For each automation, explain in plain language:

```markdown
## [Workflow Name]

**What it does:** [One sentence]
**When it triggers:** [Plain language — "When a deal moves to 'Proposal Sent'..."]
**What you'll notice:** [What the user sees — "You'll get a Slack notification and a task will appear"]
**What you need to do:** [Their responsibility — "Complete the task within 24 hours"]
**What if something goes wrong:** [Who to contact, what to check]
```

### 3. Process Playbooks

End-to-end process documentation:

```markdown
# [Process Name] Playbook

## Overview
[What this process accomplishes in 2-3 sentences]

## When to Use
[Trigger conditions in plain language]

## Step-by-Step
### Step 1: [Action]
- **Who:** [Role]
- **What:** [Specific action in the CRM]
- **SLA:** [Time expectation]
- **If stuck:** [Escalation path]

### Step 2: [Action]
[...]

## Success Criteria
[How to know the process worked correctly]

## Common Mistakes
- [Mistake] → [How to avoid/fix]
```

### 4. FAQ Document

Based on common user confusion:

```markdown
# [Client] CRM FAQ

## Getting Started
- **Q: How do I log in?** [Answer]
- **Q: Where do I find my pipeline?** [Answer]

## Daily Tasks
- **Q: How do I log a call?** [Answer]
- **Q: What do I do when a deal moves forward?** [Answer]

## Troubleshooting
- **Q: I can't see a contact/deal.** [Answer about permissions, ownership]
- **Q: A workflow didn't fire.** [Checklist to verify]
```

### 5. Coaching Session Agenda

Structured agenda for live training sessions:

```markdown
# Coaching Session — [Date]
## Topic: [Focus area]
## Duration: [Time]
## Attendees: [Roles]

### Warm-up (5 min)
- Quick wins since last session
- Open questions from the team

### Topic Review (15 min)
- [Concept explanation]
- [Live demo in CRM]

### Hands-on Practice (15 min)
- [Exercise for attendees to do in their own CRM]
- [Expected outcome]

### Q&A (10 min)

### Next Steps
- [Homework / things to practice before next session]
- [Next session date and topic]
```

### 6. Adoption Progress Checklist

For the client team to self-track:

```markdown
# RevOps Adoption Checklist

## Week 1-2: Basics
- ☐ All users can log in and find their pipeline
- ☐ All users logging activities daily
- ☐ Deals being created and moved through stages

## Week 3-4: Process
- ☐ Lead routing working correctly
- ☐ Follow-up tasks being completed on time
- ☐ Reporting dashboards reviewed in team meetings

## Month 2: Optimization
- ☐ Lead scoring producing accurate results
- ☐ Workflows running without errors
- ☐ Team can troubleshoot basic issues independently

## Month 3+: Maturity
- ☐ Team proposing their own workflow improvements
- ☐ Data quality metrics maintained
- ☐ Regular pipeline reviews happening without prompting
```

## Writing Principles

- **Simple language.** No jargon. "Click the dropdown" not "modify the picklist value."
- **Specific references.** Use the client's actual field names, stage names, and pipeline names.
- **Visual structure.** Numbered steps, checkboxes, tables. Easy to scan.
- **Answer "why."** Don't just say what to do — explain why it matters. "Log the call so your manager can see pipeline activity" not just "Log the call."
- **Assume zero CRM expertise.** The best materials work for someone who's never used a CRM before.

## Coaching Cadence

Suggest this default cadence (adjust per client):
- **Weeks 1-4:** Weekly 30-minute sessions (heavy onboarding)
- **Months 2-3:** Biweekly 30-minute sessions (reinforcement)
- **Months 4-12:** Monthly 30-minute sessions (optimization + advanced topics)

## Output

Save materials to vault: `01-clients/[slug]/training/[document-name].md`

Create a training folder under the client if it doesn't exist.

## Global Rules

- Materials are for the client's team, not for Pascal or Claude
- Always adapt to the client's specific implementation — never use generic examples
- Confirm materials with Pascal before sharing with the client
- Preserve Obsidian frontmatter and wikilinks
