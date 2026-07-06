---
name: revops-implement
description: "Implement a RevOps blueprint by configuring HubSpot or Attio directly. Use when the user mentions 'implement blueprint', 'configure CRM', 'build pipelines', 'set up workflows', 'create properties', 'implement RevOps', or any request to execute the hands-on configuration of a client's CRM system. This is Stage 3 of Ryzo's RevOps service delivery. Requires an approved blueprint."
---

# RevOps Implement

You are configuring a client's CRM system based on an approved blueprint. This is hands-on implementation — you create properties, pipelines, workflows, and dashboards. Every change is documented.

## Before Starting

1. **Read the approved blueprint** from vault: `01-clients/[slug]/revops-blueprint-*.md`
2. **Confirm approval:** Check that the blueprint status is `approved`, not `pending-approval`. If pending, STOP and ask Pascal.
3. **Load CRM agent instructions** from `service-os/agents/crm-agent.md`
4. **Confirm client CRM platform** (HubSpot, Attio, other)
5. **Start the implementation log**

## Implementation Order

Dependencies matter. Follow this sequence:

### Phase 1: Properties
Create custom properties BEFORE anything references them.
- Create contact, company, and deal properties per blueprint
- Verify field types, options (for dropdowns), and required/optional settings
- Document each property created

### Phase 2: Pipeline Stages
- Configure pipeline(s) with stages from the blueprint
- Set required fields per stage
- Configure deal probability per stage (if applicable)
- Set up stage automation rules

### Phase 3: Lifecycle Stages
- Configure lifecycle stages per blueprint definitions
- Set up transition rules (which transitions are allowed)
- Map lifecycle stages to pipeline stages where applicable

### Phase 4: Lead Scoring
- Configure fit score criteria
- Configure engagement score criteria
- Set scoring thresholds for MQL/SQL
- Set up score decay rules
- Test with sample records

### Phase 5: Workflows
- Build workflows in the order they depend on each other
- For each workflow:
  1. Create the workflow with trigger and conditions
  2. Add actions
  3. Test with a test record
  4. Activate only after testing passes
- Document any deviations from blueprint

### Phase 6: Dashboards & Reports
- Create dashboards per blueprint specs
- Configure report sources, filters, and metrics
- Verify data accuracy with spot checks
- Set sharing permissions

### Phase 7: Integrations
- Configure third-party connections per blueprint
- Test sync with sample data
- Verify field mappings
- Set up error alerting

## Implementation Log

Maintain a running log of every change:

```markdown
## Implementation Log

### [Timestamp] — [Phase]: [What was done]
**Before:** [Previous state]
**After:** [New state]
**Verified:** ☐ Yes / ☐ No
**Notes:** [Any deviations from blueprint, issues encountered]
```

Save to vault: `01-clients/[slug]/revops-implementation-YYYY-MM-DD.md`

## Testing Protocol

After each phase:
1. **Create a test record** that should trigger the new configuration
2. **Walk it through the process** — does it behave as expected?
3. **Check edge cases** — what happens with incomplete data? Wrong values?
4. **Verify reporting** — does the change appear correctly in dashboards?

Before activating workflows on live data:
1. Test with 3-5 test records covering different scenarios
2. Verify no unintended side effects on existing records
3. Confirm with Pascal before activation

## Rollback Awareness

For each change, note how to undo it:
- Properties: can be archived (not easily deleted if data exists)
- Pipeline stages: can be renamed/reordered but not deleted if deals exist
- Workflows: can be deactivated instantly
- Integrations: can be disconnected

## Handling Deviations

If the blueprint doesn't account for something you encounter:
1. Document the gap
2. Propose a solution
3. Confirm with Pascal before implementing
4. Update the blueprint document with the deviation

Do NOT improvise silently. Every deviation from the blueprint is documented.

## Output

Save implementation log to vault: `01-clients/[slug]/revops-implementation-YYYY-MM-DD.md`

Include:
- Summary of what was configured
- Before/after state for each phase
- Test results
- Any deviations from blueprint with rationale
- Known issues or follow-up items

## Global Rules

- **Always confirm before bulk changes.** Modifying existing records (vs creating new config) requires Pascal's approval.
- **Take before-state exports** before modifying anything that affects existing data.
- **Test workflows with test records** before activating on live data.
- **Never delete existing data.** Archive, deactivate, or mark as deprecated.
- **Document everything.** If it's not in the implementation log, it didn't happen.
