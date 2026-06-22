---
date: 2026-06-22
url: https://tenphi.me/blog/why-i-spent-years-trying-to-make-css-states-predictable/
tags: [engineering, tooling]
rating: 3
---

## [Why I spent years trying to make CSS states predictable](https://tenphi.me/blog/why-i-spent-years-trying-to-make-css-states-predictable/)

**Summary**
When two CSS rules have the same specificity, the one defined later in the file wins — a rule that makes component state logic fragile and hard to extend. Andrey Yamanov describes building Tasty, a CSS compiler that solves this by letting developers declare component state priorities declaratively, then generating mutually exclusive selectors so that no two rules ever compete. Instead of writing competing `:hover` and `[disabled]` rules and hoping the order is right, you describe which state takes precedence and the compiler ensures they never overlap. The system was validated in production across a 100+ component UI kit. His core insight: component states should be easy to describe and impossible to make ambiguous.

**Key takeaways**
- CSS specificity + source order create a hidden resolution system that developers must maintain manually — Tasty externalises this into a compiler.
- Declarative state maps (which state wins over which) compile to non-overlapping selectors like `.t0:hover:not(:active):not([disabled])`, eliminating ambiguity at the source.
- The same approach scales to media queries, container queries, pseudo-classes, and nested selectors.

**Importance** ★★★☆☆ (3/5)
*Useful for anyone building or maintaining a component library; niche for those who aren't.*

**Read in full?** Summary is enough
*The summary captures the core problem and solution; the full article adds implementation detail for Tasty users specifically.*
