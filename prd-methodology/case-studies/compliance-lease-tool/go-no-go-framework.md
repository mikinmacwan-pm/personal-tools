# Go/No-Go Framework — Compliance Lease Tool

**7 major decision gates with explicit go/no-go triggers and pivot strategies**

---

## Gate 1: Market Validation (Week 0–1)

**Question:** Is there a real, sized market with defensible competitive gap?

### Go Criteria
- [ ] TAM > $400M with two convergent sizing models (within 2–3×)
- [ ] SAM > $100M in US mid-market
- [ ] Competitive white space identified (no direct competitor owns "compliance-first, mid-market")
- [ ] 3+ external timing signals

### Current Status: ✅ GO

**Evidence:**
- TAM: $500M–$700M (IDC top-down + bottom-up customer × spend triangulated)
- SAM: $150M–$200M (US mid-market, 50–500 leases)
- White space: No competitor owns "compliance-first, mid-market" positioning
- Timing: ASC 842 (2022), ESG surge (2024), AI capability (2023), incumbent consolidation (2023–2024), competitive gap (observed)

### No-Go Triggers
- [ ] TAM < $100M (market is too small)
- [ ] Incumbent can easily unbundle (no defensible white space)
- [ ] No external timing justification (would have been good idea 2+ years ago)

### Pivot Strategies
- **If TAM is lower than estimated:** Target enterprise (higher ACV, lower volume needed)
- **If white space is smaller:** Focus on vertical (legal-first, rather than admin-first)

**Decision:** PROCEED to Problem Validation (Week 1–4)

---

## Gate 2: Problem Validation (Week 1–4)

**Question:** Do target personas actually have the problem, and will they pay for a solution?

### Go Criteria
- [ ] 3–5 interviews per persona show clear evidence of problem (not just stated, but shown in behavior/workarounds)
- [ ] 60%+ of users willing to pay $250+/month (Tier 1 assumption validation)
- [ ] Current workaround is manual, time-consuming, or error-prone
- [ ] Competitive threat model is credible (specific, grounded in customer research)

### Current Status: ✅ GO

**Evidence:**
- Sarah (admin): 3–4 hrs/week on manual tracking; missed deadline once; WTP $300–$400
- Marcus (portfolio manager): 3–4 hrs/week on triage; no real-time data; WTP $300–$500
- Jennifer (legal officer): 4–5 hrs/week on jurisdiction compliance; WTP $400–$500
- 6/8 users willing to pay $250+/month

### No-Go Triggers
- [ ] Users don't actually do the work (it's assumed pain, not lived pain)
- [ ] WTP is <$150/month (CAC cannot be justified)
- [ ] Everyone is already happy with CoStar or equivalent (low switching motivation)
- [ ] Can't articulate why we win vs. top 3 competitors

### Pivot Strategies
- **If WTP is $150–$250:** Lower pricing model or target different persona (legal officers have higher WTP)
- **If problem is less acute than expected:** Pivot to different job (e.g., ESG tracking instead of renewal alerts)
- **If everyone loves CoStar:** Reposition as "CoStar alternative for mid-market" (very specific, competitive messaging)

**Decision:** PROCEED to PRD Specification (Week 3–4)

---

## Gate 3: PRD Readiness (Week 4)

**Question:** Is the spec defensible? Does it pass the evaluation rubric with 0 blockers?

### Go Criteria
- [ ] 26-item PRD evaluation rubric results show 0 blockers
- [ ] Key assumptions are ranked by risk (Tier 1/2/3)
- [ ] Success metrics are quantified (target accuracy, churn, CAC, retention)
- [ ] Model selection is justified (compared to at least one alternative)

### Go/No-Go Decision Process
- Run PRD through 26-item rubric
- If blockers found, iterate until 0 blockers achieved
- If improvements found, prioritize by impact (blocking vs. nice-to-know)

### Current Status: PENDING (PRD not yet written)

**Target completion:** EOW Week 4

### No-Go Triggers
- [ ] >3 blockers on rubric (gaps in core thinking)
- [ ] Key assumptions are untestable in MVP (no way to know if right for 12+ weeks)
- [ ] Feature scope looks like Phase 2, not MVP
- [ ] No responsible AI assessment for AI product

### Pivot Strategies
- **If blockers are found:** Iterate on spec, don't proceed to engineering
- **If scope is too large:** Strip features, define true MVP (3–4 core features only)
- **If model selection is uncertain:** Do 1-week technical spike before PRD handoff

**Decision:** [To be made after PRD is written]

---

## Gate 4: Engineering Spike (Week 2, Parallel Path)

**Question:** Is the core technical challenge solvable? Can we extract lease data with >90% accuracy?

### Go Criteria
- [ ] Lease data extraction (dates, terms, jurisdiction, amendments) achieves ≥90% F1 on test set
- [ ] Extraction cost is <$0.01 per page (economically viable)
- [ ] Infrastructure architecture is sound (data pipeline, model serving, error handling)

### Current Status: PENDING (Tech spike not yet run)

**Timeline:** Week 2–3 (1–2 week spike)

**Test Plan:**
- Collect 100 representative leases from users
- Fine-tune Claude or GPT-4 on 50 leases
- Test on held-out 50
- Measure F1 on: start date, end date, renewal terms, jurisdiction, amendments, ESG clauses

### No-Go Triggers
- [ ] F1 < 85% (too error-prone for compliance use)
- [ ] Cost > $0.02 per page (unit economics don't work)
- [ ] Infrastructure is complex (>12 weeks to build)

### Pivot Strategies
- **If F1 is 85–90%:** Proceed but add manual review workflow (QA + double-check step)
- **If F1 is <85%:** Pause; do 2-week ML research on domain adaptation techniques
- **If cost is too high:** Reduce scope (only extract critical fields, not all metadata)

**Decision:** [To be made after technical spike]

---

## Gate 5: MVP Shipping (Week 12, Target)

**Question:** Does the MVP deliver on core value proposition? Target metrics: >95% F1 extraction, <5% monthly churn on early cohort.

### Go Criteria
- [ ] 50–100 beta customers have used product for 4+ weeks
- [ ] Extraction accuracy ≥95% F1 in production (vs. 90% in lab)
- [ ] Alert system is reliable (zero false positives on renewal alerts)
- [ ] Churn in first 4 weeks is <2% (early-adopter retention is strong)
- [ ] NPS from beta users is >40 (or at least 60%+ say "would recommend to colleague")

### Go/No-Go Decision Process
- After 4 weeks with 50 beta users, measure:
  - F1 accuracy on extracted data
  - Alert reliability (compare alerts to ground truth)
  - Weekly churn rate
  - NPS or recommendation likelihood

### Current Status: PENDING (MVP not yet built)

### No-Go Triggers
- [ ] F1 < 90% in production (accuracy regressed from lab)
- [ ] Churn > 5% weekly (early adopters are not satisfied)
- [ ] >10% of alerts are false positives (users distrust system)
- [ ] <40% NPS or <50% recommendation likelihood

### Pivot Strategies
- **If accuracy is lower in prod than in lab:** Debug why (data drift? Different lease formats?)
- **If churn is high:** Conduct exit interviews to understand why beta users are leaving
  - If due to accuracy issues: prioritize model improvement
  - If due to missing features: prioritize quick feature additions
  - If due to UX issues: prioritize onboarding and support
- **If alerts are unreliable:** Add human review step before alerting (increases cost but improves trust)

**Decision:** [To be made after MVP is built and tested with 50 beta users for 4 weeks]

---

## Gate 6: Beta PMF (Week 14, Target)

**Question:** Do customers love the product and see it as table-stakes? Target: >70% retention at 12 weeks, >50 NPS from diverse segments.

### Go Criteria
- [ ] 50+ beta users across 3+ different personas (admins, portfolio managers, legal officers)
- [ ] 12-week cohort retention is >70% (90%+ 30-day retention)
- [ ] NPS is >40 from each persona (not just early adopters)
- [ ] Paying beta users are willing to renew/upgrade
- [ ] Product-market fit signals exist (users refer friends, open-ended praise)

### Current Status: PENDING (MVP not yet in market)

### No-Go Triggers
- [ ] Retention drops below 50% at 12 weeks (losing users quickly)
- [ ] NPS is <30 (customers not satisfied)
- [ ] Users are churn-adjacent (saying "nice tool but not essential")
- [ ] Retention varies wildly by persona (one segment loves it, another doesn't)

### Pivot Strategies
- **If legal officers love it but admins don't:** Pivot to legal-officer-first positioning (different GTM, different features)
- **If admins love it but portfolio managers don't:** Double down on admin-first positioning and de-emphasize portfolio manager features
- **If retention is strong but NPS is low:** Identify specific pain points and prioritize fixes in Phase 1B

**Decision:** [To be made after beta cohort reaches 12-week mark]

---

## Gate 7: GA Unit Economics (Week 20, Target)

**Question:** Can we reach GA with acceptable unit economics (CAC < $3K, LTV > $10K)?

### Go Criteria
- [ ] CAC from earliest cohorts (founders + word-of-mouth) is <$2K
- [ ] LTV (3-year) is >$10K (churn <5% monthly assumed)
- [ ] Expansion revenue is possible (upsell to 2–3 locations increases ARPU by 20%+)
- [ ] Net revenue retention from cohort 1–2 is >90%
- [ ] Runway to break-even is <24 months

### Current Status: PENDING (No real customer data yet)

### No-Go Triggers
- [ ] CAC is >$5K (paid channels don't work as expected)
- [ ] LTV is <$7K (churn is higher than expected or ARPU is lower)
- [ ] No expansion revenue (customers don't upgrade to higher tiers)
- [ ] Runway to break-even is >30 months (unit economics don't support longer runway)

### Pivot Strategies
- **If CAC is too high:** Shift to founder-led sales (less expensive but slower) or target enterprise (higher ACV, different GTM)
- **If churn is higher than expected:** Invest in onboarding and customer success (reduce churn from 5% to 3%)
- **If expansion revenue is low:** Bundle additional features (ESG tracking, comps data) into higher tier to drive upsell

**Decision:** [To be made after analyzing economics of earliest paying customer cohorts]

---

## Overall Decision Tree

```
Gate 1: Market Validation ──→ ✅ GO
    │
    └──→ Gate 2: Problem Validation ──→ ✅ GO
            │
            └──→ Gate 3: PRD Readiness ──→ [Pending]
                    │
                    ├──→ ✅ GO ──→ Gate 4: Engineering Spike [Parallel] ──→ [Pending]
                    │                    │
                    │                    └──→ Gate 5: MVP Shipping ──→ [Pending]
                    │                            │
                    │                            └──→ Gate 6: Beta PMF ──→ [Pending]
                    │                                    │
                    │                                    └──→ Gate 7: GA Unit Economics ──→ [Pending]
                    │
                    └──→ ❌ NO-GO ──→ Iterate on PRD or Kill Project
```

---

## Key Decision Principles

1. **Each gate must be passed before proceeding.** Don't start engineering until PRD readiness gate is passed.
2. **Parallel gates are OK.** Engineering spike (Gate 4) can run in parallel with PRD writing (Gate 3) to save time.
3. **No skipping gates.** Each gate tests a different assumption. Skipping a gate means shipping without validation.
4. **Pivot doesn't mean kill.** Most "no-go" triggers lead to pivots, not project kills. Only proceed when pivot is clear.
5. **Data-driven decisions only.** Each gate decision is based on specific metrics, not gut feel or optimism.

---

**Version:** 1.0 | **Status:** Gates 1–2 Passed; Gates 3–7 Pending | **Last Updated:** July 2026
