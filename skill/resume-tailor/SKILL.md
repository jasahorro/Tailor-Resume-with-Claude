---
name: "resume-tailor"
description: "Tailors a resume and writes a matching cover letter for a specific job. Use this skill when the user provides a job posting URL (or pastes a job description) and wants their resume and cover letter customized for that role. Trigger whenever the user mentions tailoring, customizing, or applying their resume to a job, or pastes a job link, even if they don't explicitly mention a \"skill\"."
---

# Resume Tailor

## Inputs

* **Job URL** (required): Use `web_fetch` to scrape. If login-walled, ask user to paste the text.
* **Base resume**: Read from `~/Desktop/resume-project/resume.md`. If missing, ask the user to paste it and save it there first.
* **User overrides**: Honor any emphasis notes the user provides.

## Steps

**1. Scrape** the job posting via `web_fetch`. Extract: title/level, company, responsibilities, required vs. preferred qualifications, tech stack, and soft skill signals.

**2. Positioning brief** (internal, don't show unless asked):

* What outcome is this hire solving for in 6-12 months?
* Seniority signal: IC executor / Senior IC / Lead+Manager
* Implied requirements (e.g., "cross-functional" = stakeholder management)
* Culture signal: startup / enterprise / mission-driven
* Keywords appearing 2+ times (must be mirrored naturally)

**3. Gap analysis:** for each required qualification: ✅ Covered / ⚠️ Implied but needs reframing / ❌ Missing (note it, never fabricate)

**4. Rewrite the resume**

* Bullets: impact-first ("Delivered X, resulting in Y"), mirror JD verb vocabulary, add `[METRIC NEEDED]` where numbers are missing (never invent them), cut irrelevant bullets
* Summary: rewrite completely. Role title, value prop, echo company's problem (3-4 sentences)
* Skills: reorder by JD relevance, remove irrelevant entries
* Experience: trim older/less relevant roles to 2 bullets
* Hard constraint: never change job titles, dates, companies, degrees, or facts. Only reframe.

**5. Cover letter:** problem-first opening (not "I'm excited to apply"), two story paragraphs (situation → action → outcome) mapped to the top 2 JD requirements, confident specific close. Tone matches culture signal: startup = bold/direct, enterprise = measured, mission-driven = values-forward.

**6. Save outputs**

~/Desktop/resume-project/tailored-resume.md
~/Desktop/resume-project/cover-letter.md
~/Desktop/resume-project/tailoring-notes.md

Tailoring notes should include: positioning brief summary, keyword coverage table (✅/⚠️/❌), what changed and why, all `[METRIC NEEDED]` flags, and match confidence (Strong / Moderate / Stretch + one-line rationale).

**7. Summarize:** tell the user: match confidence, the 1-2 biggest framing changes, any `[METRIC NEEDED]` flags to fill in, and the cover letter angle chosen. 

**8. Interview prep:** Generate 5 interview prep questions based on:
   - Key technical skills mentioned in the job description
   - Behavioral questions tied to the role's responsibilities
   - Questions about the candidate's relevant experience from the tailored resume

**9. For each question, provide:**
   - The question itself
   - A suggested talking point drawn from the TAILORED resume (not the base resume)
   - A tip for structuring the answer (e.g., use the STAR method for behavioral questions)

**10. Save** the interview prep questions to ~/Desktop/resume-project/interview-prep.md
