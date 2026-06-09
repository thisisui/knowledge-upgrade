---
date: 2026-06-09
url: https://dbushell.com/2026/02/20/visually-hidden/
tags: [engineering, design]
rating: 3
---

## [Everything You Never Wanted to Know About Visually-Hidden](https://dbushell.com/2026/02/20/visually-hidden/)

**Summary**
This article examines a CSS technique called "visually-hidden" — a way to add text to a web page that is invisible to sighted users but still readable by screen readers (software used by blind and visually impaired people to hear web page content read aloud). The technique has been in use since 2004 and consists of a CSS class that makes an element take up no visible space without actually removing it from the page, because removing it from the page would also remove it from screen readers. The article traces 20 years of incremental fixes — adjustments added to handle edge cases in specific browsers and screen readers — and asks whether simpler modern approaches could replace the original "kitchen-sink" version. The conclusion is that no single minimal version has been proven to work reliably across all combinations of browsers and screen readers, and that the best strategy is still to write well-structured HTML so the technique is rarely needed in the first place.

**Key takeaways**
- The traditional "visually-hidden" CSS class has accumulated many properties over 20 years because each one was added to fix a specific bug in a specific tool — removing any of them risks breaking accessibility for users of that tool. Simpler modern alternatives (using `clip-path` or `transform: scale(0)`) work in most cases but have not been tested across every relevant combination of browser and screen reader software.
- Multiple accessibility experts warn that this technique is overused: developers reach for visually-hidden text to compensate for poorly structured HTML, instead of fixing the underlying structure. A button that only makes sense with a hidden label is a button that was designed badly; the hidden label is a workaround, not a solution.
- One practical problem specific to this technique: sighted users who also use a screen reader (for example, people with low vision who use both sight and audio) cannot locate the hidden content on screen because it has no visible position — the screen reader announces something the user cannot see or point to, which causes confusion.

**Importance** ★★★☆☆ (3/5)
*Deep historical context on a niche but widely-used CSS pattern — useful if you maintain a design system or write accessibility-sensitive UI code, but not urgent reading otherwise.*
