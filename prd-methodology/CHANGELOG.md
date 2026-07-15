# Changelog

All notable changes to this project are documented here.

## [0.1.0] — 2026-07-13

### Initial Release

**Added:**
- `HOW-I-BUILD-PRDS.md` — Core methodology guide covering 3-stage product operating system
  - Stage 1: Market Hypothesis
  - Stage 2: Validation  
  - Stage 3: Specification
  - Decision frameworks and go/no-go criteria at each stage
  - Common mistakes and how to avoid them
  - Adaptation guidance for different product types

- **Case Study: Compliance Lease Tool**
  - `case-studies/compliance-lease-tool/README.md` — Overview showing how methodology applies to commercial real estate SaaS
  - `case-studies/compliance-lease-tool/hypothesis.md` — Market sizing (TAM $1.0B–$1.2B, SAM $150M–$200M, SOM $10M–$25M), competitive analysis, 5 timing signals
  - `case-studies/compliance-lease-tool/validation/market-research-summary.md` — Detailed market analysis, SAM sizing for US mid-market, competitive landscape (5 archetypes), market trends
  - `case-studies/compliance-lease-tool/validation/user-research-summary.md` — 3 validated persona interviews (Sarah, Marcus, Jennifer) with direct quotes and cross-cutting themes
  - `case-studies/compliance-lease-tool/assumptions-ranked.md` — 8 critical assumptions ranked by risk (Tier 1/2/3) with evidence and validation approach
  - `case-studies/compliance-lease-tool/go-no-go-framework.md` — 7 major decision gates with go/no-go triggers and pivot strategies
  - `case-studies/compliance-lease-tool/validation-plan.md` — Concrete Week 1–4 de-risking plan with week-by-week activities and decision logic
  - `case-studies/compliance-lease-tool/lessons-learned.md` — 10 meta-lessons from PRD process

- **Reusable Templates**
  - `templates/PRD-TEMPLATE.md` — 14-section blank PRD template ready to fill in
  - `templates/MARKET-SIZING-TEMPLATE.md` — TAM/SAM/SOM calculation template with top-down and bottom-up methods
  - `templates/USER-RESEARCH-GUIDE.md` — 45-minute interview script, JTBD extraction method, WTP documentation, synthesis approach

- **Evaluation Tools**
  - `tools/PRD-EVALUATOR-CHECKLIST.md` — 26-item rubric across 7 sections identifying blockers vs. improvements
  - `tools/RESPONSIBLE-AI-ASSESSMENT.md` — 4-pillar framework (Accountability, Transparency, Fairness, Reliability) with pre-launch checklist

- **Repository Setup**
  - `README.md` — Landing page with quick start guide and repository overview
  - `CHANGELOG.md` — This file
  - `.gitignore` — Standard ignores for development artifacts

### Key Principles Documented

- Move fast on validation, not building (target: 2–3 weeks research before PRD)
- Evaluation is a thinking tool, not a gate
- Rank assumptions by risk (Tier 1 = kill-product, Tier 2 = pivot, Tier 3 = feature-level)
- Defensible differentiation must pass the 6-month competitor copy test
- Never use single market sizing model — triangulate
- User research requires depth (5–8 interviews per persona), not breadth (surveys)
- Willingness-to-Pay is separate from excitement; test independently
- Tier 1 assumptions must be tested before engineering commitment

### Why This Version

This initial release establishes the complete product operating system for de-risking product decisions. Use this as:
- A methodology guide for your own products
- A case study showing hypothesis-testing rigor
- Templates and tools for building PRDs
- Evidence of product thinking for recruiting purposes

---

## Version Numbering

This project uses [Semantic Versioning](https://semver.org/).

- **Major** — Structural changes to methodology or new stages added
- **Minor** — New case studies or templates added
- **Patch** — Fixes, clarifications, or improvements to existing content

---

**Last Updated:** July 13, 2026
