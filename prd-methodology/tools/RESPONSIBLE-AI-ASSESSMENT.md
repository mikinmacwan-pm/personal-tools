# Responsible AI Assessment Framework

**4-pillar assessment for AI products: Accountability, Transparency, Fairness, Reliability**

---

## How to Use This Framework

1. **Complete this assessment** before MVP launch (Week 12, target)
2. **Get buy-in** from engineering, product, and privacy/compliance teams
3. **Assign owners** for each pillar
4. **Track progress** — update weekly as you build
5. **Audit pre-launch** — ensure all items are checked before GA

---

## Pillar 1: Accountability

**Goal:** Ensure humans can audit, override, and correct AI decisions.

### 1.1 Audit Trail

**Requirement:** Log every AI decision (what went in, what came out, when, by whom).

**Implementation checklist:**
- [ ] All model outputs are logged with input + timestamp
- [ ] Logs include user ID or session ID (traceable)
- [ ] Logs are stored for ≥90 days (compliance horizon)
- [ ] Logs can be queried (for investigation) and exported (for audit)

**Example:** "User Sarah uploaded lease PDF at 2024-07-13 14:32 UTC. Model extracted 5 key fields. Extraction confidence: 94%. User approved output. Logged to database."

**Success criteria:** When an audit asks "what did the model do on this lease?", you can answer in 5 minutes.

---

### 1.2 Error Reporting

**Requirement:** Users can flag when AI makes a mistake, and you log it.

**Implementation checklist:**
- [ ] "This is wrong" button in UI for every AI output
- [ ] Users can submit corrected data (used for fine-tuning)
- [ ] Error reports are logged and searchable
- [ ] Error patterns are analyzed monthly (to identify model drift)

**Example:** User finds extraction error → clicks "Correct this" → inputs correct value → system logs: "Ground truth correction: predicted='2024-12-31', correct='2025-01-15'"

**Success criteria:** Track error rate by customer, feature, and model version.

---

### 1.3 Human Override

**Requirement:** Humans can override AI decisions when needed.

**Implementation checklist:**
- [ ] Every AI output has an "Override" or "Edit" option
- [ ] Override is logged (what was overridden, by whom, why if possible)
- [ ] Overrides are surfaced in dashboard (to identify systematic failures)
- [ ] System learns from overrides (if 10 users override the same field, retrain)

**Example:** System extracted renewal date as "2024-12-31" with 72% confidence. User sees warning, clicks "Edit," changes to "2025-01-15". System logs override and uses it to improve model.

**Success criteria:** <5% of outputs require override (high-confidence model). >70% of outputs are accepted as-is (users trust system).

---

## Pillar 2: Transparency

**Goal:** Make AI decisions explainable to users.

### 2.1 Confidence Scoring

**Requirement:** Model reports how confident it is in each decision.

**Implementation checklist:**
- [ ] Each output includes confidence score (0–100%)
- [ ] Confidence is calibrated (80% confidence means 80% of those predictions are correct)
- [ ] Low-confidence outputs are flagged for review
- [ ] Confidence is explainable to non-technical users ("High", "Medium", "Low")

**Example:** 
```
Extracted Renewal Date: 2024-12-31 [HIGH CONFIDENCE - 94%]
Renewal Notice Period: 90 days [MEDIUM CONFIDENCE - 71%]
ESG Clause Present: No [LOW CONFIDENCE - 42%]
```

**Success criteria:** Confidence scores pass calibration test (80% of "high confidence" predictions are actually correct; 50% of "low confidence" are correct).

---

### 2.2 Source Attribution

**Requirement:** Model shows which parts of the input led to the output.

**Implementation checklist:**
- [ ] For key extractions, highlight source text in original document
- [ ] Explain which page/section the extraction came from
- [ ] Show if extraction came from text vs. tables vs. images (if applicable)
- [ ] For judgments (e.g., "this lease is compliant"), show reasoning

**Example:**
```
Extracted Renewal Date: 2024-12-31
Source: Page 2, Section 3.2: "Lease shall renew automatically on December 31, 2024, unless either party..."
```

**Success criteria:** Users can trace every extraction back to source document.

---

### 2.3 Explainability

**Requirement:** Users understand why the model made a decision.

**Implementation checklist:**
- [ ] For each decision, provide 1–2 sentence explanation (non-technical)
- [ ] Link to documentation ("Why does our system classify this as 'non-compliant'?")
- [ ] For failures, show what the model was looking for vs. what it found
- [ ] Use analogies ("This is similar to case X, where Y happened")

**Example:**
```
Compliance Finding: MISSING ENVIRONMENTAL CLAUSE
Why: California leases (50+ years) must include environmental disclosure under CA Environmental Quality Act. This lease has no such clause.
What to do: Add Amendment A (template provided) or mark exemption.
Help: [Link to compliance guide]
```

**Success criteria:** 80%+ of users say "I understand why the system flagged this".

---

## Pillar 3: Fairness

**Goal:** Ensure AI doesn't systematically fail for certain segments.

### 3.1 Bias Assessment

**Requirement:** Test model performance across different segments (company size, geography, lease type).

**Implementation checklist:**
- [ ] Identify potentially sensitive attributes (company size, geography, industry, lease complexity)
- [ ] Hold out test sets stratified by these attributes
- [ ] Measure F1 / accuracy separately for each segment
- [ ] Flag any segment where accuracy drops >10% vs. overall
- [ ] Document findings and mitigation strategies

**Example:**
```
Extraction Accuracy by Segment:
- Small companies (10–50 leases): 91% F1 (vs. 95% overall) [Acceptable]
- Large companies (500+ leases): 94% F1 [Good]
- California leases: 89% F1 [FLAG: Investigate]
- Texas leases: 96% F1 [Good]
- Older leases (>10 years): 85% F1 [FLAG: Complex formatting]
```

**Success criteria:** No segment has accuracy >10% below average. Flag and mitigate outliers.

---

### 3.2 Performance Floor

**Requirement:** Define minimum acceptable accuracy for each segment.

**Implementation checklist:**
- [ ] For each segment, define minimum F1 (e.g., "CA leases must be ≥90% F1")
- [ ] Pre-launch: measure against floor; if below, don't launch for that segment
- [ ] Post-launch: monitor monthly and alert if segment drops below floor
- [ ] When launching to new segment, measure against floor before opening access

**Example:**
```
Minimum Performance Floor by Segment:
- All company sizes: F1 ≥ 90%
- All U.S. geographies: F1 ≥ 88%
- Older leases (>20 years): F1 ≥ 82% (allows for complexity)
```

**Success criteria:** All segments in production meet their performance floor.

---

### 3.3 Ongoing Monitoring

**Requirement:** Track fairness metrics monthly post-launch.

**Implementation checklist:**
- [ ] Dashboard showing accuracy by segment (updated weekly)
- [ ] Alert if any segment drops >5% below baseline
- [ ] Quarterly fairness review (analyze root causes of any drops)
- [ ] Update model or processes if systematic bias is detected

**Example:** Dashboard shows CA lease extraction dropped from 92% to 87% in July. Investigation reveals: new lease format (2024 standard) has different compliance clause placement. Action: retrain on 2024 leases.

**Success criteria:** No segment systematically underperforms. Fairness issues caught within 1 week of drift.

---

## Pillar 4: Reliability

**Goal:** Prevent hallucinations and ensure safe failure modes.

### 4.1 Hallucination Testing

**Requirement:** Test that model doesn't invent information that isn't in the input.

**Implementation checklist:**
- [ ] Honeypot test: Feed model leases missing critical fields (e.g., no renewal date)
  - [ ] Model should output "Not found" or low confidence, NOT fabricate a date
  - [ ] Target: 0 hallucinations on honeypot test
- [ ] Adversarial test: Intentionally misleading input (e.g., "This lease is NOT compliant")
  - [ ] Model should not confuse negations
  - [ ] Target: <1% hallucination rate on adversarial inputs
- [ ] Real-world test: 100 random leases from beta users
  - [ ] Manual review of extractions to catch false positives
  - [ ] Target: 0 hallucinations on random sample

**Example honeypot:**
```
Input: [Lease PDF with renewal date DELETED]
Model Output: "Renewal Date: NOT FOUND [confidence 3%]" ✅
Model Output: "Renewal Date: 2025-12-31" ❌ [Hallucination!]
```

**Success criteria:** 0 hallucinations on honeypot. <0.5% on production.

---

### 4.2 Validation Rules

**Requirement:** Hard constraints to prevent invalid outputs.

**Implementation checklist:**
- [ ] Date validation: Extracted dates must be realistic (2000–2050)
- [ ] Field validation: Required fields must be filled (e.g., renewal date can't be "TBD")
- [ ] Semantic validation: Logic checks (end date > start date, notice period < lease term)
- [ ] Format validation: Dates are ISO 8601, numbers are numeric, etc.

**Example:**
```
Validation Rule: Renewal Date must be:
- ISO 8601 format (YYYY-MM-DD)
- Between lease start and 10 years after lease end
- Not in the past
If extraction fails validation, output "Extraction failed; manual review required"
```

**Success criteria:** 100% of outputs pass validation. Invalid outputs are rejected with clear error message.

---

### 4.3 Safe Failure Modes

**Requirement:** Define what happens when AI can't decide.

**Implementation checklist:**
- [ ] If confidence <50%: Mark as "Needs Review" (don't auto-accept)
- [ ] If validation fails: Raise alert to user (don't silently fail)
- [ ] If extraction fails: Show original document and ask for manual entry
- [ ] If system error: Graceful degradation (show partial results, not crash)

**Example:**
```
Scenario: Model confidence for "Renewal Date" is 32%
Action: Don't auto-populate. Show user: "We couldn't extract renewal date. Please enter manually."
Don't: Silently skip the field or make a guess.
```

**Success criteria:** System never silently fails. Users always know when they need to take action.

---

## Pre-Launch Checklist

**Complete all of these before shipping to production:**

### Week 10 (2 weeks pre-launch)

- [ ] **Accountability:**
  - [ ] Audit trail is logging all decisions
  - [ ] Error reporting UI is built and tested
  - [ ] Override mechanism is working

- [ ] **Transparency:**
  - [ ] Confidence scores are calibrated (tested on holdout set)
  - [ ] Source attribution is working (documents highlight source text)
  - [ ] Explainability copy is written (non-technical explanations)

- [ ] **Fairness:**
  - [ ] Bias assessment completed for all planned segments
  - [ ] Performance floor defined for each segment
  - [ ] All segments meet their floor on test set

- [ ] **Reliability:**
  - [ ] Honeypot test run: 0 hallucinations ✅
  - [ ] Adversarial test run: <1% hallucination rate ✅
  - [ ] Validation rules deployed and tested
  - [ ] Safe failure modes documented

### Week 11 (1 week pre-launch)

- [ ] All guardrails deployed to staging
- [ ] Integration test with end-to-end flow
- [ ] Privacy/compliance review sign-off
- [ ] Legal/ethics review (if required)

### Week 12 (Launch day)

- [ ] Pre-launch monitoring dashboard is live
- [ ] Alerting thresholds are set
- [ ] Responsible AI review meeting (sign-off from all owners)
- [ ] Launch with limited cohort (50–100 users)

### Post-Launch (Week 14+)

- [ ] Weekly fairness review (check bias metrics)
- [ ] Monthly Responsible AI review (check all 4 pillars)
- [ ] Quarterly audit (independent review of audit trail, error logs, overrides)

---

## Responsible AI Review Sign-Off

**Owners:** Product, Engineering, Privacy/Compliance (and Ethics if available)

**Before launching, this statement must be true:**

> "We have assessed this AI product against the Responsible AI framework (Accountability, Transparency, Fairness, Reliability). We have passed honeypot testing for hallucinations. We have validated performance across customer segments. We have implemented human oversight and override mechanisms. We are confident this product can launch to 50–100 beta users with ongoing monitoring."

**Signature:**
- [ ] Product Owner: __________ Date: __________
- [ ] Engineering Lead: __________ Date: __________
- [ ] Privacy/Compliance: __________ Date: __________
- [ ] (Ethics, if applicable): __________ Date: __________

---

## Post-Launch Monitoring Dashboard

**Track these metrics weekly:**

| Metric | Target | Alert Threshold | Current |
|---|---|---|---|
| Overall F1 Accuracy | ≥95% | <92% | _ |
| Hallucination Rate | <0.1% | >0.5% | _ |
| Fairness (worst segment) | Within 10% of average | >15% gap | _ |
| Mean Confidence Score Calibration | 1:1 (high conf = high accuracy) | >10% miscalibration | _ |
| % Outputs Requiring Override | 5–10% | >15% | _ |
| % Errors Caught by Validation | 100% | <95% | _ |
| User Satisfaction (NPS on AI quality) | ≥40 | <30 | _ |

---

**Version:** 1.0 | **Last Updated:** [Date]
