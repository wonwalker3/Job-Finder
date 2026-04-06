# Job-Finder — Codex/OpenClaw Operating Guide

## What this repo is

AI-powered job search automation for Codex/OpenClaw: pipeline tracking, offer evaluation, CV generation, portal scanning, and batch processing.

This repo was forked from `santifer/career-ops`. The original architecture is strong, but it was built around Claude Code. This fork is being adapted into a Codex/OpenClaw-first workflow.

## Current direction

Use this repo as a **personal job-search operating system**:
- evaluate roles
- decide whether to apply
- generate tailored resume PDFs
- draft application answers
- track everything cleanly

Not as a blind mass-application bot.

## Main files

| File | Function |
|------|----------|
| `data/applications.md` | Application tracker |
| `data/pipeline.md` | Inbox of pending URLs |
| `data/scan-history.tsv` | Scanner dedup history |
| `portals.yml` | Query and company config |
| `templates/cv-template.html` | HTML template for CVs |
| `generate-pdf.mjs` | Playwright HTML → PDF |
| `cv.md` | Candidate resume source of truth |
| `config/profile.yml` | Candidate identity, targets, comp |
| `article-digest.md` | Proof points / metrics / project evidence |
| `reports/` | Evaluation reports (`{###}-{company-slug}-{YYYY-MM-DD}.md`) |

## First-run onboarding

Before evaluating anything, make sure these exist:

1. `cv.md`
2. `config/profile.yml`
3. `portals.yml`
4. `data/applications.md`

If they are missing:
- create `cv.md` from the candidate’s resume / pasted history
- copy `config/profile.example.yml` → `config/profile.yml`
- copy `templates/portals.example.yml` → `portals.yml`
- create `data/applications.md` with the standard table

```markdown
# Applications Tracker

| # | Date | Company | Role | Score | Status | PDF | Report | Notes |
|---|------|---------|------|-------|--------|-----|--------|-------|
```

## Operating modes

Use natural language prompts instead of Claude slash commands.

| User intent | Expected workflow |
|-------------|-------------------|
| Paste JD or URL | Full auto-pipeline: evaluate + report + PDF + tracker |
| Ask to evaluate offer | `modes/oferta.md` |
| Ask to generate CV/PDF | `modes/pdf.md` |
| Ask to scan for jobs | `modes/scan.md` |
| Ask to process pipeline inbox | `modes/pipeline.md` |
| Ask for batch evaluation | `modes/batch.md` + `batch/batch-runner.sh` |
| Ask for tracker status | `modes/tracker.md` |
| Ask for application help | `modes/apply.md` |

## Personalization rules

- Change archetypes in `modes/_shared.md` when target roles change.
- Change scanner targets in `portals.yml`.
- Change candidate identity only in `config/profile.yml` and `cv.md`.
- Change the PDF design only in `templates/cv-template.html`.
- Do not invent metrics. Read them from `cv.md` and `article-digest.md`.

## Batch mode

Batch processing is driven by `batch/batch-runner.sh` and uses `codex exec` workers.

- Input: `batch/batch-input.tsv`
- Progress state: `batch/batch-state.tsv`
- Logs: `batch/logs/`
- Tracker additions: `batch/tracker-additions/`

Each worker should:
1. read the JD
2. write the report
3. generate the PDF
4. write the tracker TSV addition
5. return a final JSON summary for the orchestrator log

## Repo migration notes

This fork is in transition from Claude-specific to Codex/OpenClaw-first.

Priority migration targets:
1. remove Claude-only assumptions
2. normalize prompts/specs into one language
3. tailor archetypes and scoring to the candidate
4. keep the strong file-based workflow and PDF/tracker utilities
