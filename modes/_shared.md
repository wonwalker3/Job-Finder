# Shared Context — Job-Finder

This file defines the shared logic for evaluation, tailoring, and application-prep flows.

## Sources of truth

Always read these before evaluating any role:

| File | Path | When |
|------|------|------|
| Resume source | `cv.md` | Always |
| Proof points | `article-digest.md` (if present) | Always when available |
| Candidate profile | `config/profile.yml` | Always |

Rules:
- Never invent metrics.
- Prefer `article-digest.md` for detailed metrics if it conflicts with older summary text in `cv.md`.
- Do not mutate the candidate’s factual background to fit a role.

---

## North Star role families

This fork is being adapted for a practical, flexible search rather than one narrow AI-founder narrative.

Evaluate opportunities across these role families unless the candidate profile says otherwise:

| Role family | What the company is buying |
|-------------|-----------------------------|
| **Applied AI / Automation Builder** | Someone who can turn AI/automation ideas into working systems and real workflows |
| **Technical Product / AI Product** | Someone who can translate business needs into product decisions, tools, and shipped outcomes |
| **Solutions / Implementation / Customer-Facing Technical** | Someone who can bridge clients, systems, demos, integrations, and delivery |
| **Revenue / Operations Systems Builder** | Someone who can improve GTM, RevOps, internal tools, process automation, and reporting |
| **Business Operator with Technical Leverage** | Someone who can own outcomes, move fast, and use systems/AI/tools to increase throughput |
| **Adjacent Stretch Role** | A role slightly outside the core background but still sellable with a credible narrative |

The candidate does not need a single rigid title target. The system should optimize for:
- believable fit
- compensation sanity
- strong story alignment
- actual willingness to do the work

---

## Adaptive framing by role family

| If the role is... | Emphasize... |
|-------------------|--------------|
| Applied AI / Automation Builder | shipping, workflows, operational leverage, experimentation, tool-building |
| Technical Product / AI Product | prioritization, customer insight, business translation, product judgment |
| Solutions / Implementation | communication, translation, demos, implementation speed, trust-building |
| Revenue / Ops Systems | systems thinking, process cleanup, automation ROI, visibility, execution |
| Business Operator | ownership, judgment, initiative, moving things forward without bureaucracy |
| Adjacent Stretch | transferable wins, adjacent credibility, fast learning, realistic gap handling |

---

## Candidate story framing

Use the candidate’s profile narrative from `config/profile.yml`.

Default frame for this fork:
- practical builder
- business-minded
- technical enough to ship and automate
- not a buzzword tourist
- someone who can create leverage, not just produce slides

The system should make the candidate sound:
- credible
- direct
- useful
- high-agency

Not like:
- a generic corporate resume generator
- a fake founder myth machine
- someone inflating into roles they clearly cannot do

---

## Scoring priorities

Use a 1–5 score, but the score must be grounded in reality.

### Core dimensions

| Dimension | What to check |
|-----------|----------------|
| Core fit | Does the background actually line up with the real job? |
| Story fit | Can the candidate explain why this role makes sense? |
| Compensation fit | Is the comp likely in range? |
| Work-style fit | Remote/hybrid/travel expectations realistic? |
| Credibility of proof | Are there concrete examples to back up the pitch? |
| Risk level | Are there fatal gaps or just normal stretch areas? |

### Score guidance

- **4.5–5.0** → strong apply
- **4.0–4.4** → good apply
- **3.2–3.9** → maybe / selective apply
- **below 3.2** → usually skip

A score should not just flatter the candidate. It should help decide where effort belongs.

---

## Resume/PDF tailoring rules

When generating tailored resume output:
- use truthful keyword alignment only
- reorder and reframe existing experience; do not fabricate
- prioritize what would matter in a 6-second scan
- pull real proof from `cv.md` and `article-digest.md`
- keep language clean, direct, and recruiter-readable

If the job is weak or the fit is poor, say so instead of forcing a tailored PDF unless explicitly requested.

---

## Application-help rules

This repo is not intended for blind autopilot submission.

Allowed:
- evaluate roles
- draft answers
- fill fields with review
- prepare a tailored resume PDF
- help navigate forms

Not allowed by default:
- submitting applications without review
- inventing answers
- overstating qualifications

---

## Tracker rules

Always keep the tracker clean.

Rules:
1. New entries should be written through TSV additions when using batch/pipeline flows.
2. Existing status/notes updates may edit the tracker directly when appropriate.
3. Every report should include `**URL:**` in the header.
4. Use canonical states from `templates/states.yml`.

---

## Style rules for generated content

Generated job-search content should sound:
- clear
- sharp
- grounded
- concise

Avoid:
- corporate sludge
- fake passion language
- over-explaining
- unsupported claims
- jargon for its own sake

The candidate should sound like someone worth hiring, not like a resume optimization robot.
