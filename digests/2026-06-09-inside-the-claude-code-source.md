---
date: 2026-06-09
url: https://gist.github.com/Haseeb-Qureshi/d0dc36844c19d26303ce09b42e7188c1
tags: [ai, engineering, tooling]
rating: 4
---

## [Inside the Claude Code Source](https://gist.github.com/Haseeb-Qureshi/d0dc36844c19d26303ce09b42e7188c1)

**Summary**
This is a technical analysis of Claude Code — the AI coding assistant made by Anthropic — written by an engineer who read through approximately 1,900 files of its source code to understand how it is built from the inside. The article explains the surprising design decisions Anthropic made: for example, the entire visual interface of this command-line tool is built using React, a technology that is normally used to build websites, not programs that run in the terminal. The author's main conclusion is that the most valuable part of an AI coding tool is not the AI model itself, but the surrounding code that manages conversations, controls what the AI is allowed to do, and decides what information to send to the AI. This analysis is useful for developers who want to build similar AI-powered tools, or who want to understand why tools like Claude Code behave the way they do.

**Key takeaways**
- The most important part of an AI coding tool is not the AI itself, but the surrounding infrastructure — the code that manages conversation history, handles errors, controls permissions, and decides what context to send to the AI. The author calls this the "harness", and it is where most of the real engineering work lives.
- Claude Code prevents conversations from becoming too long (and too costly) by automatically summarizing older parts of the conversation. It uses four different strategies for this, choosing between them depending on whether a user is actively watching or the tool is running automatically in the background.
- The instructions sent to the AI are split into two parts: a fixed section of about 3,000 words of general rules that never change between sessions, and a variable section with information specific to the current session (such as which files are open). The fixed part is cached so the AI does not have to re-process it every time, which reduces both response time and cost.

**Importance** ★★★★☆ (4/5)
*Rare inside look at how a production AI coding tool is actually engineered — directly actionable for anyone building AI-powered developer tooling.*
