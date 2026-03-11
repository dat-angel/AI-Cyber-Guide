# Security Brief Skill

**Job:** "Turn that understanding into a message for humans."

Run this skill after Security Check to generate draft comms for different audiences. Works with any AI tool — Claude, ChatGPT, Copilot, Cursor, Gemini, or a terminal client.

---

## Prompt Templates

### Engineering (Slack)

> Skill: Security Brief – Engineering
> Input: [paste Security Check output]
> Audience: Engineering / SRE
> Format as a Slack message with:
> - Target
> - Impact
> - Action (what to do now)
> - Next update time
> - Unknowns / open questions
> Tone: direct, action-oriented.

### Executive (Email)

> Skill: Security Brief – Executive
> Input: [paste Security Check output]
> Audience: Executives
> Format the response with these sections:
> - Target
> - Impact
> - Action
> - Next update
> - Unknowns
> Tone: concise, clear, professional. Keep it under 200 words.

### Customer (Email)

> Skill: Security Brief – Customer
> Input: [paste Security Check output]
> Audience: Customers / partners
> Format the response with these sections:
> - What happened
> - What we're doing
> - What you should do
> - Status
> - More info
> Tone: transparent, professional, not alarmist. Keep it under 200 words.

---

## Examples — CVE-2026-2441 (Chrome Zero-Day)

### Engineering — Good Output

```
🔴 CVE-2026-2441: Chromium Zero-Day (Actively Exploited)
Affected: All Chromium-based browsers, headless Chrome, CI/CD
CVSS: 9.8 (Critical)
Action: Update NOW
Remediation: Root can fix in-place (no upgrade needed)
Updates: Next huddle at 18:00 EST
```

### Executive — Good Output

```
Subject: CVE-2026-2441 - Critical Impact Assessment

Summary: Critical zero-day in Chromium, actively exploited.
Severity: CVSS 9.8 - Critical
Systems: All endpoints with Chromium browsers | ~500 affected
Status: Patches rolling out
Risk: High - active exploitation confirmed
Next Update: 18:00 EST
```

### Customer — Good Output

```
Subject: Security Advisory: Chromium Browser Update

What happened: A critical vulnerability was discovered in Chromium-
based browsers that is being actively exploited in the wild.
What we're doing: We've confirmed our systems are patched and are
scanning all customer-facing environments.
What you should do: Update Chrome/Edge to version 126.0.6478.57+.
If you use headless Chrome in CI/CD, pin to the patched version.
Status: Mitigated — patches deployed across our infrastructure.
More info: status.example.com/incidents/2026-2441
```

---

## What Weak Output Looks Like

**Executive — Weak:**

> We recently became aware of a serious Linux vulnerability that may impact some of our systems. Our teams are investigating and will provide more information as it becomes available. In the meantime, please be assured that we take security very seriously and are working hard to address the issue.

Problems:
- No specific target (who is supposed to act or decide).
- No clear impact, scope, or whether we're actually affected.
- No action for the reader, and no concrete next update time.

**Customer — Weak:**

> We are aware of a recently disclosed security issue. Our security team is looking into it and we will update you shortly. We take the security of our customers very seriously.

Problems:
- "Looking into it" — no specifics on what's happening.
- "Shortly" — no concrete timeline.
- No action for the customer (do they need to do anything?).
- No link to a status page or further information.

---

## SBOM Gate

Before generating any communication, ask: **Can you answer "are we affected?"**

If you don't have an SBOM (Software Bill of Materials), your first message must say so:
> "We are currently inventorying our dependencies to confirm exposure. We will update by [time]."

Don't communicate without knowing your own exposure first. That's how you end up walking back optimistic statements.

---

## How to Run in Any Tool

| Tool | Method |
|------|--------|
| **Claude / ChatGPT / Gemini** | Paste the prompt template with Security Check output. |
| **Perplexity** | Paste the prompt. Works in the same thread as Security Check. |
| **Cursor / Windsurf** | Add to `.cursorrules` or project rules, then reference in chat. |
| **VS Code + Copilot** | Add to `.github/copilot-instructions.md`, then ask in chat. |
| **Terminal LLM (llm, aichat, etc.)** | Pipe the prompt as stdin or paste into the session. |
| **Offline / local LLM** | Paste Security Check output manually, then run the prompt. |

---

*This is Step 2 of the two-step workflow. Run Security Check first to get the facts, then Security Brief to format for your audience.*
