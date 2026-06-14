---
date: 2026-06-14
url: https://research.perplexity.ai/articles/designing-refining-and-maintaining-agent-skills-at-perplexity
tags: [ai, engineering, devex]
rating: 5
---

## [Designing, Refining, and Maintaining Agent Skills at Perplexity](https://research.perplexity.ai/articles/designing-refining-and-maintaining-agent-skills-at-perplexity)

**Summary**
This article documents Perplexity's internal system for building "Skills" — modular packages of instructions and context that tell an AI agent how to perform a specific, specialized task. Unlike traditional software documentation, a Skill is not written for humans to read: it is written for a language model to consume at runtime, which means the design principles are almost the opposite of normal code or docs. The article explains how to structure a Skill as a folder of files that load progressively (only the short description loads by default; the full instructions load on demand; heavy reference files load only when explicitly needed), how to write descriptions that act as routing triggers rather than feature summaries, and how to grow Skill quality over time by accumulating "gotchas" — specific failure cases the agent previously got wrong. The core test for whether a piece of content belongs in a Skill: "Would the agent get this wrong without this instruction?" — if not, remove it, because every word costs tokens for every user in every session.

**Key takeaways**
- Write the description as a routing trigger, not a feature summary: start with "Load when..." and use the exact words a user would type when they have the problem this Skill solves — the description is what decides whether the Skill gets loaded at all.
- Prioritize gotchas (specific failure modes and edge cases) over step-by-step instructions — models already know common procedures; the rare, non-obvious traps are where Skill content earns its token cost.
- Skills load in three tiers (index ~100 tokens always, full body ~5,000 tokens on trigger, reference files unbounded on demand) — design content to sit at the right tier so rarely-needed details don't tax every session.

**Importance** ★★★★★ (5/5)
*A rare, concrete, production-tested framework for AI agent Skill design — directly applicable to anyone building or maintaining Skills in Claude Code or similar agent systems.*
