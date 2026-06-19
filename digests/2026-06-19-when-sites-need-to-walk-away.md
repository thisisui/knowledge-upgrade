---
date: 2026-06-19
url: https://chriscoyier.net/2026/04/28/when-sites-need-to-walk-away/
tags: [engineering, business]
rating: 3
---

## [When sites need to walk away](https://chriscoyier.net/2026/04/28/when-sites-need-to-walk-away/)

**Summary**
Chris Coyier responds to the Internet Archive's finding that 26% of web pages from 2013–2023 are no longer accessible, using a real case — a local mountain biking site (BendTrails) shutting down unless someone pays $80,000–$90,000 for it — to argue that most sites take an unnecessarily destructive exit. The site's operators plan to take it completely offline rather than leaving it as a free static archive, despite the fact that hosting a static site costs under $4/month. Coyier argues the web needs better tools and norms for graceful archival: converting a live site to a static snapshot when the owner steps away, rather than deleting it. He points to `wget` as a simple tool for creating static archives and suggests this should be a standard practice when shutting down content-rich sites.

**Key takeaways**
- Taking a site fully offline is rarely necessary — a static archive at minimal hosting cost preserves years of community value
- `wget` can convert a live site to a static archive that requires no maintenance and costs almost nothing to host
- The web needs a cultural norm: when stepping away from a site, archive it rather than delete it

**Importance** ★★★☆☆ (3/5)
*Practical and under-discussed — anyone who runs a content site should know this before they shut it down.*

**Read in full?** Summary is enough
*Short post; the summary captures the argument and the concrete tool recommendation fully.*
