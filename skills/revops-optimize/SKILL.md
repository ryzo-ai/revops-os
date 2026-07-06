---
name: revops-optimize
description: "Optimize a live RevOps implementation based on performance data. Use when the user mentions 'RevOps optimization', 'pipeline optimization', 'scoring accuracy', 'stage conversion', 'workflow performance', 'RevOps improvement', or any request to iterate on an existing RevOps implementation. This is Stage 5 of Ryzo's RevOps service delivery."
---

# RevOps Optimize

You are iterating on a live RevOps implementation based on performance data. Compare current metrics to the baseline established during implementation and identify what needs tuning.

## Before Starting

1. **Read the implementation report** from vault: `01-clients/[slug]/revops-implementation-*.md`
2. **Load baseline metrics** from the implementation report
3. **Load client profile** from vault
4. **Pull current performance data** from CRM

## Optimization Areas

### 1. Pipeline Velocity

- **Time-in-stage analysis:** How long do deals sit in each stage?
- **Bottleneck identification:** Which stages have the longest dwell time?
- **Comparison to baseline:** Is velocity improving or degrading?
- **Root causes:** Missing information? No follow-up process? Wrong stage definitions?
- **Recommendation format:** "Stage X dwell time is Y days (baseline: Z). Root cause: []. Fix: []"

### 2. Stage Conversion Rates

- **Stage-to-stage conversion:** What percentage move forward vs drop off?
- **Drop-off points:** Where are leads/deals falling out of the funnel?
- **Comparison to baseline:** Are conversion rates improving?
- **Segment analysis:** Do conversion rates differ by source, segment, or rep?
- **Recommendation format:** "Stage X→Y conversion is A% (baseline: B%). Contributing factors: []. Fix: []"

### 3. Lead Scoring Accuracy

- **Predicted vs actual:** Do high-scoring leads actually convert at higher rates?
- **False positives:** High scores that never convert — what do they have in common?
- **False negatives:** Low scores that did convert — what signals were missed?
- **Threshold calibration:** Is the MQL threshold too high or too low?
- **Recommendation format:** "Scoring accuracy is X%. Top false positive pattern: []. Suggested adjustment: []"

### 4. Workflow Performance

- **Trigger rates:** Are workflows firing at expected frequency?
- **Error rates:** Are any workflows failing?
- **Unintended consequences:** Is any workflow creating unexpected results?
- **Coverage gaps:** Are there manual processes that should be automated now?
- **Recommendation format:** "Workflow [name] fires X times/week (expected: Y). Issue: []. Fix: []"

### 5. Data Quality Trends

- **Field completion rates:** Are required fields being filled?
- **Data freshness:** Are records being updated regularly?
- **Duplicate rate:** Is the duplicate rate improving or growing?
- **Standardization:** Are pick-list values being used consistently?

### 6. Adoption Metrics

- **Activity logging:** Are reps logging activities?
- **Process compliance:** Are people following the defined workflow?
- **Workaround signals:** Where are people still using spreadsheets or email?
- **Feature usage:** Which CRM features are used vs ignored?

## Output Format

```markdown
---
type: revops-optimization
client: [slug]
date: YYYY-MM-DD
period: [date range analyzed]
---

# RevOps Optimization Report — [Client Name]

## Executive Summary
[Top 3 findings and recommended actions]

## Metrics vs Baseline
| Metric | Baseline | Current | Trend |
|--------|----------|---------|-------|
| | | | ↑/↓/→ |

## Findings & Recommendations

### Priority 1: [Finding]
- **Current:** [metric]
- **Baseline:** [metric]
- **Root cause:** [analysis]
- **Recommendation:** [specific action]
- **Expected impact:** [quantify]

### Priority 2: [...]

## Next Review
[Recommended date for next optimization review]
```

Save to vault: `01-clients/[slug]/revops-optimization-YYYY-MM-DD.md`

## Global Rules

- Changes to live system require Pascal's confirmation
- Always show data before recommending changes
- If scoring model needs recalibration, produce the new model as a blueprint amendment — don't change scoring rules directly
