---
date: 2026-06-19
url: https://webframp.com/posts/the-workflow-collision/
tags: [ai, engineering, product]
rating: 4
---

## [The workflow collision](https://webframp.com/posts/the-workflow-collision/)

**Summary**
Sean Escriva identifies five specific points where human team workflows and AI agent lifecycles are structurally incompatible, and argues the mistake is trying to reconcile them rather than composing them. Human teams use pull-based work (workers self-organize); agents require operator-initiated tasks for security reasons. Human teams plan just-in-time collaboratively; agents need upfront adversarially-reviewed specifications before they start. Human workflows minimize state for clarity; agent systems need granular checkpoints for auditability and the ability to resume after failure. Human workflows treat failure as information to learn from; agent systems prevent failure through gates. The recommended resolution: keep human workflows at the strategic level (design sessions, decisions) and let agent lifecycles operate as sub-processes within implementation phases — composition rather than alignment.

**Key takeaways**
- Don't try to fit agents into your Kanban board — human workflow and agent lifecycle are incompatible at the structural level; compose them instead
- Agents need upfront, adversarially-reviewed specs before execution; human just-in-time planning actively breaks agent reliability
- The human layer owns strategy and design decisions; the agent layer owns execution — the handoff boundary is the specification

**Importance** ★★★★☆ (4/5)
*Precise diagnosis of a failure mode every team integrating agents will hit — the five collision points are a useful checklist for structuring human-agent workflows.*

**Read in full?** Yes
*The five collision points are developed with concrete examples that the summary compresses — worth reading as a reference before restructuring a team's agent workflow.*
