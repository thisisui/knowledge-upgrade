---
date: 2026-06-19
url: https://www.hannahhearth.com/posts/tools-the-vercel-product-design-team-actually-uses
tags: [design, devex, ai]
rating: 3
---

## [Tools the Vercel product design team actually uses](https://www.hannahhearth.com/posts/tools-the-vercel-product-design-team-actually-uses)

**Summary**
Hannah Hearth documents how the Vercel product design team actually works in 2026, noting that even within their small team, everyone is using completely different tools — a signal of how rapidly the design tooling landscape is fragmenting. Timo uses Claude to review Codex's implementation plans before execution, catching unnecessary complexity early. Tom runs multiple concurrent agent threads in Conductor to keep creative momentum going rather than waiting for one process to finish. Sam built a custom Chrome extension for rapid component navigation in production code and a browser tool called UI Fork for toggling between component variations before committing. The team works directly from production code rather than design files, and non-AI tools (Figma, screen recording, before/after comparison) remain in use for specific tasks.

**Key takeaways**
- Using one AI to review another AI's plan (Claude reviewing Codex) before execution is a concrete pattern for catching over-engineering early
- Running parallel agent threads prevents the idle-waiting problem in AI-assisted design — manage multiple threads, don't watch one
- Production-first design is now practical: custom tooling (Chrome extensions, browser-side variant testing) has replaced Figma handoff for implementation work

**Importance** ★★★☆☆ (3/5)
*Concrete workflow patterns from a credible team at the frontier — the Claude-reviews-Codex pattern and UI Fork are worth borrowing directly.*

**Read in full?** Yes
*Specific tool names, custom-built extensions, and the team's individual setups are detailed enough in the original to warrant reading — this is a reference article, not a think-piece.*
