# Job-Finder

AI-powered job search pipeline adapted from `santifer/career-ops` for a **Codex/OpenClaw-first** workflow.

This repo is for running a disciplined, high-signal job search:
- evaluate jobs
- generate tailored resume PDFs
- scan job portals
- draft application answers
- track applications cleanly

Not for blind mass-apply nonsense.

---

## What this repo is

Job-Finder is a file-based job-search operating system.

You feed it a job description or job URL, and it can:
- score whether the role is worth your time
- generate a markdown report
- generate a tailored PDF resume
- add the result to your tracker
- help with application prep

The original repo was built around Claude Code. This fork is being converted toward:
- **Codex for agent work**
- **OpenClaw for orchestration/browser help**
- the same strong file-based workflow underneath

---

## Current status

This fork is in active conversion.

What is already strong:
- PDF generation via Playwright/Chromium
- tracker merge / dedup / verify utilities
- report structure
- batch/state model
- dashboard foundation

What is being changed:
- Claude-specific instructions and execution paths
- default archetypes and scoring assumptions
- docs and workflow language
- candidate profile defaults

---

## Core workflow

### 1. Evaluate
Input:
- pasted job description
- or job URL

Output:
- fit score
- strengths / gaps
- tailored recommendations
- report in `reports/`

### 2. Tailor
Generate:
- role-specific resume PDF
- application answer drafts
- key talking points

### 3. Track
Write outcomes to:
- `data/applications.md`
- `batch/tracker-additions/`

### 4. Scan
Search:
- job portals
- company careers pages
- configured target companies

---

## Repo structure

```text
Job-Finder/
├── AGENTS.md                    # Codex/OpenClaw operator guidance
├── CLAUDE.md                    # Legacy upstream guidance (to be retired/replaced)
├── cv.md                        # Candidate resume source of truth
├── article-digest.md            # Candidate proof points / metrics (optional)
├── config/
│   └── profile.example.yml      # Candidate profile template
├── modes/
│   ├── _shared.md               # Shared evaluation logic
│   ├── oferta.md                # Single-job evaluation mode
│   ├── pdf.md                   # PDF generation mode
│   ├── pipeline.md              # Pending URL inbox flow
│   └── ...
├── templates/
│   ├── cv-template.html         # Resume HTML template
│   ├── portals.example.yml      # Scanner config template
│   └── states.yml               # Canonical tracker states
├── batch/
│   ├── batch-prompt.md          # Worker prompt template
│   └── batch-runner.sh          # Batch orchestrator
├── data/                        # Tracker and pipeline files
├── reports/                     # Evaluation reports
├── output/                      # Generated PDFs
├── dashboard/                   # Terminal dashboard
└── docs/                        # Setup/customization/architecture docs
```

---

## Setup

```bash
git clone https://github.com/wonwalker3/Job-Finder.git
cd Job-Finder
npm install
npx playwright install chromium
```

Create your working files:

```bash
cp config/profile.example.yml config/profile.yml
cp templates/portals.example.yml portals.yml
```

Then add:
- `cv.md`
- optionally `article-digest.md`
- `data/applications.md` if it does not exist yet

Suggested tracker starter:

```markdown
# Applications Tracker

| # | Date | Company | Role | Score | Status | PDF | Report | Notes |
|---|------|---------|------|-------|--------|-----|--------|-------|
```

---

## Runtime notes

### Batch mode
The batch runner now targets **Codex** workers instead of `claude -p`.

### PDF generation
PDF generation uses:
- Playwright
- Chromium
- HTML template rendering

### Browser-heavy flows
Application help and some job extraction flows are best handled through browser automation/orchestration rather than static fetch alone.

---

## Near-term roadmap

1. finish Codex/OpenClaw baseline conversion
2. tailor archetypes/scoring to the actual candidate
3. clean up legacy Claude-only docs
4. simplify the golden path:
   - input job
   - evaluate
   - generate PDF
   - update tracker
5. layer in scanner and apply-copilot improvements

---

## License

MIT
