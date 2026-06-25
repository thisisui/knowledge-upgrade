---
date: 2026-06-25
url: https://nolanlawson.com/2026/05/25/using-ai-to-write-better-code-more-slowly/
tags: [ai, engineering, devex]
rating: 4
---

## [Using AI to Write Better Code More Slowly](https://nolanlawson.com/2026/05/25/using-ai-to-write-better-code-more-slowly/)

**Summary**
Most people use AI coding tools to produce code faster, often accepting lower quality in exchange for speed. Nolan Lawson argues for the opposite use: deliberately slowing down and using AI models to review code and catch bugs, so the code you ship is higher quality. He runs several different AI models (Claude, Codex, and Cursor's Bugbot) against the same pull request — a proposed code change waiting to be merged — and has them rank the bugs they find by severity, then fixes the important ones. Using multiple different models matters because when they disagree or independently agree, it becomes easier to tell real bugs apart from invented ("hallucinated") ones.

**Key takeaways**
- Run several different AI models on the same code change to review it; the more different models you use, the fewer false or hallucinated bugs survive, because real problems tend to be flagged by more than one.
- Treat AI review as a path to understanding, not just speed: fixing the bugs it surfaces forces you to learn the codebase's pre-existing technical debt, the same way careful debugging did before AI existed.
- Be willing to stop: fix critical and high-priority issues, skip fixes where the effort outweighs the benefit, and abandon a change entirely if review reveals deep architectural problems.

**Importance** ★★★★☆ (4/5)
*A concrete, immediately adoptable workflow that inverts the dominant "AI = faster, sloppier" framing into "AI = slower, better."*

**Read in full?** Yes
*The full article and its comment thread add real-world examples — like AI review exposing a gap in database security rules — that make the multi-model approach tangible.*
