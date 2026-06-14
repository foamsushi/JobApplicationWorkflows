---
description: Application Step 1
---

Agent Configuration

Role: Career Architect
Tools: Browser, Editor
Inputs:

masterCV/

job_url

Phase 1A — Job Description Ingestion
Browser Action

Scrape full job description from job_url

Preserve original wording (no summarization yet)

Phase 1B — Dual-Axis Analysis (NEW)
Reasoning Tasks

The agent performs two parallel analyses:

AXIS 1 — Capability Match (Traditional)

Identify:

Hard skills (chemistry, software, methods)

Domain experience

Compliance / standards

Language requirements

AXIS 2 — Role Gravity & Cognitive Fit (NEW)
TS&D Gravity Signals (Flag)

Examples:

troubleshooting

customer complaints

localization

support

interface between

operational execution

rapid response

day-to-day support

R&D Leverage Signals (Positive)

Examples:

methodology development

test design

evaluation strategy

early-stage development

innovation pipeline

qualification framework

risk reduction

root cause prevention

Artifact: gap_analysis_report.md
Required Structure

## Capability Match Summary

- Estimated Match Score: XX%

## Missing or Underrepresented Keywords

| Keyword | Present in Experience? | Action |
| ------- | ---------------------- | ------ |

## Skill Gaps (Validated Only)

| Gap | Real Gap or CV Omission? | Action |

## Role Gravity Assessment

| Signal Type  | Evidence from JD                     | Weight |
| ------------ | ------------------------------------ | ------ |
| TS&D Gravity | “…handling customer complaints…”     | Medium |
| R&D Leverage | “…design new testing methodologies…” | High   |

## Risk Notes

- TS&D Overfitting Risk: Low / Medium / High
- Mitigation Required in Cover Letter: Yes / No

Agent Configuration

Role: Role Fit Gatekeeper
Tools: Reasoning
Inputs:

Scraped JD

Candidate Archetype (persistent context)

Phase 1C.1 — Job Signal Extraction

The agent extracts and counts signals in five dimensions.

1. Value Creation Mode
   Signal Examples
   Upstream / Strategic concept development, test design, methodology, early-stage, innovation
   Midstream / Translational scale-up, qualification, industrialization
   Downstream / Reactive troubleshooting, complaints, support, localization
2. Autonomy & Framing Latitude

Positive signals:

“Define”, “Design”, “Develop new”

“Own”, “Lead”, “Establish”

Negative signals:

“Execute”, “Support”, “Assist”

“Follow procedures”

“Day-to-day”

3. Interruption Density

High-risk phrases:

“Fast-paced”

“Dynamic environment”

“Multiple stakeholders”

“Interface between”

“Customer-facing”

4. Success Metrics (Implicit)

Look for:

Prevention: reduced rework, improved robustness

Throughput: responsiveness, turnaround time, ticket closure

5. Identity Framing

How the role defines you:

Expert / Owner / Designer

vs

Support / Interface / Resource

Phase 1C.2 — Scoring & Classification
Weighted Scoring Model (Example)
Dimension Weight
Value Creation Mode 30%
Autonomy & Framing 25%
Interruption Density 20%
Success Metrics 15%
Identity Framing 10%

Score each dimension from –2 to +2.

Classification Output
FINAL JOB CLASS
Class Meaning Action
TARGET Structurally aligned with candidate strengths Proceed to full workflow
CONDITIONAL Technically strong, structurally risky Proceed only if limited time
AVOID High TS&D gravity / low autonomy Stop processing
Artifact: role_fit_decision.md

## Role Classification: TARGET / CONDITIONAL / AVOID

### Summary Rationale

- Value Creation Mode:
- Autonomy Level:
- TS&D Gravity:
- Interruption Risk:

### Evidence from JD

- Quote 1
- Quote 2

### Recommendation

- Proceed / Proceed with caution / Do not apply

JOB TYPES TO TARGET (Explicit Encoding)

Agent should boost jobs with titles or descriptions like:

Senior R&D Scientist

Materials / Polymer Scientist

Principal Scientist

Technical Expert (R&D)

Advanced Development Engineer

Method Development Scientist

Formulation Scientist (early-stage)

Keywords:

“Define evaluation methods”

“Develop new test protocols”

“Early-stage development”

“Risk reduction”

“Innovation pipeline”

JOB TYPES TO AVOID (Explicit Encoding)

Agent should hard-flag roles like:

TS&D Specialist (pure)

Application Engineer (customer-facing)

Product Support Scientist

Field Technical Service

Manufacturing Support Engineer

Quality / Complaints Engineer

Process Engineer (production-owned, no R&D)

Keywords:

“Primary interface to customers”

“Rapid response to customer issues”

“Day-to-day support”

“Execution-focused”

“High-volume request handling”

JOB TYPES TO CONDITIONALLY CONSIDER

These are acceptable only if autonomy signals are strong:

R&D + TS&D hybrid roles

Scale-up / Industrialization Scientist

Localization support roles

Mitigation required in later workflows:

Boundary-aware cover letter

Methodology-forward CV framing

Interview probes on autonomy

Hard Rule:
The agent must not invent skills to close gaps.
