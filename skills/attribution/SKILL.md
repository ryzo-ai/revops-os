---
name: attribution
description: Attribute revenue to its true source — inbound vs outbound, first/last/multi-touch models, self-reported attribution, channel ROI, and marketing- vs sales-sourced pipeline. Use when the user mentions attribution, inbound vs outbound, multi-touch attribution, channel ROI, marketing-sourced pipeline, self-reported attribution, or "where do our deals come from".
---

# Attribution

Attribute pipeline and revenue to the channels and motions that actually produced it, well enough to make a budget decision — not perfectly.

## Why Attribution Is Hard

B2B deals involve multiple people, multiple touches, and multi-month cycles. A buyer reads a blog post in month one, ignores three emails, sees a LinkedIn ad, asks a peer in a Slack group, then books a demo from a Google search for your brand name. Most of that trail is invisible to any tracking system — this is "dark social," and no tool fixes it completely.

The goal is **directional truth for budget decisions**, not forensic precision. You're trying to answer "should we spend more on outbound or content next quarter," not "exactly how many dollars did this LinkedIn post generate." Chasing false precision (a single model, a single number, decimal-point ROI) is a bigger risk than an admittedly-approximate view that's directionally right. Build the simplest model that changes a decision, and get more sophisticated only when someone can name the decision the extra sophistication would change.

## Sourced vs Influenced

These three terms get conflated constantly. Define them once and hold the line:

- **Marketing-sourced** — marketing created the pipeline. The first touch that turned an unknown person into a tracked lead was a marketing channel (organic, paid, content, webinar, partner). Without that touch, this pipeline doesn't exist yet.
- **Sales-sourced** — a rep created the pipeline. Outbound prospecting, a cold call, an SDR sequence, a founder DM. The first touch was a human on your team reaching out.
- **Marketing-influenced** — marketing touched the deal somewhere in the journey, but didn't source it. The prospect came in through outbound, and later downloaded a report or attended a webinar before closing. Influence is a much looser bar than sourced — almost every deal touches marketing content somewhere, so an "influenced" number is only useful as a supporting metric, never as marketing's headline number. If marketing claims credit via "influenced" while sales claims the same deal as "sourced," you have a reporting fight, not a data problem — fix it by making sourced (first touch) the tie-breaker and influenced purely descriptive.

Report sourced pipeline by team (marketing-sourced vs sales-sourced) as the primary split. Use influenced as a secondary, non-competing metric ("marketing touched 80% of sales-sourced deals somewhere in-cycle") — never let it substitute for sourced in a comp or budget conversation.

## Inbound vs Outbound

Classify every deal's origin by its **first meaningful touch** — the first interaction that put the account on your radar, not the first CRM record created (a rep can create a contact record for someone who filled out a form last week; that's still inbound).

- **Inbound** — the account found you: organic search, referral, content, a demo request form, a partner referral, word of mouth.
- **Outbound** — you found the account: a cold call, an SDR email sequence, a founder cold DM, a paid ad that was itself a response to outbound-driven brand awareness (edge case — use judgment, and see the trap below).

**The last-touch trap**: if a rep cold-emails a prospect who has quietly been reading your blog and following your LinkedIn for three months, last-touch attribution credits outbound with sourcing the deal — sales sees "SDR sourced this," runs a victory lap, and the org over-invests in outbound while under-crediting the content that actually warmed the account. The reverse trap also happens: a prospect who was outbound-prospected six months ago, went cold, then re-engaged by filling out a demo form gets marked "inbound" with no visibility into the outbound touch that originally created awareness.

The fix isn't picking one side — it's **tracking both**, explicitly:
- First touch overall (what created initial awareness — inbound or outbound)
- Most recent significant touch before the deal was created (what triggered the actual buying motion)

Hold both fields on the account/deal record. When they disagree, that disagreement is itself the signal worth reporting — it tells you which channel is doing the warming and which is doing the converting.

## Model Menu

No single model is "correct" — each answers a different question and has a built-in bias. Pick based on what decision you're making, not because it's the most sophisticated option available.

| Model | What it answers | Bias |
|-------|-----------------|------|
| **First-touch** | What creates initial awareness / fills the top of funnel? | Over-credits demand-gen and brand channels; ignores everything that happened to actually close the deal |
| **Last-touch** | What triggers the final conversion action? | Over-credits bottom-funnel and sales activity; credits "Direct" or "Google — brand" for deals that took months of nurturing to get there |
| **Linear** | Every touch gets equal credit | Dilutes the channels that matter most; treats a single email open the same as a demo attendance |
| **Time-decay** | Recent touches matter more | Systematically underweights the awareness-stage channels that started the journey |
| **U-shaped** (first + last touch weighted, middle touches split the rest — commonly 40/20/40) | Balances "what created this" with "what closed this," while still crediting the middle | Ignores which middle touches actually mattered vs. noise |
| **W-shaped** (credit split across the three key touches — first touch, lead-creation touch, opportunity-creation touch — with roughly even weight, and a small remainder distributed across the rest) | Same as U-shaped, plus explicitly credits the moment a lead converts to a qualified opportunity | Needs clean, consistent stage-change tracking to work — garbage in if your CRM stages are inconsistent |

**Recommendation**: don't start with multi-touch. Start with a **dual first-touch + last-touch view** side by side — it's simple to build, explainable to a room of non-marketers, and already surfaces the inbound/outbound tension above. Move to U-shaped or W-shaped only once you have enough clean touch-point data (consistent UTMs, consistent CRM stage timestamps) that the extra model complexity adds signal instead of just adding a number nobody trusts.

## Self-Reported Attribution

The single highest-ROI attribution fix for dark social is blunt and low-tech: ask. Add a **"How did you hear about us?"** field to your demo request / contact form and treat the answer as a real data point, not decoration.

Structure it well:
- Use a dropdown with your actual channel list (not a free-text box that becomes unusable data) — e.g. "Search / Google," "LinkedIn," "Referral from a colleague," "Podcast/webinar," "Saw an ad," "Read a blog post/article," "Other" with a free-text follow-up only on "Other" and "Referral"
- Keep the list short (6-10 options) — a 20-item dropdown gets randomly clicked
- Ask at the point of highest intent (demo request, signup) rather than earlier in the funnel where the answer is less informed

**Reconciling with tracked data**: self-reported and tracked attribution will disagree, and that's expected — self-report catches dark social and offline influence (a colleague mentioned it, a conference conversation) that tracking structurally cannot see; tracked data catches the precise channel and campaign that self-report can't. Use tracked data as primary when it's confident (a clean UTM chain exists) and self-reported as a cross-check and gap-filler when tracked data is thin or the buyer says something tracking didn't capture at all (most commonly: word of mouth, and podcast/newsletter mentions that don't click through). If self-reported "referral" volume is high but your tracked referral numbers are near zero, that gap is telling you something real about a channel you aren't measuring, not that your form data is unreliable.

## Channel ROI

The basic formula is **(pipeline or revenue attributed to a channel) / (spend on that channel)**, run both on pipeline (leading indicator, available sooner) and on closed revenue (lagging but real). Alongside it, track:
- **CAC by channel** — total spend / new customers acquired, per channel
- **Payback period by channel** — how many months of revenue from a customer it takes to recover CAC for that channel

The caution that matters more than any of the formulas: **ROI comparisons across channels are only valid if every channel is measured with the same attribution model.** If outbound gets credited on a "sourced" (first-touch) basis and paid social gets credited on an "influenced" (any-touch) basis, paid social will structurally look more productive than it is — not because it performs better, but because its bar for credit is lower. Before publishing a channel ROI comparison, confirm every channel in the table was scored the same way; if that's not possible yet, publish per-channel pipeline/revenue with the model labeled next to each row rather than force a comparison the data can't support.

## Implementation Notes

- **UTMs on every outbound link** — campaign, source, medium, content — applied consistently by convention, not ad hoc per campaign. Inconsistent UTM naming (`li` vs `linkedin` vs `LinkedIn`) silently fragments a channel's data across multiple rows in every report downstream.
- **A canonical `original_source` field, set once, never overwritten.** This is the single most common attribution bug: a marketing automation tool or CRM workflow updates the "lead source" field every time a contact does something new, so by the time a deal closes, the field shows the last thing that happened instead of how the contact was actually created. Set `original_source` (and `original_source_timestamp`) on first contact creation and lock the field — no workflow, integration, or manual edit should ever change it after that point.
- **A separate `most_recent_source` field** that *is* allowed to update — this is what captures the last-touch side of the inbound/outbound dual view above, and re-engagement patterns (cold lead comes back through a different channel).
- **Hidden form fields** to capture UTM parameters (and referrer URL) at the moment of form submission, mapped straight into the CRM's source fields — don't rely on session-based tracking alone to survive the gap between first visit and eventual form fill, especially across devices.
- **CRM properties to hold, at minimum**: `original_source` (first touch, locked), `original_source_detail` (campaign/content-level detail), `most_recent_source` (last touch, updatable), `self_reported_source` (from the form field above), and a boolean or enum for `inbound_or_outbound` classification set at deal creation and reviewed, not auto-derived blindly from source alone.

## Related skills
Part of RevOS. See also the other capability skills and the `revops` router.
