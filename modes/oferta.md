# Mode: oferta — Full job evaluation

When the candidate shares a job description or job URL, produce a practical evaluation that helps answer one main question:

> **Is this worth applying to, and if yes, how should we position the candidate?**

The output should be useful, direct, and easy to act on.

---

## Evaluation goals

Every evaluation should help with:
1. deciding whether to apply
2. identifying the strongest angle for the candidate
3. identifying the real risks/gaps
4. preparing for resume tailoring and application answers

---

## Required output structure

Always produce the following sections.

## A) Role snapshot

Summarize the role clearly:
- company
- title
- role family / archetype
- seniority
- remote / hybrid / onsite expectation
- one-line summary of what the job is really asking for

Keep it short and useful.

## B) Candidate match

Map the role against `cv.md` and `article-digest.md` if available.

Cover:
- strongest points of alignment
- relevant proof points
- real gaps
- whether those gaps are fatal, manageable, or mostly cosmetic

Use exact evidence where possible. Do not bluff.

## C) Positioning strategy

Explain how to position the candidate for this role.

Examples:
- why the role makes sense for the candidate
- what angle to lead with
- what to emphasize in resume/interviews
- what to de-emphasize
- whether this is a clean fit or a stretch sell

## D) Compensation / market read

Use available research when possible.

Cover:
- likely compensation band
- whether it appears realistic for the candidate’s target range
- whether the company/role looks worth serious effort

If data is thin, say so.

## E) Resume tailoring plan

Provide a focused plan for tailoring the resume.

Include:
- top summary changes
- top experience bullet changes
- top keyword opportunities
- projects/case studies worth surfacing

Do not rewrite the whole resume in this mode unless explicitly asked.

## F) Interview prep notes

Provide:
- 3–6 likely interview angles or questions
- the best stories / proof points to use
- red flags likely to come up
- how to answer those without sounding fake

## G) Application recommendation

End with a plain recommendation:
- **Strong Apply**
- **Apply**
- **Selective / Maybe**
- **Skip**

Also include a score from 1.0 to 5.0.

### Score guidance
- **4.5–5.0** → strong apply
- **4.0–4.4** → apply
- **3.2–3.9** → selective / maybe
- **below 3.2** → usually skip

The score should reflect reality, not optimism.

---

## Report persistence

After the evaluation, save a markdown report in:

`reports/{###}-{company-slug}-{YYYY-MM-DD}.md`

### Report header format

```markdown
# Evaluation: {Company} — {Role}

**Date:** {YYYY-MM-DD}
**Archetype:** {detected role family}
**Score:** {X.X/5}
**URL:** {job URL or source}
**PDF:** {generated path or pending}
```

Then include sections A–G.

---

## Tracker update

After generating the report:
- create a tracker addition entry
- use the canonical state system
- default to:
  - `Apply Next` for strong targets
  - `Evaluated` for roles that are decent but not yet prioritized
  - `Skip` for poor-fit roles

If using batch/pipeline flow, write TSV additions for merge.

---

## Tone rules

The evaluation should sound:
- blunt when needed
- practical
- recruiter-aware
- candidate-useful

Avoid:
- inflated praise
- generic career-coach sludge
- pretending weak roles are strong matches
- over-explaining obvious things
