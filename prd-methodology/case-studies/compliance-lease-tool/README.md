# Case Study: Compliance Lease Tool

**A theoretical commercial real estate SaaS showing how the product operating system applies to a concept-stage product**

## Overview

This case study walks through a concept-stage product — the **Compliance Lease Tool** — using the 3-stage product operating system. The product does not yet exist. This is what the validation and PRD process looks like before engineering commitment.

**The problem:** Lease administrators at mid-market companies spend 3–5 hours/week tracking lease renewals, amendments, and jurisdiction-specific compliance (ASC 842, ESG disclosures, local regulations). They use spreadsheets. They miss 90-day renewal notices and pay $40K penalties. Current solutions (CoStar, Visual Lease) are built for enterprise (50,000+ seats) and overkill for mid-market (50–500 leases).

**The hypothesis:** A compliance-first, mid-market-focused lease tool with proactive alerts and jurisdiction tracking can own the $150M SAM in the US mid-market and capture $10M–$25M in Year 3 revenue.

## Quick Facts

| Metric | Value | Source |
|---|---|---|
| **TAM** | $1.0B–$1.2B | IDC analysis + bottom-up customer × spend |
| **SAM** | $150M–$200M | US mid-market (50–500 leases, $250–$500/month WTP) |
| **SOM** | $10M–$25M | 3-year projection (200–300 customers Y1 → 5,500–6,700 Y3) |
| **Pricing** | $300/month | Willingness-to-pay validation (n=8 interviews, $250–$400 range) |
| **Primary User** | Lease Administrator | Sarah (45 years old, $60K salary, 3–5 hrs/week on renewals) |
| **Competitive Gap** | Compliance-first, mid-market | Incumbents focus on enterprise; DIY users are at other extreme |
| **Timing Signal** | ASC 842 regulatory adoption | 62% of new leases require compliance tracking (2024 survey) |

## How This Case Study Works

### Stage 1: Market Hypothesis — [hypothesis.md](hypothesis.md)

Documents:
- **Market sizing:** TAM ($1.0B–$1.2B), SAM ($150M–$200M), SOM ($10M–$25M)
- **Competitive landscape:** 5 archetypes (Enterprise, General, Specialist, Accounting, DIY) with analysis of why incumbents won't move fast into mid-market
- **Timing signals:** 5 external drivers
  1. ASC 842 regulatory pressure (created new compliance burden in 2022)
  2. ESG compliance surge (62% of new leases now require ESG tracking)
  3. AI adoption jump (20%→58% in last 18 months — opportunity to automate)
  4. Incumbent consolidation (CoStar acquired Visual Lease + Insight acquired Lease Accelerator — signals market is consolidating, leaving mid-market underserved)
  5. Competitive gap (no one owns "compliance-first, mid-market" positioning)
- **Go/No-Go decision:** Market hypothesis passes go criteria; proceed to validation

### Stage 2: Validation — [validation/](validation/)

Documents:
- **Market Research Summary** — [market-research-summary.md](validation/market-research-summary.md)
  - TAM triangulation (analyst reports + bottom-up model)
  - SAM sizing for US mid-market
  - SOM with 3-year penetration projections
  - Competitive landscape detail (5 archetypes + why-can't-they-move analysis)
  - Market trends (regulatory, ESG, AI, consolidation)
  - Pricing benchmarks

- **User Research Summary** — [user-research-summary.md](validation/user-research-summary.md)
  - 3 validated personas with direct quotes:
    - **Sarah** (Lease Admin): "Last year I missed a 90-day renewal notice. Cost us $40K."
    - **Marcus** (Portfolio Manager): "Friday spreadsheet is 40 rows. Takes 2–3 hours to triage."
    - **Jennifer** (Legal Officer): "I maintain 3 separate spreadsheets for 3 jurisdictions."
  - Cross-cutting themes (alerts are table-stakes, jurisdiction-specific compliance is table-stakes, manual processes are pain)
  - Willingness-to-pay validation ($250–$400/month)
  - Validated assumptions table

- **Assumptions Ranked** — [assumptions-ranked.md](assumptions-ranked.md)
  - 8 critical assumptions with Tier 1/2/3 ranking
  - For each: what I assumed, evidence I have, evidence I need, validation approach

- **Go/No-Go Framework** — [go-no-go-framework.md](go-no-go-framework.md)
  - 7 major decision gates with go/no-go triggers and pivot strategies
  - Example: MVP Gate requires >95% F1 extraction accuracy; if stuck <90%, triggers rearchitect decision

- **Validation Plan** — [validation-plan.md](validation-plan.md)
  - Concrete Week 1–4 de-risking plan
  - Week 1: Pricing validation (50 users, target >60% willing at $250–$400/month)
  - Week 2: Competitive threat assessment
  - Week 3: GTM validation ($5K LinkedIn + $5K cold email, measure CAC)
  - Week 4: Feature validation (mockup test with 5 beta users)

### Stage 3: Specification

Not included in this case study (the product is concept-stage, not PRD-stage). Once validation passes, use [templates/PRD-TEMPLATE.md](../../../templates/PRD-TEMPLATE.md) to build the full spec.

### Lessons Learned — [lessons-learned.md](lessons-learned.md)

10 meta-lessons from the PRD process (not a shipping retrospective):

1. **Move fast on validation, not building** — 2–3 weeks user research before PRD
2. **PRD evaluation is thinking tool, not gate** — Found 8 blockers, fixed them pre-handoff
3. **Rank assumptions by risk, test Tier 1 first** — WTP (kill-product), Jurisdiction support (pivot), CAC (deprioritization)
4. **Build go/no-go frameworks before building** — Define success criteria before testing
5. **Competitive threat modeling matters more than expected** — Spend as much time on "why can't competitors catch up" as feature design
6. **What I'd do differently if building again** — Deeper competitive threat modeling, earlier GTM de-risking, more user interviews (5→10), earlier technical spike (Week 2), deeper regulatory deep-dive

## How to Use This Case Study

**If you're validating a new product:**
- Use this as a template. Follow the structure: hypothesis → market research → user research → assumptions ranking → go/no-go framework → validation plan
- Adapt the interviews, market sizing models, and competitive analysis to your domain

**If you're hiring or assessing product thinking:**
- This demonstrates:
  - Market sizing rigor (two models, triangulation)
  - Deep customer discovery (3 personas with direct quotes)
  - Ranked assumptions and risk assessment
  - Explicit go/no-go frameworks
  - Competitive threat modeling beyond features
  - A clear de-risking plan before engineering commitment

**If you're skeptical about hypothesis testing:**
- Walk through the assumptions ranking and ask: "Which of these would kill the product if wrong?" The answer is Tier 1. That's what you test in Week 1–2 before touching code.

## Key Insights from This Case Study

### 1. Regulatory Timing Creates Market Opportunity

ASC 842 (2022) created a new compliance burden for all leaseholders. Most mid-market companies still use spreadsheets. The regulatory change, combined with incumbent consolidation, created a 2–3 year window to own the mid-market.

### 2. Incumbents Cannot Move Fast Into New Segments

CoStar and Visual Lease built their business on enterprise (50,000+ seats). They cannot unbundle to mid-market without:
- Revenue loss (unbundling = lower ARPU)
- Organization conflict (salesforce built for enterprise deals)
- Product debt (architecture assumes high-seat-count economics)

This is the classic innovator's dilemma. It's not that they don't see the opportunity — it's that they can't pursue it without destroying their core business.

### 3. Willingness-to-Pay is Separate from Excitement

All 8 users interviewed were excited about the product concept. But when asked directly: "Would you pay $300/month?" the answer was: 6/8 yes at $250–$400, 2/8 "maybe at $150/month."

If you don't separate excitement from WTP, you'll price wrong and burn through runway.

### 4. Jurisdiction Specificity is Table-Stakes, Not Differentiation

Every legal officer interviewed mentioned maintaining multiple spreadsheets for different jurisdictions (CA, NY, TX have different compliance rules). You thought jurisdiction tracking was a differentiation point. It's actually table-stakes — table-stakes don't sell, they're requirements.

The real differentiation is: "We have jurisdiction expertise + you don't have to hire an expert."

### 5. Competitive Threat Modeling is About Structural Defensibility, Not Features

The question isn't "Can Google build this?" (yes, easily). The question is "Why won't Google build this, and why won't CoStar catch us in 12 months?"

Answers:
- **Google:** Different pricing model (per-seat → per-customer), different GTM (Google Cloud → mid-market direct sales). Misaligned incentives.
- **CoStar:** Existing customers demand enterprise pricing; moving to $300/month would cannibalize revenue. Regulatory barrier for new entrant to get certified before CoStar does.

If your defensibility relies on "features are hard to copy," you'll lose. If it relies on "structure and positioning," you'll win.

## Recommended Reading Within This Case Study

- Start: **[hypothesis.md](hypothesis.md)** — 15-minute read on market sizing and competitive gap
- Then: **[validation/user-research-summary.md](validation/user-research-summary.md)** — 15-minute read showing what validated customer research looks like
- Then: **[assumptions-ranked.md](assumptions-ranked.md)** — 10-minute read on risk ranking
- Deep dive: **[validation-plan.md](validation-plan.md)** — 20-minute read on concrete de-risking activities
- Reflection: **[lessons-learned.md](lessons-learned.md)** — 15-minute read on what you'd do differently

---

**Version:** 1.0 | **Status:** Concept-stage (not shipping) | **Last Updated:** July 2026
