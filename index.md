---
layout: home
title: Knowledge Digests
---

A personal reading log. Each entry is a short summary of an article worth remembering — what it says, why it matters, and what to do differently as a result.

<div id="tag-filters" style="margin-bottom:1rem"></div>

| # | Date | Title | Tags | Rating | Summary |
|---|------|-------|------|--------|---------|
| 1 | 2026-06-09 | [Encoding Team Standards](digests/2026-06-09-encoding-team-standards.md) | ai, engineering, devex | ★★★☆☆ | Encode senior engineers' prompt instincts as versioned repo instruction files so AI output quality is consistent across the team. |
| 2 | 2026-06-09 | [Inside the Claude Code Source](digests/2026-06-09-inside-the-claude-code-source.md) | ai, engineering, tooling | ★★★★☆ | Technical breakdown of how Claude Code is built — the real value is in the infrastructure around the AI, not the AI model itself. |
| 3 | 2026-06-09 | [The Beginning of Programming as We'll Know It](digests/2026-06-09-the-beginning-of-programming-as-well-know-it.md) | ai, engineering, devex | ★★★☆☆ | AI generates code faster but not better — human judgment and review remain essential to ship quality software. |
| 4 | 2026-06-09 | [The Design Engineer Symptom](digests/2026-06-09-the-design-engineer-symptom.md) | design, engineering, ai, product | ★★★☆☆ | AI coding tools let designers ship UI changes without developers — real case studies show promise but testing remains the hard part. |
| 5 | 2026-06-09 | [What If AI Just Makes Us Work Harder?](digests/2026-06-09-what-if-ai-just-makes-us-work-harder.md) | ai, business, leadership | ★★★☆☆ | AI is likely to increase total work output, not free up time — the same pattern seen with email and PowerPoint, backed by current research. |
| 6 | 2026-06-09 | [The Machines Are Fine. I'm Worried About Us.](digests/2026-06-09-the-machines-are-fine.md) | ai, research, leadership | ★★★★☆ | Using AI to skip the hard parts of learning produces credentials without capability — the erosion is gradual and invisible until years later. |
| 7 | 2026-06-09 | [Designers Finally Have a Say in the Product They Design](digests/2026-06-09-designers-finally-have-a-say.md) | design, ai, product, engineering | ★★★☆☆ | AI lets designers implement their own interface details directly, removing the translation loss that happens when developers approximate design specs. |
| 8 | 2026-06-09 | [On Velocity Gating](digests/2026-06-09-on-velocity-gating.md) | engineering, design | ★★★★☆ | Three-layer technique to prevent hover flickering on dense UI rows: EMA speed smoothing, split engage/disengage thresholds, and directional hysteresis. |
| 9 | 2026-06-09 | [Everything You Never Wanted to Know About Visually-Hidden](digests/2026-06-09-visually-hidden.md) | engineering, design | ★★★☆☆ | 20-year history of the visually-hidden CSS hack — no simpler modern version is proven safe yet; best strategy is writing HTML that rarely needs it. |
| 10 | 2026-06-09 | [What To Know in JavaScript (2026 Edition)](digests/2026-06-09-what-to-know-in-javascript-2026.md) | engineering, tooling | ★★★★☆ | Full survey of the JS ecosystem in 2026: Temporal API, TypeScript v7 (10× faster), framework acquisitions, and serious npm supply-chain security incidents. |
| 11 | 2026-06-09 | [Simplest Supply Chain Defense](digests/2026-06-09-simplest-supply-chain-defense.md) | security, engineering, tooling | ★★★★☆ | Add one line to your package manager config to block packages newer than 7 days — blocks 11 of 21 documented supply chain attacks at zero ongoing cost. |
| 12 | 2026-06-09 | [Burnout Is Real for Open Source Maintainers](digests/2026-06-09-burnout-is-real-for-open-source-maintainers.md) | engineering, leadership | ★★☆☆☆ | Lodash creator on 5 years of burnout — the fix is governance (shared ownership, steering committee) not individual willpower. |
| 13 | 2026-06-09 | [The Great CSS Expansion](digests/2026-06-09-the-great-css-expansion.md) | engineering, design | ★★★★☆ | CSS now replaces Floating UI, GSAP, Radix popovers, and dialog libraries natively — up to 322 kB of JavaScript removable today. |
| 14 | 2026-06-09 | [AI Fatigue Is Real and Nobody Talks About It](digests/2026-06-09-ai-fatigue-is-real.md) | ai, engineering, devex | ★★★☆☆ | AI shifts your role to reviewing rather than creating — which is more draining. Practical rules: 3-attempt limit, 70% threshold, mornings AI-free. |
| 15 | 2026-06-09 | [Making Emojis and Icons Screen Reader Accessible](digests/2026-06-09-making-emojis-and-icons-accessible.md) | engineering, design | ★★★☆☆ | Three HTML patterns for emojis and icon-only buttons: aria-label, aria-hidden + sr-only span, or visible text label — each for different design constraints. |
| 16 | 2026-06-09 | [Craft Is Untouchable](digests/2026-06-09-craft-is-untouchable.md) | ai, design, leadership | ★★★☆☆ | AI doesn't kill craft — it makes it easier to skip. The discipline of iteration and refinement is still what separates adequate from excellent work. |
| 17 | 2026-06-10 | [How To Use Standard HTML Video & Audio Lazy-Loading on the Web Today](digests/2026-06-10-how-to-use-standard-html-video-and-audio-lazy-loading-on-the-web-today.md) | engineering, design | ★★★☆☆ | Add `loading="lazy"` to `<video>` and `<audio>` elements to defer loading until they're visible — but only for below-fold media. |

<script>
(function () {
  const table = document.querySelector("table");
  const container = document.getElementById("tag-filters");
  if (!table || !container) return;

  const rows = Array.from(table.querySelectorAll("tbody tr"));
  const tagIndex = 3; // 0-based column index for Tags

  const allTags = new Set();
  rows.forEach(row => {
    const cell = row.cells[tagIndex];
    if (!cell) return;
    cell.textContent.split(",").forEach(t => allTags.add(t.trim()));
  });

  let active = null;

  const pills = Array.from(allTags).sort().map(tag => {
    const btn = document.createElement("button");
    btn.textContent = tag;
    btn.style.cssText = "margin:0 4px 4px 0;padding:3px 10px;border:1px solid #aaa;border-radius:12px;background:#fff;cursor:pointer;font-size:0.85em";
    btn.addEventListener("click", () => {
      if (active === tag) {
        active = null;
        rows.forEach(r => r.style.display = "");
        pills.forEach(p => p.style.background = "#fff");
      } else {
        active = tag;
        rows.forEach(r => {
          const cell = r.cells[tagIndex];
          const tags = cell ? cell.textContent.split(",").map(t => t.trim()) : [];
          r.style.display = tags.includes(tag) ? "" : "none";
        });
        pills.forEach(p => p.style.background = p === btn ? "#e8e8e8" : "#fff");
      }
    });
    return btn;
  });

  pills.forEach(p => container.appendChild(p));
})();
</script>
