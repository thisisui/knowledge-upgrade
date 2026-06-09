---
date: 2026-06-09
url: https://daniakash.com/posts/simplest-supply-chain-defense/
tags: [security, engineering, tooling]
rating: 4
---

## [Simplest Supply Chain Defense](https://daniakash.com/posts/simplest-supply-chain-defense/)

**Summary**
A "supply chain attack" happens when a malicious person secretly adds harmful code to a software package that other developers download and install — rather than attacking your project directly, they attack the shared libraries your project depends on. This article proposes the simplest possible defense: configure your package manager (the tool you use to download these shared libraries) to refuse to install any package that was published less than 7 days ago. The reasoning is that most malicious packages are discovered and removed by the community within hours to days — the notorious axios attack (where a stolen developer account was used to publish harmful code) lasted only 4 hours before being caught. By waiting 7 days before allowing a new package version to be installed, you give the community time to notice and remove the problem before it reaches your project. An analysis of 21 major supply chain attacks from 2018 to 2026 found that 11 of them would have been blocked by this single rule.

**Key takeaways**
- This defense is a one-line configuration change in your package manager. For npm (version 11.10 or newer), add `min-release-age=7` to your `.npmrc` file. For pnpm (version 10.16 or newer), add `minimumReleaseAge: 10080` to your `.npmrc` file. For Yarn 4 (version 4.10 or newer), add `npmMinimalAgeGate: "7d"` to your `.yarnrc.yml` file. Bun and Python's uv package manager also support this setting.
- This defense only works against attacks where a malicious package version is published and quickly removed — it does not protect against long-term infiltrations (like the XZ Utils attack, where malicious code was introduced over two years without detection), attacks where a legitimate maintainer intentionally adds harmful code, or vulnerabilities that exist in real, legitimate code.
- Most dependency automation tools (Renovate and Dependabot — tools that automatically create pull requests to update your project's dependencies) already support a configurable waiting period before applying updates, and they allow security-critical updates to bypass the delay. This means you can get the safety of the delay without slowing down urgent security patches.

**Importance** ★★★★☆ (4/5)
*One configuration line that blocks nearly half of documented supply chain attacks — low effort, high value, and directly applicable to most JavaScript and Python projects today.*
