# How I Build PRDs: The 3-Stage Product Operating System

**A detailed methodology for rigorously validating product hypotheses before engineering commitment**

## Executive Summary

This guide walks through a 3-stage product operating system used to de-risk product decisions. The core principle: **move fast on validation, not building.** Spend 2–3 weeks on deep user research, competitive analysis, and market sizing to identify the assumptions that kill the product. Test them. Then write a PRD that's defensible because every major decision has been stress-tested.

The 3 stages are:

1. **Market Hypothesis** (Week 0–1): Is the market real, big, and timed right?
2. **Validation** (Week 1–4): Can we reach customers? Do they have the problem? Will they pay?
3. **Specification** (Week 3–4): Is the solution buildable, defensible, and complete?

Each stage has explicit go/no-go decision gates. Proceed only when you have evidence.

---

## Stage 1: Market Hypothesis (Week 0–1)

### What We're Testing

Before you call a single user, answer three questions:

1. **Is the market real and sized correctly?** TAM must be >$100M for venture-scale. SAM (your accessible segment) must be defensible.
2. **Is there a defensible competitive gap?** Why isn't someone already winning here? Can you copy fast and still win?
3. **Is the timing right?** What changed in the last 12–24 months that makes this solvable now?

### How to Do It

#### 2.1 Market Sizing (TAM / SAM / SOM)

**Never use a single model.** Use two approaches and triangulate:

**Top-Down:**
- Find an analyst report or IDC/Gartner estimate for the broadest relevant category
- Apply your segment's penetration assumption to arrive at SAM
- Example: "Legal tech market is $20B (IDC 2024). Contract review AI is ~5% of that market, so TAM = $1B. Our SAM is US mid-market (large enterprises doing <$500M in contract volume yearly), which is 12% of the US legal tech market, so SAM = $120M."

**Bottom-Up:**
- Count # of potential buyers in your target segment
- Multiply: × average deal size × number of contracts/seat/customer per year
- Example: "200,000 mid-market companies in the US × average 50 leases per company × $300/month = $3.6B TAM. But realistic SAM (those with >10 leases and $100K+ annual spend on compliance) is ~$200M."

**Triangulation Rule:** If both methods land within 2–3× of each other, report the range. If they diverge more, you don't understand the market yet — dig deeper before proceeding.

#### 2.2 Competitive Landscape

Avoid feature matrices. Instead, answer these questions:

**Who is winning and why?**
- Map competitors on two axes that actually differentiate: (cost vs. depth) or (ease-of-use vs. feature-richness)
- Identify the leader and name why they're winning (pricing, brand, workflow lock-in, data advantage)

**What's the incumbent's constraint?**
- Why can't the market leader move fast into your segment? Usually: (a) margin pressure, (b) organizational complexity, (c) legacy customer demands, (d) product architecture debt
- Example: "Costar owns the enterprise segment but is constrained by 50,000+ seat commitments. Mid-market can't afford that. They won't unbundle."

**Is there white space?**
- What jobs or segments are *nobody* addressing well? That's your entry point.
- Example: "Enterprise players focus on 500+ seat deals. DIY spreadsheet users are at the other extreme. Nobody owns 'mid-market, compliance-first, jurisdiction-aware.' That's the gap."

**Can we defend it?**
- Ask directly: *Why can't a well-funded competitor copy this in 6 months?* If the answer is weak, you don't have a defensible MOAT.
- Strong answers: proprietary data, regulatory moat (we got certified first), workflow lock-in, switching cost

#### 2.3 Timing Signals — Why Now?

List 3–5 timing drivers. These must be *external* changes in the market, not just "we have a good idea":

**Examples of strong timing signals:**
- Regulatory change (GDPR, ASC 842, FDA SaMD guidance) that creates new compliance burden
- Adoption curve (LLMs went from 2% to 58% in a category in 18 months — why?)
- Competitor exit (a well-funded player shut down or pivoted, leaving a gap)
- Technology shift (new foundation model capabilities made something previously impossible now feasible)
- Consolidation signal (incumbents are acquiring to fill a gap, signal there's a gap to fill)
- Customer behavior shift (search volume, social media discussion, or analyst report mentioning this as top 3 concern)

**Weak timing signals (avoid these):**
- "The market is ready" (no evidence)
- "Customers asked for this" (plural of anecdote is not data)
- "Now is a good time" (vague)

#### 2.4 Market Hypothesis Go/No-Go Gate

**Go criteria:**
- TAM > $500M (venture scale) with two convergent sizing models
- Defensible competitive white space OR clear MOAT (data, regulatory, workflow lock-in)
- 3+ external timing signals (regulatory, adoption, consolidation, or tech capability)

**No-Go triggers:**
- TAM < $100M or sizing models diverge >5×
- Incumbent can copy in <6 months with no switching cost
- No external timing justification (if it was a good idea 2 years ago, why now?)

**Proceed when:** You have high-confidence market sizing, a credible competitive gap, and an external timing rationale. If uncertain, spend 1–2 more days on research before moving to Stage 2.

---

## Stage 2: Validation (Week 1–4)

### What We're Testing

You've confirmed the market is real. Now test the *customer-specific* assumptions:

1. **Does this persona have the problem?** Not "do people in the market have it" — does *this specific buyer* and their team?
2. **How acute is the problem?** Can you quantify the cost (time, money, error rate) in a way that justifies 3+ months of effort?
3. **Would they actually change?** (Willingness to Pay = WTP). Don't ask "would you use this?" Ask "would you pay $X/month for this?"

### How to Do It

#### 3.1 User Research (3–5 Interviews per Persona)

**Recruitment Rule:** Recruit for *behavior*, not demographics.

- **For B2B:** Find people who actually do the job you're solving for. If building for lease administrators, recruit lease admins, not CFOs who might care about leases.
- **For discovery:** Do NOT recruit only happy customers. Include churned users, users who tried you and left, and non-adopters. They carry the strongest signal.

**Interview Structure (45 minutes total):**

| Section | Duration | Approach |
|---|---|---|
| Warm-up | 5 min | "Tell me about your role and how long you've been doing it." |
| Workflow | 15 min | "Walk me through the last time you did [the job they hire for]. What did you do?" Watch for workarounds. |
| Pain | 15 min | "When have you gotten this wrong? What happened?" Quantify the cost if possible. |
| Workarounds | 10 min | "How do you solve this today?" — get specific. They tell you exactly what to build by showing what they're trying. |
| Solution | 5 min | "If I told you we could [specific outcome], would you care?" Gauge interest but don't over-pitch. |

**Jobs-to-be-Done Extraction (Post-Interview):**

For each interview, extract 3 jobs:
- **Functional:** "Review leases for 90-day renewal notices"
- **Emotional:** "Stay in control so I don't get blindsided"
- **Social:** "Look proactive and organized to my team"

Most PMs stop at functional. The emotional and social jobs are where you find differentiation.

**Willingness to Pay (WTP) Signals:**

Ask **after** they understand the problem, not after a pitch:
- "How much do you currently spend on solving this?" (current solution cost)
- "If someone could solve 80% of this problem and save you [time/money], how much would that be worth to you monthly?" (don't anchor too low)
- Track range: "Would you pay $100/month? $300? $500?"

Van Westendorp Price Sensitivity Meter is a better tool if you can recruit 50+ targets.

#### 3.2 Competitive Threat Modeling

For each competitor, answer:

- **Why did their last 5 customers *not* choose you?** Call 3–5 customers of the leading competitor and ask.
- **What would it take for them to move?** Don't ask "are you satisfied?" Ask "if someone built [specific thing you're building], would you switch?"
- **What's their pricing trajectory?** Check pricing page history (Wayback Machine). Are they dropping price? (Sign of commoditization risk)
- **Who are they hiring?** Check their job postings. Look at the sales/engineering ratio. All sales hires = entering enterprise. All engineering = doubling down on product.

#### 3.3 Market Research Synthesis

By Week 3–4, consolidate:
- **3 validated personas** with specific pain points, WTP ranges, and jobs-to-be-done
- **Top 3 workarounds** that customers use today
- **WTP range** that 60%+ of users are willing to pay
- **Competitive threat model** — 3-5 sentence summary of "why we can win despite competition"
- **Ranked assumptions** — Tier 1 (kill-the-product if wrong), Tier 2 (major pivot), Tier 3 (feature reprioritization)

#### 3.4 Validation Go/No-Go Gate

**Go criteria:**
- 3–5 interviews per persona showing clear evidence of the problem (not just stated, but shown in behavior/workarounds)
- WTP signal: >60% of users willing to pay $X/month where X covers your CAC
- Current workaround is manual, time-consuming, or error-prone (giving you a clear value prop)
- Competitive threat model is credible (specific, grounded in customer research, not just "we're better")

**No-Go triggers:**
- Users don't actually do this work (it's an assumed pain, not a lived pain)
- WTP is <$50/month (too low to build profitably)
- Everyone is already on a solution they're happy with (low switching cost = hard to win)
- You can't articulate why you win vs. top 3 competitors

**Pivot criteria:** If you hit a no-go, don't kill the product yet. Check:
- **Pivot to different persona?** ("Mid-market admins don't care, but enterprise legal officers do — go there")
- **Pivot to different job?** ("They don't care about compliance, but they care about audit trails — lead with that")
- **Pivot to pricing model?** ("$300/month doesn't work, but $2K/quarter with volume discounts does")

**Proceed when:** You have clear evidence of customer pain from 3–5 deep interviews, a credible WTP signal (>60%), and a competitive story that holds up to scrutiny.

---

## Stage 3: Specification (Week 3–4)

### What We're Testing

You've validated the market and the customer problem. Now build a defensible spec:

1. **Is the solution buildable?** Can we solve this with available technology, or do we need to invent something new?
2. **Is it scoped correctly?** MVP feature set vs. future phases — can we ship something valuable in 4–8 weeks?
3. **Does it pass the evaluation rubric?** A 26-item checklist that finds gaps before engineering starts.

### How to Do It

#### 4.1 Write the PRD (Using the Template)

A full PRD has 12–14 sections. See templates/PRD-TEMPLATE.md for the blank version.

**Core sections:**

| Section | Purpose | Key Question |
|---|---|---|
| Executive Summary | Stakeholder alignment | "Can someone understand what we're building and why in 2 minutes?" |
| Problem Definition | Grounding in research | "What validated assumption is this solving?" |
| Solution Overview | Clear scoping | "What are we shipping vs. deferring?" |
| User Stories & Requirements | Engineering clarity | "Can an engineer read this and know what to build?" |
| Success Metrics | Testability | "How will we measure if this worked?" |
| Go/No-Go Criteria | Decision clarity | "At what point do we kill this if it's not working?" |
| Implementation Plan | Model selection | "Which AI model, why, and what's the tradeoff?" |
| Evaluation Plan | Quality assurance | "How do we test accuracy before shipping?" |
| Responsible AI | Risk mitigation | "What could go wrong with the AI, and how do we catch it?" |
| Risks & Mitigations | Completeness | "What 3 risks could derail this?" |
| Timeline | Reality check | "Is this timeline realistic?" |

#### 4.2 Use the PRD Evaluator Checklist (26 Items)

Before handoff to engineering, run your PRD through a 26-item rubric that checks for blockers vs. improvements:

**Blockers:** Gaps that block the PRD moving forward.
- Example: "No success metric defined" = blocker (you don't know what success looks like)
- Example: "No competitive differentiation explained" = blocker (why build if we can't defend?)

**Improvements:** Weak points that don't block progress but should be strengthened.
- Example: "Timeline is realistic but doesn't account for design iteration" = improvement (not blocking, but plan is optimistic)

**Evaluation sections:**
1. Problem Definition (8 items): specificity, personas, validation, impact, market sizing, timing, competitive gap, assumptions
2. Solution Definition (4 items): clarity, feature scope, out-of-scope, user stories
3. Requirements (3 items): prioritization, non-functional, MVP scope
4. Success & Metrics (3 items): success metrics, go/no-go gates, evaluation plan
5. Implementation (3 items): model selection criteria, alternatives, AI risk mitigation
6. Risks & Mitigations (2 items): risk identification, mitigation specificity
7. Timeline (2 items): dated milestones, dependencies

**Use the rubric as a thinking tool, not a gate.** It exists to find gaps early, not to reject PRDs. Iterate on the spec until you hit 0 blockers. Then ship with confidence.

#### 4.3 Model Selection & Responsible AI (for AI Products)

**Model Selection Criteria:**
- **Context window:** How much document can you fit in a single call? (Compare: GPT-4 = 128K, Claude = 200K, Llama-2 = 4K)
- **Latency:** API response time matters for user-facing features. (API < 3sec, local <100ms)
- **Cost:** Pricing per 1K tokens. (GPT-4 = $0.03 input / $0.06 output; Claude = $0.003 input / $0.015 output; open source = hosting cost)
- **Accuracy:** Benchmark on your specific task, not general benchmarks. (MMLU tells you nothing about lease extraction)

**Responsible AI Assessment (4 Pillars):**
1. **Accountability:** Audit trail, error logging, human override capability
2. **Transparency:** Confidence scoring, source attribution, explainability
3. **Fairness:** Bias testing across segments, performance floor, monitoring
4. **Reliability:** Hallucination testing, validation rules, safe failure modes

Pre-launch checklist:
- [ ] Honeypot test: 0 hallucinations on test set
- [ ] Accuracy by segment: ≥90% F1 across all user segments
- [ ] Confidence calibration: Model outputs match actual accuracy
- [ ] Responsible AI review: Sign-off from privacy, compliance, or ethics review

#### 4.4 Specification Go/No-Go Gate

**Go criteria:**
- PRD has 0 blockers on 26-item evaluation rubric
- Assumptions are ranked by risk and Tier 1 assumptions are testable in MVP
- Model selection is justified (compared to at least one alternative)
- Success metrics are quantified and measurable

**No-Go triggers:**
- >3 blockers on the evaluation rubric
- Key assumptions are untestable in MVP (you can't know if you're right for 12+ weeks)
- Feature scope looks like Phase 2, not MVP (trying to ship too much)
- No responsible AI assessment for an AI product

**Proceed when:** PRD hits 0 blockers, assumptions are ranked and testable, and you have explicit success metrics. You're ready to hand off to engineering.

---

## Principles That Make This Work

### 1. Move Fast on Validation, Not Building

- Target: User research (2 weeks) + competitive analysis (3 days) + market sizing (3 days) + PRD iteration (3 days) = 4 weeks total
- What you skip: Prototyping, design mockups, pitch decks (build these after validation if needed)
- Why: Building is the slow, expensive part. Validation is fast and cheap. Get evidence before you commit the expensive resources.

### 2. Evaluation is a Thinking Tool, Not a Gate

- The 26-item rubric finds gaps, it doesn't approve PRDs
- It's most useful at Week 3–4 when you draft the PRD. Run it, iterate, run it again.
- You'll find 8–10 items that are missing. That's not failure — that's discovery. Plug the gaps and ship.

### 3. Rank Assumptions by Risk

Not all unknowns are equal. Tier them:

| Tier | Definition | Example | Testing Timeline |
|---|---|---|---|
| **Tier 1 (Kill the product)** | If wrong, the product has no market | "Lease admins have budget for this" | Week 1–2 (must test before PRD) |
| **Tier 2 (Major pivot)** | If wrong, repositioning required | "Jurisdiction-specific compliance is table-stakes" | Week 1–3 (should test before PRD) |
| **Tier 3 (Feature reprioritization)** | If wrong, remove a feature or deprioritize | "Automated amendments are 90% accurate" | MVP launch criteria |

**Rule:** Test Tier 1 assumptions before writing the PRD. If any Tier 1 assumption fails, kill the project or pivot. Don't proceed to engineering.

### 4. Competitive Differentiation Must Pass the 6-Month Test

For every claimed differentiation, ask: *Why can't a competitor with $5M and an engineering team copy this in 6 months?*

- **Weak answers:** "Better UX" (can be copied in 12 weeks), "Lower price" (not a moat)
- **Strong answers:** "We fine-tuned a model on 50,000 proprietary leases and have 2+ year data advantage," "First mover in regulatory certification," "Deep integration with customer accounting systems creates switching cost"

If the answer is weak, adjust the positioning. Don't ship without a defensible MOAT.

### 5. User Research Must Include Frustration Interviews

The users most likely to churn are the most honest about what's missing in your value prop. Interview at least one person per persona who tried your competitor and didn't stick, or who uses a workaround instead of "the right tool."

### 6. Market Sizing Requires Two Methods + Triangulation

Never trust a single model. Single models are wrong by 10× more often than triangulated models.

- Get top-down from analyst reports
- Build bottom-up from customer count × spend
- If they converge within 2–3×, you have confidence. If they diverge more, dig deeper.

### 7. Go/No-Go Criteria Must Be Explicit Before Testing

Define success *before* you interview users or research competitors. Otherwise, you'll interpret results optimistically. Explicit criteria remove the bias.

**Example criteria:**
- "Go to Validation if TAM > $500M with two convergent models"
- "Go to Specification if >60% of users are willing to pay $300/month"
- "Go to Execution if PRD has 0 blockers on the 26-item rubric"

---

## Outputs at Each Stage

### After Stage 1 (Market Hypothesis)

- [ ] TAM / SAM / SOM (two methods, triangulated)
- [ ] Competitive landscape map with white-space identified
- [ ] 3–5 timing signals with sources
- [ ] Go/No-Go decision documented with rationale

### After Stage 2 (Validation)

- [ ] 3 validated personas with JTBD and pain points
- [ ] WTP data (minimum 3 price points tested with 60%+ willing to pay)
- [ ] Top 3 workarounds users employ today
- [ ] Competitive threat model (why we win)
- [ ] Tier 1/2/3 assumptions ranked with evidence gaps
- [ ] Go/No-Go decision documented

### After Stage 3 (Specification)

- [ ] Full PRD (12–14 sections)
- [ ] PRD evaluation rubric results (0 blockers)
- [ ] Model selection justification (for AI products)
- [ ] Responsible AI assessment (for AI products)
- [ ] Success metrics (quantified and measurable)
- [ ] Timeline and milestone dependencies
- [ ] Go/No-Go decision + readiness for engineering

---

## When to Iterate vs. When to Kill

**Iterate when:**
- A Tier 2 or 3 assumption fails (pivot positioning or deprioritize features)
- PRD evaluation finds 3–5 improvements (fixable in a few days)
- Market sizing models diverge but both are credible (average the range and proceed)

**Kill when:**
- A Tier 1 assumption fails and the pivot path isn't clear
- >50% of users won't pay enough to justify development
- A new competitor or regulation fundamentally changes the market

**Don't iterate forever.** Set a hard stop date: "If we haven't achieved validation go/no-go by Week 4, we kill this project and move to the next hypothesis." Sunk-cost bias will kill more products than good judgment.

---

## Common Mistakes

**Mistake 1: Skipping user research because "the idea is obvious."**
- Reality: ~70% of concept-stage product assumptions fail user validation. Obvious ideas often solve the wrong problem for the wrong persona.
- Fix: Interview at least 3 users before writing the PRD.

**Mistake 2: Running 50 survey responses instead of 5 deep interviews.**
- Reality: Surveys answer "how many" but not "why." For hypothesis formation, deep interviews are 5× more valuable.
- Fix: Start with 5 moderated interviews. Then validate with 100 survey responses if you need scale.

**Mistake 3: Confusing "users are excited" with "users will pay."**
- Reality: Excitement ≠ WTP. Someone excited about your product at $0/month might delete it at $10/month.
- Fix: Always test WTP separately. Use the Van Westendorp Price Sensitivity Meter or conjoint analysis.

**Mistake 4: Using only happy customers for validation.**
- Reality: Churn cohorts and users who tried-and-left are more honest about what's missing.
- Fix: Recruit 1–2 frustrated users per persona. They give you the real feature requirements.

**Mistake 5: Building the evaluation rubric after the PRD.**
- Reality: If you wait until the end, you'll have sunk time into fixing blockers that should have been caught early.
- Fix: Use the rubric as a checklist while you write. Iterate in real-time.

**Mistake 6: Defensible differentiation is "better" or "easier."**
- Reality: "Better" can be copied in 3 months. "Easier" can be copied in 6 weeks.
- Fix: Your differentiation must be: data-driven (flywheel), regulatory (moat), or structural (switching cost). Else iterate on positioning.

**Mistake 7: Proceeding to engineering before Tier 1 assumptions are tested.**
- Reality: You burn engineering resources on a product that might fail validation in Month 2. Kill it early instead.
- Fix: Test Tier 1 assumptions *before* you commit engineering capacity. If they fail, pivot or kill.

---

## Adapting This Methodology

**For pre-product (greenfield) ideas:**
Use all three stages. Start with market hypothesis to confirm you're in a real market.

**For adding a feature to an existing product:**
Skip market hypothesis (you know the market). Start at Validation with 3–5 user interviews on the specific feature. Then Specification.

**For AI products specifically:**
Add 1 week to the Validation stage for model benchmarking (Week 2–3). You need to know: *Can the AI solve this problem at the required accuracy?* This is a gate before you proceed to Specification.

**For highly regulated spaces (healthcare, finance, legal):**
Add compliance review to each stage. Market Hypothesis should include "Is this compliance-heavy enough to create regulatory moat?" Specification should include regulatory sign-off before engineering starts.

---

## Recommended Reading

**On hypotheses and validation:**
- Lean Product Playbook, Dan Olsen (framework for prioritizing assumptions)
- Inspired, Marty Cagan (stage-gate thinking for products)
- Mom Test, Rob Fitzpatrick (how to ask users the right questions)

**On market sizing:**
- Traction, Gabriel Weinberg (10 methods for market sizing)

**On JTBD:**
- Competing Against Luck, Clayton Christensen (foundational)

**On evaluation:**
- Inspired, Marty Cagan (evaluation as design tool, not gate)

---

**Version:** 1.0 | **Last Updated:** July 2026
