---
date: 2026-06-25
url: https://piccalil.li/blog/framework-agnostic-design-systems-part-1/
tags: [engineering, design, devex]
rating: 4
---

## [Framework-agnostic Design Systems: A Practical Approach to Web Components](https://piccalil.li/blog/framework-agnostic-design-systems-part-1/)

**Summary**
A design system is a shared library of reusable interface pieces — buttons, inputs, cards — that keeps a product visually and behaviourally consistent. The problem this article tackles is that most teams build these pieces using a specific JavaScript framework (such as React or Vue), which means the whole library has to be rebuilt if the team ever switches frameworks. Scott Riley argues the fix is to build the lowest-level, most basic pieces as "web components" — a built-in browser standard for custom reusable elements that works without any framework — so they outlive whatever framework the app currently uses. The article is part one of a practical walkthrough, ending with a worked example of a button built this way.

**Key takeaways**
- Split your components into two layers: basic, framework-free "system" components (built as web standards web components, kept as simple and declarative as possible) and the "application" components that hold complex state and reactivity inside your chosen framework — this way a future framework migration never forces you to rebuild the base library.
- Keep the base components "dumb": avoid baking reactive, stateful behaviour into them; centralising complex behaviour into shared components is harder to maintain than letting the app handle state.
- Make the browser, not a design tool like Figma, the final source of truth for systemic decisions; document the components two ways — auto-generated technical reference from JSDoc code comments, plus hand-written usage guidance on when and why to use each component.

**Importance** ★★★★☆ (4/5)
*A clear, opinionated architecture for design systems that directly reduces the cost of future framework changes — adoptable now.*

**Read in full?** Yes
*The full article includes the step-by-step button example (conditional rendering, scoped CSS with @scope, theming via custom properties) that turns the principles into copyable practice.*
