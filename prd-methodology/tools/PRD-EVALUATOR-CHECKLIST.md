# PRD Evaluator Checklist — 26 Items

**Use this rubric to evaluate your PRD before handing off to engineering. Rate each item as Pass / Blocker / Improvement.**

---

## How to Use This Checklist

1. **Read your full PRD first.** Scan entire document before scoring.
2. **Score each item:** Pass (clearly met) / Blocker (critical gap) / Improvement (weak but not blocking)
3. **Count results:** X passing, Y blockers, Z improvements
4. **Blockers = no shipping.** If you have blockers, iterate until 0.
5. **Improvements = prioritize.** Fix improvements if time permits, but don't block ship for these.

**Key Distinction:**
- **Blocker:** Gaps in core thinking that prevent shipping (no success metric defined, no user flow, no MOAT)
- **Improvement:** Weak points that should be strengthened but don't block progress (metric lacks baseline, roadmap lacks durations, risk mitigation is generic)

---

## Scoring Template

| Section | Pass | Blocker | Improvement | Comments |
|---|---|---|---|---|
| 1. Problem Definition (8 items) | _ / 8 | _ | _ | |
| 1. Core Metrics (4 items) | _ / 4 | _ | _ | |
| 2. Solution Definition (4 items) | _ / 4 | _ | _ | |
| 3. Prioritization (5 items) | _ / 5 | _ | _ | |
| 4. Roadmap (5 items) | _ / 5 | _ | _ | |
| 5. Implementation (2 items) | _ / 2 | _ | _ | |
| 6. Evaluation (7 items) | _ / 7 | _ | _ | |
| 7. Data & Prompting (5 items) | _ / 5 | _ | _ | |
| 8. Responsible AI (4 items) | _ / 4 | _ | _ | |
| 9. Pricing & Cost (7 items) | _ / 7 | _ | _ | |
| **TOTAL** | **_ / 52** | **_** | **_** | |

---

## Section 1: Problem Definition & Core Metrics (12 items)

### Problem Definition (8 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 1.1 | **Problem & JTBD** | PRD clearly states what the user is trying to accomplish and what's currently broken. "Users want better tools" doesn't pass; "Lease admins miss 90-day renewal notices costing $40K per miss" passes. | ⬜ |
| 1.2 | **Personas Defined** | At least one persona with specific role, industry, needs. "Enterprise users" alone doesn't pass; "Sarah, 45, Lease Administrator at mid-market CRE firm" passes. | ⬜ |
| 1.3 | **Problem Validated** | Problem is grounded in research data: interviews, market surveys, support tickets. "We believe users want this" doesn't pass; "8 interviews with admins confirm 3–5 hrs/week on manual tracking" passes. | ⬜ |
| 1.4 | **Impact Quantified** | Explains urgency, frequency, or cost. "It's a big problem" doesn't pass; "$40K cost per miss, happens 1–2× per year for 30% of customers" passes. | ⬜ |
| 1.5 | **Defensible MOAT** | Names what makes this hard to copy: data advantage, domain expertise, regulatory moat, workflow lock-in. "We use AI" or "better UX" doesn't pass; "Jurisdiction expertise + customer data flywheel" passes. | ⬜ |
| 1.6 | **Agentic AI Justified** | Explains why rules/logic alone can't solve this. Addresses variability, unstructured inputs, context, judgment calls. For non-AI products, mark N/A. | ⬜ |
| 1.7 | **Unstructured Data Typed** | Names unstructured inputs (PDFs, emails, images, voice) and explains why pattern-matching fails. For non-AI products, mark N/A. | ⬜ |
| 1.8 | **Differentiation from ChatGPT** | Explicitly addresses why existing tools (ChatGPT, Claude, Copilot) don't solve this. Workflow fit, domain specialization, or integration depth. For non-AI products, mark N/A. | ⬜ |

### Core Metrics (4 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 1.9 | **North Star Defined** | One metric explicitly named as primary success signal. Multiple metrics without a declared winner doesn't pass. | ⬜ |
| 1.10 | **Primary Metrics (1–2)** | Includes quantified outcomes: accuracy, time saved, task completion rate. "We will track satisfaction" without a method doesn't pass. | ⬜ |
| 1.11 | **Secondary Metrics** | Covers adoption, retention, cost reduction, NPS. At least one included. | ⬜ |
| 1.12 | **Metrics Measurable** | Each metric has unit, baseline, and plausible measurement approach. "We will track satisfaction" without method doesn't pass; "NPS monthly, measured via in-app survey" passes. | ⬜ |

---

## Section 2: Solution Definition (4 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 2.1 | **User Flow Included** | Visual diagram or numbered steps showing input → processing → output. Includes what user does vs. what system does. Prose alone doesn't pass. | ⬜ |
| 2.2 | **AI Drawbacks Addressed** | At least 2 risks acknowledged with mitigations: hallucination, explainability, bias, latency. Human-in-the-loop, confidence scores, audit trails, disclaimers. | ⬜ |
| 2.3 | **User Stories in Format** | Uses "As a [persona], I want [action], so that [outcome]" format for key features. Plain feature lists don't pass. | ⬜ |
| 2.4 | **Agent Capabilities Clear** | States what agent does autonomously, what requires human approval, how it handles errors/edge cases. | ⬜ |

---

## Section 3: Prioritization (5 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 3.1 | **Workflow Components** | Names 2–3 distinct pipeline stages (ingestion, extraction, analysis, summarization). "AI processes the data" doesn't pass. | ⬜ |
| 3.2 | **Risk per Component** | Each component has risk identified with severity/mitigation. Generic "AI risks" not tied to components don't pass. | ⬜ |
| 3.3 | **ML Feasibility Addressed** | ML necessity, data availability, accuracy expectations, explainability per component. | ⬜ |
| 3.4 | **Features Prioritized** | P0/P1/P2 labels with rationale. Unprioritized lists don't pass. | ⬜ |
| 3.5 | **MVP Scoped** | Clear boundary between MVP and Phase 2 with stated reason. Lists including everything don't pass. | ⬜ |

---

## Section 4: Roadmap (5 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 4.1 | **Phases Listed** | At least two phases: MVP and Launch (or MVP, MVP1, Launch). | ⬜ |
| 4.2 | **Durations Defined** | Each phase has features + time estimate (e.g., "Week 1–4, MVP: Core extraction"). | ⬜ |
| 4.3 | **Roadmap Linked to Risks** | Roadmap phases traceable to prioritized stories and risk levels. | ⬜ |
| 4.4 | **Dependencies Named** | At least one cross-functional dependency (data sourcing, legal, design, infra, third-party). | ⬜ |
| 4.5 | **Phasing Realistic** | MVP meaningfully smaller than launch. Identical features fail. | ⬜ |

---

## Section 5: Implementation (2 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 5.1 | **Model Selection Criteria** | Lists ≥2 specific criteria (context window, latency, cost, accuracy, open vs. closed). "We chose GPT-4" without criteria doesn't pass. | ⬜ |
| 5.2 | **Alternatives Considered** | At least one alternative named with reason for not choosing it. Single model with no comparison doesn't pass. | ⬜ |

---

## Section 6: Evaluation Plan (7 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 6.1 | **AI Performance Over Time** | Concrete evaluation approach: benchmark dataset, eval method, refresh cadence. "We will monitor" without specifics doesn't pass. | ⬜ |
| 6.2 | **Ground Truth Identified** | Specific dataset, benchmark, or labeling process. "We will test accuracy" without stating against what doesn't pass. | ⬜ |
| 6.3 | **Accuracy Targets** | Quantified thresholds: ">90% F1", ">80% user satisfaction". Qualitative statements ("high accuracy") don't pass. | ⬜ |
| 6.4 | **Eval Spreadsheet Linked** | Link to evaluation spreadsheet OR explicit plan with column headers. No mention doesn't pass. | ⬜ |
| 6.5 | **Go/No-Go Criteria** | Measurable criteria at each launch stage. "We will launch when ready" doesn't pass. | ⬜ |
| 6.6 | **A/B Testing Plan** | At least one experiment described (holdout, A/B test, measurement rollout). "We will experiment" alone doesn't pass. | ⬜ |
| 6.7 | **Post-Launch Monitoring** | Cadence, metrics, alerting threshold, drift detection. "We will monitor performance" without method doesn't pass. | ⬜ |

---

## Section 7: Data Requirements & Prompt Strategy (5 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 7.1 | **Data Strategy** | Names sources, formats, pipelines. "We have the data" without specifics doesn't pass. | ⬜ |
| 7.2 | **Data Quality & Compliance** | Mentions ≥1 of: quality checks, availability risk, compliance (GDPR, HIPAA, residency). | ⬜ |
| 7.3 | **Prompting Techniques** | Names ≥1 technique with rationale (few-shot, CoT, conditional). "We use prompts" doesn't pass. | ⬜ |
| 7.4 | **Output Formats** | ≥1 task has defined format or constraint (JSON schema, word limit, list). | ⬜ |
| 7.5 | **Prompt Improvement Plan** | Process for improving based on feedback: versioned library, A/B testing, error logging, correction threshold. | ⬜ |

---

## Section 8: Responsible AI (4 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 8.1 | **4 Pillars Addressed** | All four covered: Accountability, Transparency, Fairness, Reliability. PRDs covering 1–2 pillars don't pass. | ⬜ |
| 8.2 | **Human-in-Loop Planned** | Names ≥1 scenario requiring human review + fallback if AI fails. "Humans will review" without specifics doesn't pass. | ⬜ |
| 8.3 | **Sensitive Use Cases** | Names ≥1 high-stakes scenario specific to product with mitigation. "We're aware of AI risks" doesn't pass. | ⬜ |
| 8.4 | **Bias, Hallucination, Safe Failures** | All 3 must be addressed. Missing any one fails this item. | ⬜ |

---

## Section 9: Pricing & Cost Structure (7 items)

| # | Criterion | Pass Condition | Your Rating |
|---|-----------|---|---|
| 9.1 | **Cost/Accuracy Tradeoffs** | ≥1 infrastructure choice explained with tradeoff. Listing choices without tradeoffs doesn't pass. | ⬜ |
| 9.2 | **Dev Costs Broken Down** | Separates infrastructure and manpower with rough figures. Single total doesn't pass. | ⬜ |
| 9.3 | **Operational Costs** | ≥2 recurring items: LLM API, hosting, monitoring, maintenance, etc. | ⬜ |
| 9.4 | **Market Size** | Both TAM and SAM with source/rationale. Numbers without basis don't pass. | ⬜ |
| 9.5 | **Revenue Scenarios** | ≥2 scenarios (conservative, target) with customer count and ARR. Single scenario doesn't pass. | ⬜ |
| 9.6 | **Pricing Model Selected** | One model chosen as primary with explicit reason. Listing all models without selecting fails. | ⬜ |
| 9.7 | **Directional Pricing** | ≥1 price point named. "We will price competitively" isn't directional. | ⬜ |

---

## Score Summary

**Total Passing:** __ / 52
**Total Blockers:** __
**Total Improvements:** __

**Blocker Count Interpretation:**
- 0 blockers → ✅ Ready to ship
- 1–2 blockers → ⚠️ Fix and re-evaluate
- 3–5 blockers → 🛑 Major revision needed
- 5+ blockers → 🛑 Consider restarting PRD

---

## Next Steps

**If 0 blockers:** Ship to engineering with improvements logged for Phase 2.

**If 1–3 blockers:** Iterate PRD section-by-section. Re-run checklist daily until 0 blockers.

**If >3 blockers:** Schedule a PRD review session with co-authors. Rewrite affected sections.

---

**Version:** 1.0 | **Last Updated:** [Date]
