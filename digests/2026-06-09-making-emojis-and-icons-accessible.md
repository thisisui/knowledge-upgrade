---
date: 2026-06-09
url: https://blog.pope.tech/2026/04/01/making-emojis-and-icons-screen-reader-accessible/
tags: [engineering, design]
rating: 3
---

## [Making Emojis and Icons Screen Reader Accessible](https://blog.pope.tech/2026/04/01/making-emojis-and-icons-screen-reader-accessible/)

**Summary**
Screen readers — software that reads web page content aloud for blind and visually impaired users — handle emojis and icons in ways that often conflict with the developer's intention. An emoji like 🙏 gets announced by its official technical name ("hands pressed together") rather than what the author meant ("thank you"), and an icon-only button — a button that shows only a picture symbol with no visible text label — gets announced as having no name at all, leaving the user unable to know what the button does. This article explains three HTML techniques for fixing these problems: adding a visible text label next to the symbol, adding a text label that is invisible on screen but readable by screen readers, or adding an invisible descriptive name directly to the HTML element using a special attribute. Choosing between these three depends on the visual design constraints of the page.

**Key takeaways**
- For icon-only buttons (buttons that show only a picture with no text label), add an `aria-label` attribute to the button element with a short description of what the button does, and add `aria-hidden="true"` to the icon inside it so the screen reader ignores the icon and reads only your label. Example: `<button aria-label="Search"><svg aria-hidden="true">...</svg></button>`.
- For emojis used to convey meaning, place the emoji inside a `<span aria-hidden="true">` element (which tells the screen reader to ignore it), then immediately follow it with a `<span class="sr-only">` element containing the actual meaning in plain words. The "sr-only" CSS class makes text invisible on screen but still readable by screen readers — it uses the same visually-hidden technique discussed in a separate digest.
- When emojis cannot be controlled via HTML (for example, in social media posts), place them at the end of sentences rather than in the middle, so the screen reader reads the sentence naturally before encountering the emoji name announcement. Keep the number of emojis small to reduce the number of interruptions.

**Importance** ★★★☆☆ (3/5)
*Practical and specific — the three code patterns are immediately usable, though this is incremental reference knowledge rather than a technique most developers need to revisit regularly.*
