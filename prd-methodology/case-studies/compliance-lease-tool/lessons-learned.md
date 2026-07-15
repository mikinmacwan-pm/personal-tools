# Lessons Learned — Compliance Lease Tool

**10 meta-lessons from the PRD process (not a shipping retrospective, but insights from pre-launch validation)**

---

## Lesson 1: Move Fast on Validation, Not Building

**The principle:** 2–3 weeks of deep user research, market sizing, and competitive analysis beats 6 weeks of building and then discovering the market doesn't want it.

**What happened in this case:**
- 8 user interviews + market research + competitive analysis = 3 weeks effort
- Result: Validated that WTP is defensible, junction-specific compliance is table-stakes, and competitive window is real
- If we had built MVP first (12 weeks), we would have learned these things too late

**Why it matters:**
- User interviews cost $100–$500 per persona
- Building MVP costs $50K–$100K in engineering time
- Learning from interviews is 100–1000× cheaper than learning from failed product

**How to apply:**
- Never proceed to engineering without 3–5 user interviews per persona
- Never write PRD without market sizing (TAM/SAM/SOM)
- Never ship without competitive threat modeling

---

## Lesson 2: PRD Evaluation Is a Thinking Tool, Not a Gate

**The principle:** The 26-item PRD evaluation rubric is most valuable during writing, not after. Use it to find gaps and iterate, not to approve/reject.

**What happened in this case:**
- Used rubric to evaluate draft PRD (would be done at Week 5)
- Finding: ~8 items were initially gaps (no competitive moat articulation, no go/no-go framework, missing assumptions ranking)
- Action: Iterate on spec, fill gaps, run rubric again
- Result: 0 blockers after iteration

**Why it matters:**
- If you wait until end to evaluate, you've already sunk time into a flawed PRD
- If you iterate as you write, you catch gaps early and cheaply

**How to apply:**
- Use the 26-item rubric as a writing checklist, not a final gate
- Run it every 2–3 days while drafting PRD
- Iterate until 0 blockers, then move to engineering

---

## Lesson 3: Rank Assumptions by Risk, Test Tier 1 First

**The principle:** Not all unknowns are equal. Tier 1 assumptions kill the product. Tier 2 require major pivots. Tier 3 are feature-level. Test Tier 1 in Week 1–2.

**What happened in this case:**
- Tier 1: WTP, jurisdiction importance, competitive window
- Tier 2: Extraction accuracy, churn, CAC
- Tier 3: Amendment automation, ESG upsell, mobile app
- Action: Validated Tier 1 before proceeding (pricing survey, competitive calls, mockup testing)
- Result: High confidence to proceed to MVP

**Why it matters:**
- If you don't rank assumptions, you spend equal time testing whether customers want alerts (Tier 1 = kill-product) and whether they want a mobile app (Tier 3 = feature-level)
- Ranking forces prioritization of what could kill you

**How to apply:**
- List 8–10 key assumptions for your product
- For each, ask: "If this is wrong, do we kill the product (Tier 1), pivot (Tier 2), or remove a feature (Tier 3)?"
- Test Tier 1 before engineering starts
- Test Tier 2 in MVP
- Test Tier 3 post-launch

---

## Lesson 4: Build Go/No-Go Frameworks Before Building Anything

**The principle:** Define success criteria at each gate (MVP, Beta, GA) *before* you start work. Otherwise, you'll interpret results optimistically.

**What happened in this case:**
- Defined 7 major gates with explicit go/no-go triggers (see go-no-go-framework.md)
- Example: MVP gate requires >95% F1 extraction + <5% monthly churn
- Action: Built these into spec before engineering started
- Result: Clear stopping points; no ambiguous "is it ready?" discussions

**Why it matters:**
- Without clear criteria, you become emotionally invested ("we've spent 12 weeks, this should ship")
- With clear criteria, you can make objective decisions ("F1 is 88%, that's below 95% threshold, so no-go")

**How to apply:**
- Before engineering starts, write down 3–5 success metrics for MVP
- Make metrics quantified (not "users like it" but "NPS >40")
- Set go/no-go thresholds in advance (not after the data arrives)
- If you miss a threshold, don't ship; instead pivot or rework

---

## Lesson 5: Competitive Threat Modeling Matters More Than Expected

**The principle:** Spend as much time asking "Why can't competitors copy this?" as you spend designing features.

**What happened in this case:**
- Competitive threat model showed CoStar can't move into mid-market in <18 months because:
  - Revenue model misalignment (unbundling would cannibalize)
  - Organizational structure (sales team built for enterprise)
  - Regulatory certification (takes time)
- Action: Built this into de-risking plan (Tier 1 assumption: competitive window is 18+ months)
- Result: Reduced anxiety about "CoStar will just copy us"; increased focus on customer lock-in

**Why it matters:**
- Without competitive threat modeling, you panic when incumbents announce features
- With threat modeling, you know exactly how fast they can move and what would trigger their response

**How to apply:**
- For each major competitor, ask:
  1. Could they build this in 6 months? (yes, but...)
  2. Would their business model allow unbundling? (usually no)
  3. Would their organization let them move fast? (usually no)
  4. What would be their disincentive? (revenue cannibalization, org friction, etc.)
- Your moat is usually structural (business model, org constraints), not technical (features)

---

## Lesson 6: Validate Workarounds, Not Solutions

**The principle:** What do users do *today* when your solution doesn't exist? That's your real competition and your strongest differentiation vector.

**What happened in this case:**
- Asked "What do you use today?" not "Would you use this tool?"
- Found: Sarah uses spreadsheet + calendar reminders + property manager coordination
- Found: Marcus uses CoStar but says it's overkill; also uses spreadsheet
- Found: Jennifer uses manual audit + external counsel review
- Action: Designed against these workflows, not against a theoretical ideal
- Result: MVP features are built for users who currently use spreadsheets and CoStar, not built from scratch

**Why it matters:**
- Workarounds are how users are (how they think, what they value)
- Ideal solutions are how you want them to be (clean, integrated, automated)
- Users are more likely to adopt solutions that improve their workaround incrementally

**How to apply:**
- In user interviews, ask: "Walk me through exactly what you do today. Show me."
- Don't ask: "Would you use a tool that did X?"
- Observe: Where are the manual steps? Where do they fail? What frustrates them most?
- Build your MVP to directly replace the most painful steps of their workaround

---

## Lesson 7: Market Sizing Is Art + Science; Triangulation Matters

**The principle:** Never trust a single market sizing model. Top-down + bottom-up + triangulation. If they diverge >3×, you don't understand the market yet.

**What happened in this case:**
- Top-down (IDC reports) → $420M–$690M
- Bottom-up (customer count × spend) → $328M–$420M
- Converged: $400M–$690M (midpoint $545M)
- Confidence: Medium-High (both methods converge within 1.7×)
- Action: Proceeded with confidence on market sizing; didn't oversell TAM

**Why it matters:**
- Single models are often wrong by 10× (both too big and too small)
- Triangulation catches obvious errors ("our TAM is $100B but top 10 competitors do $5B total" = red flag)

**How to apply:**
- Use at least 2 sizing methods
- If they diverge <2×, average and proceed
- If they diverge 2–5×, investigate why (segmentation? geographic differences?)
- If they diverge >5×, do more research before committing resources

---

## Lesson 8: Write for Execution, Not Beauty

**The principle:** A PRD is read by engineers (who need to build) and ops teams (who need to support). Write for them, not for investors.

**What happened in this case:**
- PRD prioritizes specificity over narrative ("Alert when renewal notice due date is 90 days out" not "Proactive alerts")
- Includes technical details for engineers (model selection, extraction accuracy targets)
- Includes operational details for ops team (audit trail requirements, jurisdiction rule updates)
- De-emphasizes storytelling and product narrative

**Why it matters:**
- Engineers skip narrative; they want requirements
- Ops team skips product vision; they want operational spec
- A 50-page beautiful PRD for stakeholders is worthless to the people who ship it

**How to apply:**
- Ruthlessly remove narrative. Replace with spec.
- Use tables, numbered lists, and explicit acceptance criteria
- Include every decision a builder would need (why this model, not that model)
- Leave a page for "narrative/storytelling" at the end if stakeholders need it

---

## Lesson 9: Differentiation Must Pass the "Why Can't Competitors Copy in 6 Months?" Test

**The principle:** Before claiming differentiation, ask directly: Could a competitor with $5M and a 6-person team copy this?

**What happened in this case:**
- Initial hypothesis: "Jurisdiction-specific compliance is our moat"
- Reality check: Any competitor could hire a legal analyst and build jurisdiction rules in 4–6 months
- Revised hypothesis: "Jurisdiction expertise + customer data lock-in is the moat" (requires accumulation of customer leases + learning from corrections)
- Action: Shifted emphasis from "we have jurisdiction rules" to "our system learns from every lease our customers upload"

**Why it matters:**
- Most claimed differentiators (features, UX, pricing) can be copied in 3–6 months
- Real differentiation is usually structural (data flywheel, regulatory moat, switching cost)
- Being honest about this early prevents wasting time on fragile advantages

**How to apply:**
- For each claimed differentiator, ask: "Could Anthropic copy this in 6 months?"
- If yes → find a different differentiator (it's not sustainable)
- If no → double down on why it's hard to copy (usually because it requires customers, time, or regulatory approval)

---

## Lesson 10: Confidence Scoring is Not an Afterthought

**The principle:** Every metric and assumption should be tagged with confidence level. >80% evidence = high. 30–50% = medium. <30% = requires validation.

**What happened in this case:**
- Assumptions ranked with confidence scores:
  - WTP ≥ $250/month: 85% confidence (8 interviews, direct WTP questions)
  - Extraction ≥95% F1: 70% confidence (industry benchmarks, not tested on our data)
  - CAC < $3K: 60% confidence (comparable products, not validated in market yet)
- Action: Planned validation activities based on confidence scores (highest priority for lowest confidence)

**Why it matters:**
- Without confidence scoring, all assumptions look equally risky
- With scoring, you prioritize what to test first (low-confidence Tier 1 assumptions)
- Stakeholders appreciate honest confidence assessments ("we're 85% confident" vs. pretending to 100% certainty)

**How to apply:**
- For each assumption, estimate: How much evidence do I have? (0–100%)
- Add confidence score to assumption matrix
- Prioritize validation based on: Risk (Tier 1/2/3) × Inverse-Confidence (test low-confidence assumptions first)

---

## What I'd Do Differently If Building Again

### 1. Deeper Competitive Threat Modeling

I underestimated how much time to spend on competitive threat. I would:
- Run 10 calls with CoStar customers (not 5)
- Do 3 calls with CoStar sales reps (backchannel) to understand their roadmap
- Analyze CoStar earnings calls (quarterly) for signals of mid-market focus
- Track job postings (LinkedIn) for hiring signals

**Why:** Competitive threat is Tier 1 assumption. Warrant more validation than I gave it.

### 2. Earlier GTM De-Risking

I would run GTM validation (Week 1–2) not Week 3:
- Paid campaigns to test messaging (does "avoid $40K penalties" resonate?)
- Landing page testing to understand value prop clarity
- This informs positioning before building MVP

**Why:** GTM is harder to change post-MVP. Better to learn messaging early.

### 3. More User Interviews (5→10 per Persona)

I would do 10 interviews per persona (not 5):
- 5 problem validation interviews (deep discovery)
- 5 solution validation interviews (testing specific features with mockups)

**Why:** With 30 total interviews, I'd have higher confidence on requirements and lower risk of missing a persona need.

### 4. Earlier Technical Spike (Week 2, Not Week 4)

I would run the ML/extraction spike in Week 2 (parallel with user research), not Week 4:
- Early tech validation removes risk fast
- If extraction is <85% F1, pivot product earlier

**Why:** Waiting until Week 4 wastes 2 weeks that could have been used on pivoting.

### 5. Regulatory Deep-Dive (Week 1–2)

I would spend 1 week researching jurisdiction regulations before user research:
- Call 5 lawyers in different states (CA, TX, NY, IL, FL)
- Understand ASC 842 compliance requirements thoroughly
- Research ESG disclosure requirements

**Why:** Understanding regulations deeply informs which users to interview and what questions to ask.

---

## Takeaways

1. **Validation before building is the best insurance policy.** It costs 10–20% of engineering budget but catches 70% of product risks.

2. **Assumptions ranking + go/no-go frameworks remove emotions from decisions.** Data-driven pivots and kills are more defensible than optimism-driven perseverance.

3. **Competitive advantage is usually not technical.** It's structural (business model, customer lock-in, regulatory positioning).

4. **Workarounds are more valuable than solutions.** Understanding how users work today is more useful than designing an ideal future state.

5. **Confidence scoring forces intellectual honesty.** Saying "we're 60% confident on this assumption" is more credible than claiming 100% certainty.

---

**Version:** 1.0 | **Status:** Ready for Next Iteration | **Last Updated:** July 2026
