---
date: 2026-06-25
url: https://tiptap.dev/docs/hocuspocus/getting-started/overview
tags: [engineering, tooling, devex]
rating: 3
---

## [Hocuspocus Overview](https://tiptap.dev/docs/hocuspocus/getting-started/overview)

**Summary**
Hocuspocus is an open-source backend server that adds real-time collaboration — many people editing the same document at once, like in Google Docs — to your own application. It is built on top of Y.js, a library that uses a technique called a CRDT (conflict-free replicated data type), which lets edits from different users be merged automatically without conflicts, no matter what order they arrive in. Hocuspocus runs as a WebSocket server (a persistent two-way connection between browser and server) that relays and stores these edits, and it also supports offline-first work, meaning a user can keep editing while disconnected and have their changes merge cleanly when they reconnect. It is mainly aimed at developers building collaborative text editors, and works with editors like Tiptap, ProseMirror, Slate, Quill, and Monaco.

**Key takeaways**
- The hard part of multi-user editing — merging simultaneous changes without conflicts — is handled by Y.js's CRDT, the same way Git merges distributed commits regardless of order; Hocuspocus is the server that moves and persists those changes.
- It is editor-agnostic and runtime-flexible: works with Tiptap, ProseMirror, Slate, Quill, and Monaco, and runs on Node.js, Bun, Deno, and Cloudflare Workers.
- It scales horizontally to millions of users by using Redis to coordinate state across multiple server instances.

**Importance** ★★★☆☆ (3/5)
*A solid, concrete starting point if you specifically need to add live collaboration to an app; irrelevant otherwise.*

**Read in full?** Summary is enough
*This is an orientation page; the real value is in the setup and configuration guides that follow it, not in this overview.*
