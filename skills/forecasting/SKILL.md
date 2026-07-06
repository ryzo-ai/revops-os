---
name: forecasting
description: Forecast revenue reliably — pipeline coverage ratios, forecast categories (commit/best-case/pipeline), win-rate and historical models, and forecast hygiene. Use when the user mentions revenue forecast, sales forecast, pipeline coverage, forecast categories, commit vs best case, win rate, or quota attainment projection.
---

# Forecasting

Forecast revenue as a decision tool, not a wish — with the coverage math, categories, and hygiene that make a number defensible.

## Purpose

A forecast exists to drive decisions that have to be made before the quarter closes: how many reps to hire, how much to spend on paid channels, what to tell the board, whether to pull a lever now or wait. Those decisions are only as good as the number behind them.

That means the goal of forecasting is **accuracy, not optimism**. A forecast that's consistently too high causes real damage — overhiring, overspending, a board expectation that gets missed publicly. A forecast that's consistently too low (sandbagging) causes quieter but still real damage — underinvestment, reps who look artificially safe, a company that under-plans for growth it's actually going to get. Both failure modes come from the same root cause: treating the forecast as a performance to manage rather than a measurement to get right. The rep, manager, and RevOps function all have an incentive to distort the number in some direction — the discipline of forecasting is building a process that resists that pull.

## Pipeline Coverage

**Coverage ratio** = open pipeline available to close in the period ÷ the quota (or target) for that period.

If the sales team needs to close $500K this quarter and has $1.75M in relevant open pipeline, coverage is 3.5x.

**The 3–4x rule of thumb.** A commonly cited heuristic is that healthy pipeline coverage sits somewhere in the 3–4x range. Treat this as a rough starting point, not a target to hit blindly — it's a heuristic that assumes a win rate in the 25–33% range, and it varies a lot by business. A motion with a much higher win rate needs far less coverage to hit the same number; a motion with a much lower win rate needs more.

**Derive your own target instead of borrowing the heuristic.** The actual relationship is:

```
required coverage ≈ 1 / win rate
```

If a team's historical win rate on qualified pipeline is one in five deals, that team needs roughly 5x coverage to have enough shots on goal to hit target — not the generic 3–4x. If win rate is one in three, roughly 3x is closer to right. Add a buffer on top of the raw ratio (rather than treating it as exact) to absorb deals that slip out of the period, get disqualified late, or simply don't convert to plan — the 1/win-rate number is a floor, not a cushion.

This means the first forecasting task for any team isn't picking a coverage target — it's establishing a reliable, current win rate to derive one from, and periodically re-deriving it as the win rate moves.

## Forecast Categories

Every open deal in a forecast period should sit in exactly one category, defined by how confident the rep and manager are that it closes — not by deal size or how much the rep wants it to close.

| Category | Definition | What qualifies a deal |
|----------|------------|------------------------|
| **Commit** | Deals the rep is staking their number on. High confidence this closes in the period, as forecasted. | Verbal or written agreement to move forward, procurement/legal in motion, no known open objections, a real close date inside the period. If it doesn't close, it's a genuine surprise. |
| **Best Case** | Deals that could close in the period with a good week, but aren't a sure thing. | Positive signals (engaged champion, active evaluation) but at least one real unknown — budget not fully confirmed, competing priority, a decision-maker not yet bought in. |
| **Pipeline** | Everything else that's open and active but not realistically closing this period, or too early to call. | Deal is progressing normally through earlier stages; no basis yet to claim it for this period. |
| **Omitted** | Deals excluded from the forecast entirely. | Stalled, disqualified, no activity in a defined window, or a close date that's clearly aspirational rather than real — omit rather than let it inflate Pipeline. |

**Rep roll-up discipline.** The forecast total isn't just "sum of Commit" — most teams report at least two numbers: Commit (the floor) and Commit + Best Case (the ceiling, sometimes called "Best Case forecast"). The manager's job in a forecast review is to challenge category placement, not just collect numbers: a deal a rep calls Commit should survive the question "what would have to go wrong for this to slip?" with a real answer, not silence. Category creep — quietly moving deals to Commit under pressure to hit a number — is the single fastest way to make a forecast worthless; the roll-up discipline is a management process, not a CRM field.

## Forecasting Methods

No single method is sufficient on its own — each has a different failure mode, and using more than one is how those failure modes get caught before they reach a board deck.

**1. Categorical / judgment roll-up** — Sum the Commit category (and optionally Commit + Best Case) across reps, as defined above. Appropriate as the primary forward-looking number because it incorporates human judgment and deal-specific context a formula can't see. Its weakness is exactly that: it's only as good as the discipline behind the categorization, and it's the method most exposed to sandbagging or happy-ears optimism.

**2. Stage-weighted (probability × amount)** — Assign each pipeline stage a probability of closing (calibrated from your own historical stage-to-close conversion rates, not a generic industry table — every business's stages and conversion behavior differ), multiply each open deal's amount by its stage probability, and sum. Appropriate as a sanity-check cross-reference against the categorical roll-up, and useful for a rougher, more mechanical view across a large pipeline. **Caveat — double counting**: stage-weighted totals silently double-count when a deal is already sitting in Commit (which should be treated at or near full value) but also gets its stage-weighted fraction added on top in a separate report, or when multiple stage-weighted views are summed without clarifying which deals already appear in the categorical number. Keep the two methods as parallel, separately labeled views — never add them together.

**3. Historical win-rate / velocity model** — Multiply (number of open deals expected to reach a decision in the period) × (historical average win rate) × (average deal size), optionally combined with historical sales-cycle length to estimate which currently-open deals will actually reach a decision inside the period. Appropriate as a top-down check on whether the bottom-up categorical number is plausible given the team's real historical conversion behavior, and it's the method least susceptible to any individual rep's optimism or pessimism because it doesn't touch deal-level judgment at all.

**4. Triangulate 2–3 methods, don't rely on one.** Run the categorical roll-up as the primary number, and use the stage-weighted and historical models as independent checks. When they agree, confidence in the number goes up. When they disagree significantly, that disagreement is the most useful signal in the whole exercise — it usually means either the categorization is drifting from reality (check for category creep) or the historical baseline (win rate, stage probabilities) is stale and needs recalibrating, not that one method is simply "wrong" and the other "right."

## Forecast Hygiene

- **Close dates must be real.** A close date is a claim about when a deal will be signed, not a placeholder or a quota-period default. A deal with a close date that's been pushed repeatedly without a stated reason is a data quality problem, not a forecasting problem — fix it at the source.
- **Purge stale deals on a schedule.** Deals with no recent activity, no next step, or a close date long in the past should be moved out of the active forecast (to Omitted, or reassigned a real date) rather than left to quietly inflate Pipeline or Best Case totals.
- **No sandbagging, no happy ears.** Sandbagging (deliberately under-forecasting to guarantee beating the number) and happy ears (believing a rep's optimistic read without challenge) are both distortions of the same underlying discipline. The fix for both is the same forecast-review habit: ask what evidence supports the category a deal sits in, not what the rep hopes.
- **Weekly forecast cadence.** A standing weekly review — new deals entering Commit/Best Case, deals that moved categories, deals that slipped, deals purged — keeps the forecast current and gives management time to react before the number is locked for the period. A forecast only reviewed once a month reacts too late to changes.
- **What triggers a re-forecast.** A material change should force an update rather than wait for the next scheduled review: a large deal slips out of the period, a large deal pulls forward, a rep's territory or quota changes mid-period, or the underlying win rate used in the historical model moves enough to change the derived coverage target.

## Common Errors

- **Last-minute slippage** — deals sitting in Commit or Best Case slip past the period boundary in the final days, and the forecast wasn't discounted for the (predictable, recurring) pattern of some fraction of "should close this period" deals always sliding into the next one.
- **Single-method reliance** — trusting only the categorical roll-up (or only the stage-weighted number) without a second method to catch drift, category creep, or a stale historical baseline.
- **Ignoring pipeline creation rate** — forecasting purely off what's already open without checking whether enough new pipeline is being created to sustain coverage in the *next* period; a healthy forecast this quarter built on a shrinking pipeline-creation rate is a warning for next quarter, not a clean bill of health.
- **Treating stage probability as commit probability** — a deal sitting in a stage with a historically high close rate is not the same claim as a rep saying "I'm staking my number on this." Stage probability is a population-level average across many deals; Commit is a specific, evidence-backed claim about one deal. Collapsing the two overstates confidence in any individual deal that merely looks good on paper.

## Related skills
Part of RevOS. See also the other capability skills and the `revops` router.
