---
date: 2026-06-22
url: https://blog.k10s.dev/im-going-back-to-writing-code-by-hand/
tags: [ai, engineering, devex]
rating: 4
---

## [I'm Going Back to Writing Code by Hand](https://blog.k10s.dev/im-going-back-to-writing-code-by-hand/)

**Summary**
The author built a Kubernetes dashboard (a tool for managing server clusters) over seven months using AI-assisted development with Claude, accumulating 234 commits — then had to throw it all away and rewrite from scratch. The core problem: AI coding tools consistently choose the shortest path to make a feature work, but they do not think about the long-term structure of the code. The result was a 1,690-line "god object" (a single file containing all program state, all UI logic, and all business rules tangled together), typed data replaced by positional arrays with magic index numbers, and background tasks mutating shared state in ways that caused unpredictable bugs. The article distills five architectural rules that the author will enforce before writing a single line of AI-generated code next time: explicit architecture documented upfront, isolated per-view state, no scope creep disguised as velocity, typed data structures, and a message-passing pattern for concurrency.

**Key takeaways**
- "AI builds features, not architecture" — without a written `CLAUDE.md` file defining ownership rules and interfaces before coding begins, the AI will always default to the simplest local change, which compounds into structural debt invisibly
- Velocity is a trap: when every feature feels free to add, scope expands naturally until the codebase collapses under its own weight — the psychological illusion of infinite capacity is a direct side effect of AI-assisted development
- The correct concurrency pattern for AI-generated code: background workers produce typed messages, the main event loop applies all mutations atomically — never let background tasks write to shared state directly

**Importance** ★★★★☆ (4/5)
*Concrete post-mortem with specific failure modes and fixes — the five tenets are immediately applicable to any project using AI-assisted development.*

**Read in full?** Yes
*The article includes specific code anti-patterns (the `ra[3]` positional array example, the god object structure) that make the lessons tangible in a way the summary cannot fully convey.*
