# Validation Plan — Compliance Lease Tool

**Concrete Week 1–4 de-risking activities before engineering commitment**

---

## Week 1: Pricing Validation

**Objective:** Confirm WTP at $250–$500/month (Tier 1 assumption)

### Day 1–2: Survey Design & Recruitment

**Method:** Van Westendorp Price Sensitivity Meter (n=50–100 mid-market companies)

**Survey questions:**
1. At what price is this product too expensive and you would not consider buying it?
2. At what price is this product so cheap you would question the quality?
3. At what price would this product be a bargain?
4. At what price is this product getting expensive?

**Recruitment:**
- Target: Lease administrators, portfolio managers, legal officers at companies with 50–500 leases
- Channels: LinkedIn ads, email to AppFolio users, cold email to commercial real estate companies
- Incentive: $10 Amazon gift card for completion
- Target sample: 50–100 respondents (50-75% completion rate from recruitment)

**Success criteria:** Response rate >40% (invest $3K–$5K in paid recruitment to hit 50 responses)

### Day 2–3: Survey Execution

**Timeline:** 48-hour rapid survey cycle

**Expected results:** Probability distribution of willingness to pay

**Success criteria:**
- 60%+ respondents willing to pay $250+/month
- Price range is $200–$400 (concentrated around $300)

**No-go triggers:**
- <50% willing to pay $250+/month (need to reposition or lower pricing)
- Bimodal distribution ($100–$200 vs. $500+) indicates two distinct segments (need different positioning per segment)

### Day 3: Analysis & Decision

**If WTP validates:** Confirm $299–$399 price range for public beta

**If WTP doesn't validate:** 
- **Option 1:** Lower pricing to $150–$200/month (higher volume, lower margins)
- **Option 2:** Target legal officers only (Jennifer had highest WTP at $400–$500)
- **Option 3:** Package with other features (amendments automation, comps data) to justify higher price

**Decision:** Proceed to Week 2 regardless (other assumptions need validation in parallel)

---

## Week 2: Competitive Threat Modeling

**Objective:** Understand competitive response timeline and de-risk competitive assumption (Tier 2)

### Day 1: Competitor Call Plan

**Calls with 5 customers of CoStar's mid-market offering:**

**Discussion guide:**
1. "Why did you choose CoStar?"
2. "What would it take for you to switch to a different solution?"
3. "If CoStar offered a $300/month mid-market plan, would you stay or switch?"
4. "What would a competitor need to do to win you?"

**Recruitment:** 
- Use LinkedIn or Crunchbase to find companies using CoStar's mid-market tier
- Cold email: "We're researching mid-market lease accounting solutions and would love 15 minutes to understand your needs"
- Incentive: Insights report on mid-market trends

**Target:** 5 calls (high-quality over volume)

### Day 2–3: Competitive Threat Assessment

**For each major competitor, answer:**
1. **Time to move:** How long would it take them to build our product? (CoStar: 12–18 months for clean mid-market SKU)
2. **Organizational barriers:** What internal constraints prevent them from moving fast? (CoStar: seat-based pricing, customer expectations of bundled product)
3. **Risk to them:** What's the cannibalization risk of moving into mid-market? (CoStar: ~$50M revenue at risk if mid-market unbundles)
4. **Switching cost:** If CoStar moves, can we retain customers? (High if we have strong product-market fit + data lock-in)

### Day 3: Decision

**Competitive threat model output:**
- Timeline to competitive response: 18–24 months
- Defensibility strategies: Establish customer lock-in early (audit trails, data integrations, ESG extensions)
- Trigger point: If CoStar announces mid-market product, shift to customer retention focus

**Decision:** Proceed to MVP (competitive window is real but not immediately threatening)

---

## Week 3: GTM Validation

**Objective:** Validate that CAC < $3K is achievable (Tier 1 assumption)

### Day 1–2: Paid Campaign Setup

**Test 3 acquisition channels with $5K budget:**

**Channel 1: LinkedIn Ads ($2K)**
- Target: Job title "lease administrator" + company size 50–500
- Creative: "Automated lease compliance" (pain point-focused)
- Landing page: 1-pager explaining value (3–5 min read)
- Metrics: CPL (cost per lead), CTR, conversion to sign-up

**Channel 2: Cold Email ($1.5K)**
- Target: Email list of 500 lease administrators (scraped from LinkedIn or purchased)
- Message: "Missed a lease renewal? It costs $40K every time. Here's how we solve it."
- Landing page: Same as LinkedIn
- Metrics: Open rate, reply rate, sign-up rate

**Channel 3: Product Hunt ($0 but ~8 hours labor)**
- Post: "We automate lease renewal tracking for mid-market"
- Metrics: Upvotes, clicks, sign-ups

### Day 2–3: Campaign Execution

**Success criteria:**
- LinkedIn CPL < $100 (if $100+ CPL × typical 3% conversion rate = $3,300 CAC — too high)
- Cold email reply rate >5% (indicates strong problem relevance)
- PH upvotes >200 (indicates market interest)

### Day 3: Analysis & Decision

**Expected results:**
- Founder-led + network acquisition: CAC ~$500 (low-cost, early adopters)
- Paid channels: CAC ~$2K–$3K (realistic for Year 1–2)
- Blended CAC: ~$2K if we do 50% founder-led + 50% paid in Year 1

**If CAC validates:** Proceed to paid acquisition in Year 1–2

**If CAC is too high (>$4K from paid channels):**
- Shift to founder-led sales (lower CAC but slower growth)
- Consider enterprise GTM (higher ACV, different positioning)

**Decision:** Proceed to MVP regardless (GTM can be optimized post-MVP)

---

## Week 4: Feature Validation (MVPScope)

**Objective:** Confirm MVP feature set with 5 beta users; test willingness to pay

### Day 1–2: MVP Mockup Creation

**Build mid-fidelity mockups (Figma) for:**
1. Lease data upload + extraction
2. Renewal alert dashboard (90 days out)
3. Compliance checklist (jurisdiction-specific)
4. Audit trail + amendments log

**Mockups should be:** Realistic enough to judge usability; not pixel-perfect (clearly a mockup)

### Day 2–3: Beta User Testing

**Recruit 5 beta users from earlier interview cohort:**
- Sarah (lease admin)
- Marcus (portfolio manager)
- Jennifer (legal officer)
- 2x other users from earlier interviews

**Testing protocol (1 hour per user):**

1. **Introduction (5 min):** "Here's a working prototype of what we're building. Let's walk through it together."

2. **Scenario 1 — Upload Lease (15 min):** 
   - "Imagine you have 5 new leases to add to the system. Walk me through how you'd do it."
   - Observe: Do users understand the upload flow? Do they get confused?

3. **Scenario 2 — Check Renewals (15 min):**
   - "It's Friday morning. You want to see what leases are coming up for renewal. Walk me through."
   - Observe: Is the dashboard intuitive? Do users find the info they need?

4. **Scenario 3 — Review Compliance (15 min):**
   - "You need to ensure this lease complies with Texas law. Walk me through."
   - Observe: Do users understand jurisdiction-specific requirements? Is the checklist helpful?

5. **Willingness-to-Pay (10 min):**
   - "Based on what you've seen, would you pay $300/month for this?"
   - Listen for: Confidence level, feature requests, concerns

### Day 3: Analysis & Decision

**Mockup test results (decision logic):**

| Finding | Action |
|---|---|
| 4/5 users complete scenario without confusion | ✅ MVP feature set is ready |
| 3/5 users ask for "X feature not in mockup" | Add feature to MVP only if >50% mention it |
| <3/5 complete scenarios without confusion | Revisit UX; consider design sprint before MVP build |
| 4/5 say "yes" to $300/month WTP | ✅ Price is validated |
| <3/5 say yes to WTP | Revisit positioning or lower price |

**Expected outcome:** Confirm that MVP has right feature set before engineering starts

**Decision:** If >80% of tests are successful, proceed to PRD. Otherwise, iterate.

---

## Decision Logic: When to Pivot vs. Proceed

### Proceed to MVP (All Tier 1 Assumptions Validated)

- [ ] WTP survey shows 60%+ willing to pay $250+/month
- [ ] Competitive threat model is credible (18–24 month window)
- [ ] Paid CAC is <$3K or founder-led path is viable
- [ ] Mockup testing shows 4/5 users understand MVP flow

### Pivot (One or More Tier 1 Assumptions Fail)

**If WTP < $250/month:**
- Lower pricing to $150–$200
- OR target legal officers only (higher WTP)
- OR add features (ESG, amendments) to justify higher price

**If CAC is >$4K paid:**
- Shift to founder-led sales (lower CAC, slower growth)
- OR target enterprise (higher ACV)

**If mockup testing fails:**
- Do 1-week design sprint
- Simplify MVP (fewer features, cleaner UX)
- Re-test with 3 users

**If competitive threat timeline is <12 months:**
- Accelerate MVP timeline (cut nice-to-have features)
- Focus on customer lock-in (audit trails, integrations)

### Kill (Multiple Tier 1 Assumptions Fail)

If >2 of the following are true, consider killing the project:
- WTP < $200/month and no obvious repositioning path
- Competitive threat timeline is <6 months and we can't differentiate
- CAC is >$5K paid and founder-led sales can't support growth
- Mockup testing shows fundamental UX/positioning misalignment

---

## Resource Plan (Week 1–4)

| Week | PM | Engineer | Designer | Total |
|---|---|---|---|---|
| **Week 1** | 5 days (survey) | – | – | 5d |
| **Week 2** | 4 days (competitor calls + analysis) | 1 day (tech spike plan) | – | 5d |
| **Week 3** | 3 days (campaign setup + analysis) | 2 days (technical spike) | – | 5d |
| **Week 4** | 3 days (mockup testing) | 1 day (tech spike) | 5 days (mockup creation) | 9d |
| **Total** | 15 days | 4 days | 5 days | 24d (should be 4–5 weeks) |

**Budget:** $10K–$15K
- Survey platform ($200)
- Paid ads ($5K)
- Cold email software ($500)
- Recruitment incentives ($1K)
- Designer contractor ($2K)
- Miscellaneous ($1K–$5K)

---

## Success Criteria: Go to PRD Phase

**All of the following must be true to proceed to PRD specification (Week 5+):**

1. ✅ WTP is validated at $250+/month (60%+ willing to pay)
2. ✅ Competitive threat model is credible and timeline is 18+ months
3. ✅ Paid CAC is <$3K OR founder-led path is viable
4. ✅ MVP feature set is confirmed via mockup testing (80%+ user success)
5. ✅ No Tier 1 assumptions have failed

**If any of these fails, iterate on validation or pivot product before proceeding to engineering.**

---

**Version:** 1.0 | **Status:** Ready to Execute | **Last Updated:** July 2026
