# Security Check Skill

**Job:** "What is this CVE and how bad is it?"

Use this skill first to understand the vulnerability before drafting any communications. Works with any AI tool — Claude, ChatGPT, Copilot, Cursor, Gemini, or a terminal client.

---

## Step 1: Look Up the CVE

Before generating anything, get the real data. Pick the method that works in your tool:

### If your AI tool has web/search access (Claude, ChatGPT, Perplexity, etc.)

> Search for CVE-YYYY-NNNN. Check NVD (nvd.nist.gov), GitHub Advisory Database, and vendor advisories. Return the raw facts before formatting.

### If your AI tool does NOT have web access (offline Copilot, local LLM, etc.)

Paste the advisory text yourself. Sources to check:

| Source | URL |
|--------|-----|
| NVD | `nvd.nist.gov/vuln/detail/CVE-YYYY-NNNN` |
| GitHub Advisories | `github.com/advisories?query=CVE-YYYY-NNNN` |
| MITRE | `cve.org/CVERecord?id=CVE-YYYY-NNNN` |
| Vendor advisory | Check the affected project's security page |

Then paste the text into your AI tool and continue to Step 2.

---

## Step 2: Generate the Summary

### Prompt Template

Copy-paste into any AI tool:

> Skill: Security Check
> CVE: CVE-YYYY-NNNN
> [If no web access: paste advisory text here]
> Please return 5–7 bullets with:
> - Summary of the vulnerability
> - Affected products / versions
> - Quick timeline (discovery → exploitation → fix)
> - Any obvious ecosystem / supply chain impact
> - Whether active exploitation has been observed
> - SBOM check: Can we answer "are we affected?" If not, flag it.

---

## What Good Output Looks Like

### Example — XZ Utils (CVE-2024-3094)

**Good output:**

- Backdoor planted in **XZ Utils**, a widely used data-compression library on Linux.
- Affects **xz 5.6.0–5.6.1**; some major Linux distros began shipping these versions.
- Backdoor could let an attacker **remotely execute code** on systems using the compromised library.
- Malicious contributions were introduced over **~2 years via social engineering** of the maintainer.
- Discovered by **Andres Freund (Microsoft)** while debugging SSH performance; reported responsibly.
- **Red Hat and others issued "STOP USAGE" guidance within hours**, halting adoption of vulnerable builds.

**Weak output (what to avoid):**

- "There is a serious vulnerability in a Linux component. It could let attackers in."
- "It affects a lot of systems and is rated critical."
- "Admins should patch as soon as possible."

This version is technically "not wrong," but it fails your checklist: no concrete products/versions, no timeline, no ecosystem impact, no sense of scale.

---

### Example — simple-git RCE (CVE-2026-28292)

**Good output:**

- Critical **remote code execution (RCE)** vulnerability in `simple-git`, a popular Node.js library for running Git commands.
- Affects `simple-git` versions **3.15.0 through 3.32.2**; Git treats config keys case-insensitively, which lets attackers bypass earlier patches.
- Attackers can pass `-c PROTOCOL.ALLOW=always` to re-enable the dangerous `ext::` protocol and execute arbitrary OS commands.
- Rated **CVSS 9.8 (Critical)** with network-based exploitation and no authentication or user interaction required.
- Impacts a large ecosystem footprint: roughly **9M of 12.4M weekly npm downloads** come from vulnerable versions.
- Fixed in `simple-git` **3.32.3+**; vendors and projects depending on `simple-git` must bump the library and redeploy.

**Weak output (what to avoid):**

- "There is a remote code execution in a JavaScript library used with git."
- "Attackers might be able to run commands if the app is misconfigured."
- "Updating to the latest version is recommended."

This misses the actionable pieces: which library and versions, how the exploit actually works, how serious it is (CVSS / no auth), and how wide the blast radius is.

---

## How to Run in Any Tool

| Tool | Method |
|------|--------|
| **Claude / ChatGPT / Gemini** | Paste the prompt template. Web search will auto-fetch the CVE. |
| **Perplexity** | Paste the prompt. Built-in search handles lookup. |
| **Cursor / Windsurf** | Add to `.cursorrules` or project rules, then reference in chat. |
| **VS Code + Copilot** | Add to `.github/copilot-instructions.md`, then ask in chat. |
| **Terminal LLM (llm, aichat, etc.)** | Pipe the prompt as stdin or paste into the session. |
| **Offline / local LLM** | Paste advisory text manually, then run the prompt. |

---

*This is Step 1 of the two-step workflow. After Security Check, run Security Brief to generate audience-specific communications.*
