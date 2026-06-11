---
date: 2026-06-11
url: https://neciudan.dev/whats-new-in-javascript
tags: [engineering, tooling]
rating: 4
---

## [What's New in JavaScript: ES2025, ES2026, and Beyond](https://neciudan.dev/whats-new-in-javascript)

**Summary**
JavaScript (the programming language that runs in all web browsers and on servers via Node.js) is updated annually by a standards committee called TC39. This article is a comprehensive survey of what is new in the ES2025 and ES2026 editions, covering features that are already available in modern browsers and Node.js today. It explains each new feature in concrete terms, gives browser support ranges, and ends with a practical list of old patterns that modern equivalents now replace — for example, the new `Temporal` API replaces the long-broken built-in `Date` object, `using` replaces try/finally cleanup blocks, and `Map.getOrInsert()` replaces the common "check if key exists, then set it" pattern. It also notes that AI coding assistants trained before 2025 still suggest outdated approaches, and recommends system prompt rules to push them toward modern APIs.

**Key takeaways**
- ES2025 features with full cross-browser and Node 22+ support today: Set methods (`.union()`, `.intersection()`, `.difference()`), Iterator Helpers (lazy `.map()`/`.filter()` without converting to arrays), `Promise.try` (unified error handling), and `RegExp.escape` (safe regex construction from user input).
- ES2026 features already shipping across major browsers: `Math.sumPrecise` (accurate floating-point addition — critical for financial calculations), `Map.getOrInsert()` (retrieve-or-create in one call), `Array.fromAsync` (collect async streams into arrays), and `Error.isError()` (reliable cross-context error detection).
- `Temporal` (a complete, timezone-aware date/time system replacing `Date`) and the `using` keyword (guaranteed resource cleanup, like Python's `with` statement) are Stage 3 proposals — available via polyfill or TypeScript now, with native browser rollout underway.

**Importance** ★★★★☆ (4/5)
*Dense practical reference — several of these features replace patterns that appear in almost every JavaScript codebase; worth bookmarking and cross-checking against your current utility code.*
