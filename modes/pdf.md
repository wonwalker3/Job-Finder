# Mode: pdf — Tailored resume PDF generation

This mode generates a tailored, upload-ready PDF resume for a specific role.

The goal is not to invent a new candidate.
The goal is to make the existing candidate look **clearer, tighter, and more relevant** for a real job.

---

## PDF generation goals

Use this mode to:
- tailor a resume to a specific job description
- improve ATS keyword alignment honestly
- surface the right proof points faster
- produce a clean PDF ready to upload

---

## Required pipeline

1. Read `cv.md`
2. Read `config/profile.yml`
3. Read `article-digest.md` if present
4. Read the job description or extract it from the URL
5. Identify the role family / archetype
6. Extract the most important keywords and themes from the JD
7. Reframe the resume truthfully for that role
8. Build HTML using `templates/cv-template.html`
9. Generate PDF via `node generate-pdf.mjs`
10. Update tracker/report if this role already exists in the system

---

## Tailoring rules

### Always do
- rewrite the summary for the actual role
- prioritize the most relevant experience and projects
- naturally align wording with the JD
- surface real proof points early
- keep it recruiter-readable in a fast scan

### Never do
- invent experience
- invent metrics
- claim tools/skills the candidate does not have
- cram in garbage keywords that break readability
- generate a tailored resume before understanding the JD

---

## ATS rules

Keep the resume ATS-friendly:
- single-column layout
- standard section headings
- selectable text
- no important content hidden in graphics
- no weird multi-column tricks
- strong keyword coverage in summary, experience, and skills

---

## Resume strategy

Prioritize this section order:
1. Header
2. Professional Summary
3. Core Competencies / Skills
4. Work Experience
5. Projects / Case Studies
6. Education / Certifications

### Summary strategy
The summary should answer:
- what kind of operator/builder this person is
- why they fit this role family
- what evidence makes them credible

### Experience strategy
For each relevant role:
- move the strongest bullets up
- rewrite bullets for relevance and clarity
- favor outcomes and leverage over vague responsibility language

### Projects strategy
Surface only the most relevant 2–4 projects or proof points.
If a project is not helping this role, don’t waste space on it.

---

## Output expectations

Return:
- output PDF path
- page count
- a short note on what changed
- whether the tracker/report should be updated

Suggested output file naming:

`output/resume-{company-slug}-{YYYY-MM-DD}.pdf`

---

## Tracker/report behavior

If the role already has a report:
- update the report header `PDF` field
- update tracker PDF status to ✅

If the role has not been evaluated yet, say so instead of pretending the rest of the pipeline already exists.

---

## Tone rules

Tailored resume language should sound:
- sharp
- credible
- concrete
- readable in 6 seconds

Not:
- bloated
- jargon-drunk
- fake-passionate
- over-engineered
