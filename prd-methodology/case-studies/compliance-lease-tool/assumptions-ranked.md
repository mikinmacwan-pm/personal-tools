# Assumptions Ranked by Risk — Compliance Lease Tool

**Tier 1 (Kill the Product), Tier 2 (Major Pivot), Tier 3 (Feature Reprioritization)**

## Tier 1: Kill-the-Product Assumptions

These assumptions, if wrong, make the product not viable. Test these in Week 1–2 before engineering commitment.

---

### Tier 1.1: Willingness-to-Pay ≥ $250/Month

**What I assumed:** Mid-market customers (lease admins, portfolio managers, legal officers) would pay $250–$500/month for a compliance-first lease tool.

**Why it matters:** If WTP is <$150/month, CAC ($2K–$3K) cannot be justified. Product is not economically viable.

**Evidence I have:**
- 8 user interviews across 3 personas (Sarah, Marcus, Jennifer)
- Direct WTP questions using Van Westendorp-style price sensitivity
- 6/8 users willing to pay $300–$500/month
- 2/8 users willing at $150–$250/month

**Confidence:** Medium-High (85%)

**Evidence I don't have:**
- Survey data (n=50+) to validate willingness across broader market
- Actual pricing experiment (beta users paying real money)
- Pricing elasticity data (how does demand vary with price?)

**Validation approach:**
- Run Van Westendorp Price Sensitivity Meter survey with 50+ mid-market companies (Week 1, 1 day to execute)
- If >60% willing to pay $250+, proceed to engineering
- If <50%, pivot to lower pricing model or target different persona (e.g., legal officers who have higher WTP)

**Pivot if wrong:**
- **Option A:** Lower pricing to $150–$200/month and accept lower margins (need to hit 1,000+ customers by Year 3 instead of 5,500)
- **Option B:** Target legal officers / compliance managers only (higher WTP, smaller TAM)
- **Option C:** Kill the product

---

### Tier 1.2: Alerts Are Table-Stakes, Not Differentiation

**What I assumed:** Every competitor, including DIY solutions, must offer proactive renewal/compliance alerts to be considered table-stakes.

**Why it matters:** If alerts are differentiator (not table-stakes), TAM shrinks because many users won't upgrade from spreadsheet just for alerts. If alerts are table-stakes, we need differentiation elsewhere (jurisdiction expertise, ESG tracking, etc.).

**Evidence I have:**
- 100% of user interviews (8/8) mentioned alerts as non-negotiable requirement
- Users said: "If there's no alert system, I'm not switching" (Sarah), "Real-time alerts change the game" (Marcus), "Automated alerts prevent audit findings" (Jennifer)
- Market research shows all competitors (CoStar, AppFolio, LeaseLock) offer alerts

**Confidence:** Very High (95%)

**Evidence I don't have:**
- Pricing experiment showing users won't pay premium for alerts
- Competitive analysis of whether alerts are truly table-stakes or just common

**Validation approach:**
- In MVP, ship alerts but don't emphasize as differentiator in marketing
- Emphasis instead on jurisdiction expertise + compliance gaps
- If customers churn because they expected more advanced alerting, then alerts are not actually table-stakes

**Pivot if wrong:**
- If users churn because alerts are inadequate, invest in advanced alerting (real-time amendments, SMSmessages, Slack integration)
- This would shift TAM downmarket (smaller companies that need more hand-holding)

---

### Tier 1.3: Jurisdiction-Specific Compliance Is Necessary (≥5 States Year 1)

**What I assumed:** Mid-market companies need jurisdiction-specific compliance support for at least 5 states (California, Texas, New York, Illinois, Florida) to make the product table-stakes vs. spreadsheet.

**Why it matters:** If users only need 1–2 state tracking, spreadsheet is sufficient. If they need 5+ state tracking, purpose-built tool becomes necessary.

**Evidence I have:**
- Jennifer (legal officer) explicitly mentioned tracking 3 jurisdictions (CA, TX, NY)
- Sarah (lease admin) mentioned "Texas allows 60-day notice, New York requires 90 days"
- Market research shows 25%+ of mid-market companies operate in 3+ states

**Confidence:** High (85%)

**Evidence I don't have:**
- Survey of broad market showing how many states mid-market companies operate in
- Pricing data showing if customers will pay premium for multi-state support

**Validation approach:**
- In MVP, ship with support for top 5 states (CA, TX, NY, IL, FL) where most commercial real estate activity happens
- In beta, ask customers: "Would you switch if we only supported your primary state?"
- If 80%+ say "I need at least 2 states," confirm assumption
- If <50% say this, deprioritize multi-state support

**Pivot if wrong:**
- If users don't need multi-state support, pivot to single-state "compliance specialist" tool (very focused GTM, regulatory depth)
- This reduces TAM but increases defensibility vs. national players

---

### Tier 1.4: CAC < $3,000 Is Achievable

**What I assumed:** Customer acquisition cost (fully loaded) would be <$3,000 per customer in Year 1–2.

**Why it matters:** At $300/month ARPU and 3-year LTV of $10,800, CAC of $3,000 = 27% of LTV. If CAC is $5K+, business is not viable.

**Evidence I have:**
- Comparable products (AppFolio, PropertyShark) report CAC of $1,500–$2,500 for mid-market SaaS
- If we can get 50 sales-assisted customers + 50 self-serve customers from network in Year 1 with $50K marketing, CAC = $500 (very low)

**Confidence:** Medium (60%)

**Evidence I don't have:**
- Actual customer acquisition data (haven't acquired customers yet)
- Pricing/positioning sensitivity (CAC depends heavily on positioning and messaging)

**Validation approach:**
- In validation phase (this week), run 3 small paid campaigns (LinkedIn ads, cold email, Product Hunt):
  - $5K LinkedIn ads targeting lease administrators, measure CPL (cost per lead) and CAC
  - $5K cold email to 500 targets, measure reply rate and conversion
  - Product Hunt post (free; measure traffic and signups)
- If CAC from paid channels is >$3K, shift to founder-led sales + word-of-mouth in Year 1 (target 200–300 customers, 80% from warm network)

**Pivot if wrong:**
- If CAC is $5K+, shift to enterprise GTM (higher ACV, lower CAC as % of LTV)
- Requires repositioning product for enterprise and adding 2–3 senior sales resources

---

## Tier 2: Major-Pivot Assumptions

These assumptions, if wrong, require significant repositioning or feature changes but don't kill the product.

---

### Tier 2.1: Lease Data Extraction Can Achieve ≥95% F1 with LLMs

**What I assumed:** Fine-tuned LLMs (Claude, GPT-4) can extract lease data (dates, renewal terms, jurisdiction, ESG clauses) with ≥95% F1 accuracy after fine-tuning on 1,000–2,000 leases.

**Why it matters:** If extraction accuracy is <85%, product is too error-prone for compliance use case. If it's 85–90%, requires heavy human review (doubles cost). If 95%+, nearly fully automated.

**Evidence I have:**
- Industry benchmarks show LLM-based document extraction at 90–95% F1 on structured documents (leases, contracts)
- Foundation model providers (Anthropic, OpenAI) have published improvements in long-context understanding (needed for 50+ page leases)
- Proprietary legal AI companies (LawGeex, Everlaw) report 90%+ accuracy on legal document analysis

**Confidence:** Medium (70%)

**Evidence I don't have:**
- Actual test on our lease corpus (need to fine-tune on real leases to validate)
- Performance on edge cases (very old leases, custom amendments, escrowed terms)

**Validation approach:**
- In Week 2–3, conduct technical spike: 
  - Collect 100 representative leases from users
  - Fine-tune Claude or GPT-4 on 50, test on 50
  - Measure F1 on key fields (start/end date, renewal terms, jurisdiction, amendments)
  - Target: ≥90% F1 or higher
- If <85%, pause product and do 2-week ML research spike
- If 85–90%, proceed with manual review workflow (doubles cost, limits scale)
- If 95%+, proceed with full automation

**Pivot if wrong:**
- If extraction accuracy is <85%, pivot to "compliance template + data entry" tool (users manually enter, we provide templates and alerts)
- This shifts from "magical automation" to "guided compliance process" (lower TAM but still viable)

---

### Tier 2.2: Jurisdiction-Specific Compliance Is Differentiator (vs. Table-Stakes)

**What I assumed:** Jurisdiction-specific compliance support is a true differentiator that competitors won't copy in 12 months.

**Why it matters:** If competitors easily add jurisdiction support (hiring lawyers, building rules DB), we lose our moat quickly. If it's truly hard (requires deep expertise or regulatory relationships), we have 18–24 month window.

**Evidence I have:**
- Jennifer (legal officer) said jurisdiction tracking is primary pain; no tool addresses this well
- Market research shows CoStar treats all jurisdictions generically; AppFolio has no jurisdiction support
- Building jurisdiction rule database requires expertise + ongoing research + legal review = 6–12 months effort

**Confidence:** Medium (65%)

**Evidence I don't have:**
- Direct feedback from competitors about whether they'd prioritize jurisdiction support
- Analysis of whether jurisdictional moat is defensible long-term (vs. hiring legal expertise)

**Validation approach:**
- In MVP, ship with CA, TX, NY jurisdiction rules (top 3 markets)
- Emphasize jurisdiction expertise in GTM messaging
- Track: Do customers specifically choose us for jurisdiction support?
- If 60%+ of customers say jurisdiction was a top 3 decision factor, assume it's true differentiator
- If <30% mention it, assume it's table-stakes and shift differentiation to extraction accuracy or ESG tracking

**Pivot if wrong:**
- If competitors can quickly copy jurisdiction support, shift differentiation to "end-to-end compliance automation" (combination of alerts + extraction + audit trail)
- This is harder to copy in 6 months and buys time

---

### Tier 2.3: Churn < 5% Monthly (90%+ Retention)

**What I assumed:** Customer churn would be <5% monthly after first 3 months (90% 12-month retention).

**Why it matters:** At $300/month, CAC of $3K, we need >85% retention to break even on CAC in 12 months. If churn is >8%, unit economics break.

**Evidence I have:**
- Comparable B2B SaaS products (mid-market CRE software) report 90–95% annual retention
- High switching cost (leases are mission-critical) suggests lower churn than average SaaS

**Confidence:** Medium (60%)

**Evidence I don't have:**
- Actual churn data (we haven't had customers long enough)
- Sensitivity analysis (what drives churn in this category?)

**Validation approach:**
- In Year 1, track churn religiously by cohort (month 3, 6, 12)
- If 12-month cohort retention is <85%, conduct churn interviews to understand why
- Pivot: If churn is driven by "product didn't deliver on extraction accuracy," invest in ML
- Pivot: If churn is driven by "customer didn't understand how to use tool," invest in onboarding + education

**Pivot if wrong:**
- If churn is >8% monthly, shift to shorter contract terms (annual → quarterly) to force more frequent check-ins
- Or, shift to usage-based pricing (per-lease, not flat) to better align with customer value

---

## Tier 3: Feature-Level Assumptions

These assumptions affect feature prioritization but don't kill the product or require pivots.

---

### Tier 3.1: Automated Amendment Tracking Will Be Possible

**What I assumed:** We can automatically detect lease amendments (via email from tenant, filing with state, etc.) and integrate them into the compliance database.

**Why it matters:** If we can't automate amendment tracking, users must manually log amendments (defeats automation promise). If we can, we save 10+ hours per year per customer.

**Evidence I have:**
- Marcus (portfolio manager) mentioned amendments as major pain point
- Technical feasibility: email integration + document OCR is possible
- Not table-stakes: Users can live with manual amendment logging in MVP

**Confidence:** Medium (65%)

**Evidence I don't have:**
- Whether users would use email-based amendment logging (might be too much friction)
- Whether amendment accuracy (detection) can match lease extraction accuracy

**Validation approach:**
- Phase 2 feature, not MVP
- In MVP, require users to manually log amendments via web form
- Track: Do users actually log amendments, or does 70% slip through?
- If usage is low, deprioritize auto-amendment tracking
- If usage is high, accelerate email integration + OCR

---

### Tier 3.2: ESG Compliance Tracking Will Drive Upsell Revenue

**What I assumed:** ESG compliance features will drive $50–$100/month upsell (or upgrade tier) by Year 2.

**Why it matters:** ESG is mentioned by Jennifer; Tier 2 assumption is that it's valuable enough to upsell.

**Evidence I have:**
- Jennifer (legal officer) mentioned ESG disclosures as growing requirement
- 62% of institutional real estate companies now track ESG (market research)
- Not table-stakes: can ship without ESG support; users can manage separately

**Confidence:** Low (50%)

**Evidence I don't have:**
- Direct WTP for ESG tracking (didn't ask in interviews)
- Whether customers would pay extra or expect it bundled

**Validation approach:**
- Revisit in Year 2 after core compliance product is stable
- Survey existing customers: "Would you pay $100/month for ESG tracking?"
- If >50% say yes, prioritize in Year 2 roadmap
- If <30% say yes, deprioritize

---

### Tier 3.3: Mobile App Is Nice-to-Have, Not MVP

**What I assumed:** Mobile app (iOS/Android) is not required for MVP; web-first product is sufficient.

**Why it matters:** Mobile app adds 3–4 months to MVP timeline and $100K+ in cost. If users primarily check renewals on mobile, MVP is blocked.

**Evidence I have:**
- Sarah (admin) didn't mention mobile as a pain point; primarily works from desk
- Marcus (portfolio manager) didn't mention mobile; reviews Friday spreadsheets on laptop

**Confidence:** High (85%)

**Evidence I don't have:**
- Whether compliance workflows require on-site mobile access (e.g., physical property visits)

**Validation approach:**
- MVP is web-only (responsive design for mobile browsers, not native app)
- Track: What % of MVP users access from mobile?
- If >30%, prioritize mobile app in Phase 1B (before Year 1 GA)
- If <10%, deprioritize indefinitely

---

## Summary: Risk Matrix

| Assumption | Tier | Confidence | Validation Timeline | Pivot Risk |
|---|---|---|---|---|
| WTP ≥ $250/month | 1 | 85% | Week 1 | Kill/Reposition |
| Alerts are table-stakes | 1 | 95% | MVP | Low |
| Jurisdiction support needed (5 states) | 1 | 85% | MVP | Reposition |
| CAC < $3K | 1 | 60% | Week 3–4 (GTM test) | Reposition to enterprise |
| Extraction ≥95% F1 | 2 | 70% | Week 2 (technical spike) | Feature reduction |
| Jurisdiction is differentiator | 2 | 65% | MVP + market feedback | Feature addition |
| Churn < 5% monthly | 2 | 60% | Year 1 (actual data) | Pricing/packaging change |
| Amendment tracking auto | 3 | 65% | Phase 2 | Skip feature |
| ESG upsell | 3 | 50% | Year 2 | Defer or skip |
| Mobile app needed | 3 | 85% | MVP usage data | Defer or skip |

---

**Version:** 1.0 | **Status:** Ready for Validation & Technical Spike | **Last Updated:** July 2026
