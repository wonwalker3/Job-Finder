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
- Prefer `article-digest.md` for detailed positioning if it conflicts with older summary text in `cv.md`.
- Do not mutate the candidate’s factual background to fit a role.

---

## What the first evaluations taught us

Current calibration from real evaluated roles:

- **Luxury Presence AE** → 4.6/5
- **HubSpot SMB AE** → 3.8/5
- **Mento GTM Engineer** → 2.7/5

Interpretation:
- strongest in customer-facing commercial roles with strong domain fit and practical technical leverage
- still plausible in some mainstream SaaS AE roles, but with more friction
- weak fit for roles that primarily want a true GTM systems / RevOps / growth engineering builder

This should influence scoring and targeting everywhere else.

---

## North Star role families

Evaluate opportunities across these role families unless the candidate profile says otherwise:

| Role family | Priority | What the company is buying |
|-------------|----------|-----------------------------|
| **AI-forward commercial role** | High | Seller/operator who can talk to customers, drive revenue, and use AI/tooling intelligently |
| **Solutions / implementation / customer-facing technical** | High | Someone who can bridge customers, systems, demos, onboarding, and delivery |
| **Proptech / real-estate-adjacent technology role** | High | Domain-fluent closer/operator who already understands agents, brokerages, referral businesses, or real-estate customer motion |
| **Technical product / AI product (light-to-moderate technical depth)** | Medium | Someone who can translate business/customer needs into systems, workflows, or product outcomes |
| **Revenue / operations systems role** | Medium-low | Only when the role is closer to operator judgment and workflow ownership than true RevOps engineering |
| **Pure GTM engineer / growth engineering / RevOps builder** | Low | Usually a miss unless the JD is unusually forgiving and not actually asking for real systems-depth |

---

## Strong-fit signals

Favor roles with these traits:

- customer-facing and commercially accountable
- consultative selling or solution discovery
- multi-stakeholder sales motion
- CRM / pipeline discipline matters
- practical operator judgment matters
- industry/domain knowledge helps
- AI or modern tooling fluency is a plus, not the whole job
- relationship building and business trust matter

These are the kinds of roles where the candidate's story becomes stronger, not weaker.

---

## Weak-fit signals

Penalize roles with these traits:

- explicit requirement for 3–5+ years in GTM Ops / RevOps / Growth Engineering
- direct demand for SQL, APIs, webhooks, data pipelines, or heavy systems integration depth
- role is really an internal systems-builder position wearing a GTM label
- role assumes prior production ownership of enrichment pipelines, routing logic, or revenue-engine architecture
- role is closer to software engineer / solutions architect / deep technical builder than commercial operator

The candidate may be adjacent or interested. Adjacent is not the same as competitive.

---

## Adaptive framing by role family

| If the role is... | Emphasize... |
|-------------------|--------------|
| AI-forward commercial role | consultative selling, customer judgment, modern tooling, pipeline discipline, practical AI leverage |
| Solutions / implementation | communication, translation, systems thinking, onboarding, customer trust, fast learning |
| Proptech / real-estate-adjacent | domain credibility, agent/broker understanding, referral networks, business-owner empathy |
| Technical product / AI product | prioritization, workflow design, user understanding, systems judgment, cross-functional thinking |
| Revenue / ops systems | process cleanup, operator mindset, automation instincts, CRM discipline — but only if the role is not too technical |
| Pure GTM engineer | usually a warning case; do not force the fit |

---

## Candidate story framing

Use the candidate’s profile narrative from `config/profile.yml`.

Default frame for this fork:
- top-producing sales operator
- business owner with real accountability
- practical builder who uses systems, automation, and AI for leverage
- strong customer judgment
- not an engineer, not pretending to be one

The candidate should sound:
- credible
- direct
- useful
- modern
- high-agency

Not like:
- a fake SaaS veteran
- a fake engineer
- a generic corporate resume generator
- someone inflating into roles they clearly cannot do

---

## Scoring priorities

Use a 1–5 score grounded in reality.

### Core dimensions

| Dimension | What to check |
|-----------|----------------|
| Core fit | Does the background line up with the actual job? |
| Story fit | Can the candidate explain why this move makes sense? |
| Commercial fit | Does the role value selling, customer judgment, and pipeline ownership? |
| Tooling fit | Is modern CRM / AI / workflow fluency enough, or does the role demand deeper systems skill? |
| Domain fit | Does industry/customer familiarity help materially? |
| Risk level | Are the gaps manageable, or does the JD want a fundamentally different person? |

### Scoring guidance

- **4.5–5.0** → strong apply
- **4.0–4.4** → good apply
- **3.2–3.9** → selective / maybe
- **below 3.2** → usually skip

Important:
- Do not award a high score just because the role mentions AI.
- Do not award a high score just because the candidate likes automation.
- A commercial operator role with AI/tooling upside is different from a real GTM engineering role.

---

## Resume/PDF tailoring rules

When generating tailored resume output:
- use truthful keyword alignment only
- reorder and reframe existing experience; do not fabricate
- prioritize what matters in a 6-second scan
- translate domain-specific sales experience into broadly legible business outcomes when needed
- pull real proof from `cv.md` and `article-digest.md`

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
- bluffing technical depth to force a role fit

---

## Tracker rules

Always keep the tracker clean.

Rules:
1. New entries should be written through TSV additions when using batch/pipeline flows.
2. Existing status/notes updates may edit the tracker directly when appropriate.
3. Every report should include `**URL:**` in the header.
4. Use canonical states from `templates/states.yml`.
5. When a role scores below 3.2, note clearly why so future review does not waste time repeating the same mistake.

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