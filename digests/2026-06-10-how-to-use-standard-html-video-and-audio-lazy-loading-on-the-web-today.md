---
date: 2026-06-10
url: https://engineering.squarespace.com/blog/2026/how-to-use-standard-html-video-and-audio-lazy-loading-on-the-web-today
tags: [engineering, design]
rating: 3
---

## [How To Use Standard HTML Video & Audio Lazy-Loading on the Web Today](https://engineering.squarespace.com/blog/2026/how-to-use-standard-html-video-and-audio-lazy-loading-on-the-web-today)

**Summary**
Web browsers can now delay loading video and audio files until the user actually scrolls to where those elements appear on the page — a technique called lazy-loading. Previously, browsers only supported this for images and iframes; video and audio always loaded immediately, even if the user never reached them. This article explains how to use the new `loading="lazy"` attribute on `<video>` and `<audio>` HTML elements, what it affects (not just the media file, but also poster images and autoplay), and when you should or should not use it.

**Key takeaways**
- Add `loading="lazy"` to any `<video>` or `<audio>` element to defer loading until it enters the viewport — the syntax is identical to how lazy-loading already works for images.
- Do not apply lazy-loading to media that appears at the top of the page (above the fold); doing so delays the browser from fetching it early and hurts page performance scores.
- Check browser support at runtime with `'loading' in HTMLMediaElement.prototype` before relying on the feature in production.

**Importance** ★★★☆☆ (3/5)
*Straightforward new HTML attribute with a real performance benefit — worth adopting, but only on below-fold media.*
