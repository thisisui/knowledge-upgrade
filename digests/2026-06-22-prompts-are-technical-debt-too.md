---
date: 2026-06-22
url: https://www.seangoedecke.com/prompts-are-technical-debt-too/
tags: [ai, engineering, devex]
rating: 3
---

## [Prompts are technical debt too](https://www.seangoedecke.com/prompts-are-technical-debt-too/)

**Summary**
Custom AI prompts accumulate as technical debt — and unlike code debt, they decay silently. A prompt carefully tuned for one model version may quietly become ineffective when the model is updated, and the degradation is hard to notice because there is no type error or test failure to signal it. The author argues that maintaining extensive bespoke prompt configurations (custom MCP setups, behavior-steering techniques like "think step by step", elaborate AGENTS.md files) creates an ongoing maintenance burden that rarely pays off. His recommendation: minimize custom prompting, rely on third-party tools like Claude Code or Cursor whose teams actively re-optimize prompts for each new model, and keep any AGENTS.md focused on concrete project facts rather than behavior steering. A basic setup on a current model will usually outperform a heavily-tuned system built around an older one.

**Key takeaways**
- Prompts rot silently with model updates — this makes them higher-risk than code debt, which at least fails loudly
- Outsource prompt maintenance to specialized tools (Claude Code, Cursor, Copilot) rather than maintaining bespoke configurations in-house
- AGENTS.md files should contain facts about the project, not instructions about how the AI should think or behave

**Importance** ★★★☆☆ (3/5)
*Useful counter-pressure against prompt engineering maximalism — the "delete prompts opportunistically" advice is underrated, especially for teams maintaining growing CLAUDE.md files.*

**Read in full?** Summary is enough
*The article is short and makes one clear point; the summary captures the full argument and all actionable recommendations.*
