---
date: 2026-06-09
url: https://blog.gitbutler.com/the-great-css-expansion
tags: [engineering, design]
rating: 4
---

## [The Great CSS Expansion](https://blog.gitbutler.com/the-great-css-expansion)

**Summary**
This article documents how CSS — the language used to control the visual appearance of web pages — has in recent years gained the ability to handle interactive behaviors that previously required large JavaScript libraries. JavaScript libraries are separate files of code that a web browser must download and run; popular ones for things like dropdown menus, tooltips, and scroll animations can add hundreds of kilobytes to a page's download size and slow it down. The article lists seven specific CSS features that now replace these libraries natively in the browser, quantifies the download savings (between 44 kB and 146 kB depending on how many you adopt), and explains which browsers already support each one. The historical pattern the author identifies is that web development repeatedly follows this cycle: a capability starts as a JavaScript hack, becomes widespread, and eventually gets built directly into CSS so browsers handle it automatically.

**Key takeaways**
- Five features are now safe to use in production or nearly so: the `dialog` HTML element (handles modal dialogs with focus trapping and keyboard behavior, supported since 2022), the Popover API (handles dropdown visibility, keyboard behavior, and accessibility, supported in all major browsers), Anchor Positioning (handles tooltip and floating element positioning without JavaScript, shipped in Chrome with Firefox and Safari in progress), Scroll-Driven Animations (handles animations triggered by scrolling without JavaScript, runs more efficiently than JS-based alternatives, shipped in Chrome), and View Transitions (handles animated page transitions, shipped in Chrome).
- Across 16 common JavaScript libraries that these CSS features can replace, the article calculates a total of approximately 322 kB of JavaScript that can be removed from a project. Removing this code speeds up page load times and reduces the amount of work the browser has to do to run the page, which improves the real-world performance scores that search engines and users measure.
- Two areas remain firmly in JavaScript territory with no near-term CSS solution: drag-and-drop interactions (moving items by clicking and dragging them), where the built-in browser behavior is too limited for real-world use cases, and overlay scrollbars (scrollbars that appear on top of content rather than pushing it aside), where a CSS proposal exists but has not been resolved or shipped by any browser.

**Importance** ★★★★☆ (4/5)
*Concrete list of JavaScript libraries you can remove today or in the near future — directly actionable for anyone building or maintaining a web application frontend.*
