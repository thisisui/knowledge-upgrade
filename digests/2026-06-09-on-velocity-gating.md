---
date: 2026-06-09
url: https://karlkoch.me/writing/on-velocity-gating
tags: [engineering, design]
rating: 4
---

## [On Velocity Gating](https://karlkoch.me/writing/on-velocity-gating)

**Summary**
This article solves a specific problem that happens when you have a row of items — like a music shelf, a tab bar, or a thumbnail strip — and the user moves their cursor quickly across them: every item briefly shows its hover effect as the cursor passes through, which looks like rapid flickering. The article explains a three-part technique to fix this. First, instead of reading cursor speed directly (which fluctuates wildly frame-to-frame), you calculate a smoothed speed using a running formula that blends recent measurements together. Second, you use two separate speed thresholds — one slow speed required to start hovering a new item, and a higher speed required to stop hovering the current one — which creates a comfortable zone where the user can move slowly around a hovered item without accidentally losing it. Third, you adjust those thresholds based on whether the cursor is moving toward or away from an item, so approaching an item feels immediate while overshooting it and coming back feels considered.

**Key takeaways**
- Use an exponential moving average (EMA) to smooth cursor speed instead of reading it directly. The formula is: `smoothed = 0.3 × new_speed + 0.7 × previous_smoothed`. This means each new measurement contributes 30% and the running history contributes 70%, which filters out brief speed spikes caused by display refresh timing and makes the hover system respond to the user's real intent rather than frame-by-frame noise.
- Use two separate speed thresholds: a strict "engage" threshold (the cursor must be moving slowly — below 0.4 px/ms — to start hovering a new item) and a lenient "disengage" threshold (the cursor must accelerate above 0.9 px/ms to stop hovering the current item). The gap between 0.4 and 0.9 px/ms creates a zone where the user can gently move around a hovered item without losing it — a single threshold forces a trade-off between these two behaviors.
- When the cursor is moving toward an item, widen the zone where hovering can begin (from 60% to 85% of the item's width) and raise the maximum allowed speed by 40%. When moving away, tighten both. This makes approaching an item feel immediate and natural while preventing the cursor from accidentally activating items it passes behind on the way out.

**Importance** ★★★★☆ (4/5)
*Unusually precise and directly implementable — the three-layer architecture (EMA smoothing, split thresholds, directional hysteresis) transfers to any dense row of hover targets with working code included.*
