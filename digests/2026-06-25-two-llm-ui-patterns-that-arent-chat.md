---
date: 2026-06-25
url: https://poyo.co/note/20260525T094605/
tags: [ai, design, engineering]
rating: 4
---

## [Two LLM UI Patterns That Aren't Chat](https://poyo.co/note/20260525T094605/)

**Summary**
Almost every product built on a large language model (LLM) uses a chat box, but chat forces every task into a single growing transcript, which is a poor fit for some jobs. This article presents two alternative interface patterns with working demos. The first, "comparison as a table," keeps a persistent grid where the things being compared are rows and each user question becomes a new column the model fills in cell by cell — far cleaner than asking chat to re-generate a comparison every time. The second, "exploration as a tree," lets you branch a topic into independent sub-threads so that exploring one branch deeply does not pollute the context of the others. The author's core point is that the power of these tools comes from how the context is structured and made visible, not from anything clever in the model itself.

**Key takeaways**
- Comparison pattern: model the data as a table where items are rows and questions become columns; constrain the model with a tool definition that returns exactly one cell value per row id, so output lands in the right place.
- Decomposition pattern: a tree where each node sends the model only its own heading, its parent chain, and prior answers — not the whole transcript — so branches stay independent and context doesn't "bleed together."
- The real lever is treating context as a structured, visible artifact rather than a one-directional transcript; the UI shape, not model complexity, is what makes these work.

**Importance** ★★★★☆ (4/5)
*A concrete, reusable pair of patterns for anyone building LLM products beyond the default chat box.*

**Read in full?** Read in full
*The full article has working demos and the exact tool/prompt definitions (per-row cell constraints, the three node response types) that make the patterns implementable.*
