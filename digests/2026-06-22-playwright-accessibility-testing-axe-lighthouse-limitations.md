---
date: 2026-06-22
url: https://www.davidmello.com/software-testing/test-automation/playwright-accessibility-testing-axe-lighthouse-limitations
tags: [engineering, tooling, devex]
rating: 4
---

## [Playwright Accessibility Testing: What axe and Lighthouse Miss](https://www.davidmello.com/software-testing/test-automation/playwright-accessibility-testing-axe-lighthouse-limitations)

**Summary**
Automated accessibility testing tools like axe and Lighthouse — tools commonly used in Playwright test suites to check that websites work for people with disabilities — detect only 30–57% of real accessibility problems. The article documents ten specific categories of defects that automated scans structurally cannot catch: things like a toggle button whose text label says "switch to dark mode" even after dark mode is already on, or a modal dialog that has the correct technical attributes but still traps keyboard users because focus never returns when the dialog closes. The article provides concrete Playwright code patterns for catching these defects, such as scanning contrast after triggering hover and focus states, and verifying that interactive components actually trap and return focus. The core argument is that automated scanning is a regression-prevention floor, not a complete audit — the remaining 40–70% of problems require manual testing with real screen readers and human judgment about whether text actually communicates meaning.

**Key takeaways**
- Automate what is reliably detectable (missing alt text, invalid ARIA structure, regressions) — but treat a passing axe scan as the beginning of accessibility testing, not the end
- Dynamic content is a major gap: static `aria-label` values on toggle controls, modal focus trapping/return, and dynamically revealed content all require custom Playwright test code beyond the default axe scan
- Real-screen-reader testing (NVDA, JAWS, VoiceOver) and manual keyboard navigation are not optional extras — they are the only way to catch the majority of accessibility defects

**Importance** ★★★★☆ (4/5)
*Highly actionable: gives specific Playwright patterns for the most common automation blind spots, with statistics from authoritative sources (WebAIM, W3C, Deque) to justify the investment in manual testing.*

**Read in full?** Yes
*The full article includes working Playwright code examples for each gap category — the summary captures the argument but the code patterns are the practical payoff.*
