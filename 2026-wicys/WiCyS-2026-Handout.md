# WiCyS 2026 - Framework Quick Reference

**Talk:** Human Communication at Machine Speed  
**Presenter:** [Beatriz Datangel Rodgers](https://linkedin.com/in/bzdata)
**Resources:** github.com/dat-angel/AI-Cyber-Guide 
**Last updated:** March 12, 2026


---

## 🎯 Three Audiences, Three Needs

| Audience | Need | Message Focus |
|----------|------|---------------|
| 🏃 Engineering | Immediate action | What to do NOW |
| 👔 Executive | Business impact | Risk + timeline |
| 👥 Customer | Transparent guidance | What happened + what we did |

---

## 📋 Four Pillars (Every Message)

| Pillar | Question | Answer |
|--------|----------|--------|
| **Target** | Who? | Eng / Exec / Customer |
| **Message** | What? | Impact + Action + Update |
| **Channel** | Where? | Slack / Email / Status |
| **Timing** | When? | Immediate / Hourly |

**Every message must have:** Impact + Action + Next update time

---

## 🚫 Mistake-Prevention Checklist

- ❌ No vague impact (numbers, regions)
- ❌ No delays before first communication (<2 hours)
- ❌ No missing "what to do"
- ❌ No missing "when we'll update"

---

## ⚡ Two-Step Workflow

### Step 1: Get the facts
```bash
/security-check cve [CVE-ID]
```
Looks up NVD, GitHub Advisories, and vendor pages. Returns summary, affected versions, timeline, ecosystem impact. If your AI tool doesn't have web access, paste the advisory text instead.

### Step 2: Write the comms
```bash
/security-brief cve-engineering [CVE-ID]
/security-brief cve-executive [CVE-ID]
/security-brief cve-customer [CVE-ID]
```

**Before you send anything:** Can you answer "are we affected?" If you don't have an SBOM, say so in your first communication.

---

## 📺 Example: Engineering

```
🔴 CVE-2026-2441: Chromium Zero-Day
Affected: All Chromium browsers
Action: Update NOW
Remediation: Root can fix in-place
Updates: 18:00 EST
```

## 📺 Example: Executive

```
Subject: CVE-2026-2441 - Critical Impact Assessment
Systems: ~500 affected | Risk: High
Status: Patching now
Next Update: 18:00 EST
```

## 📺 Example: Customer

```
Subject: Security Advisory: Chromium Browser Update
What happened: Critical Chromium zero-day, actively exploited.
What we're doing: Systems patched, scanning customer environments.
What you should do: Update Chrome/Edge to 126.0.6478.57+.
Status: Mitigated
More info: status.example.com/incidents/2026-2441
```

---

## 🏕️ Your 7-Day Challenge

- [ ] Star the repo
- [ ] Review the skills
- [ ] Customize for YOUR org
- [ ] Test the commands
- [ ] Rewrite the "good" output based on your company/org's writing style
- [ ] Run a tabletop
- [ ] Share with your team

---

**See you soon**
- Beatriz
