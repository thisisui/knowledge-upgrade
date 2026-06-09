---
date: 2026-06-09
url: https://martinfowler.com/articles/reduce-friction-ai/encoding-team-standards.html
tags: [ai, engineering, devex]
rating: 3
---

## [Encoding Team Standards](https://martinfowler.com/articles/reduce-friction-ai/encoding-team-standards.html)

**Summary**
When a team uses an AI coding assistant, experienced developers get much better results than beginners — not because they are better at coding, but because they naturally include more context in their requests to the AI, such as which patterns to follow, which security rules to apply, and how the code should be structured. The article proposes a solution: instead of relying on each developer to know what to ask, the team writes a set of instruction files that are given to the AI automatically on every request. These instruction files are saved alongside the code in the same version control system (git) that the team already uses, so they are shared, kept up to date, and improve over time just like code does. This way, a junior developer gets the same quality of AI output as a senior, because the AI already has the team's knowledge built into its instructions.

**Key takeaways**
- Each instruction file should have four parts: (1) a description of the role the AI should play (e.g., "act as a senior engineer following our team's patterns"), (2) a list of information the AI needs before it starts, (3) a prioritized list of rules — what is a hard requirement, what is strongly recommended, and what is optional — and (4) a description of what the output should look like.
- Save these instruction files in the same git repository as your source code, not in a separate wiki or document system — this way the whole team can review and improve them together, and they stay in sync with the codebase instead of becoming outdated documents nobody reads.
- To figure out what rules to put in the instructions, interview your senior engineers with specific questions: "What would make you reject this code in a review?", "What mistakes do you always have to correct?", "What security risks do you always check for?" — this converts knowledge that only exists in people's heads into written rules the AI can follow.

**Importance** ★★★☆☆ (3/5)
*Useful for teams of 15 or more where inconsistent AI output is already a visible problem, but it is an improvement to an existing workflow rather than a new capability.*
