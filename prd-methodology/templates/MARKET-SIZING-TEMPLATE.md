# Market Sizing Template — TAM / SAM / SOM

**Use this template to calculate market size for your product using two independent methods and triangulate**

---

## Method 1: Top-Down Market Sizing

### Step 1: Start with a Published Market Report

Find an analyst report (Gartner, IDC, Forrester, CB Insights) that covers a broader category that includes your product.

| Source | Category | Market Size | Year | Link |
|---|---|---|---|---|
| [Analyst] | [Category: e.g., "Commercial Real Estate Software"] | $[X]B | 2024 | [URL] |

**Example:**
- IDC says "Commercial Real Estate Software Market = $30B globally (2024)"
- Your product is "Lease Accounting Software" which is ~3–5% of CRE software
- So TAM = $30B × 3.5% = $1.05B

### Step 2: Apply Your Segment Assumptions

Narrow from the global market to your serviceable market by applying realistic assumptions about geography, company size, use case, etc.

| Factor | Assumption | Rationale | Impact |
|---|---|---|---|
| **Geography** | US = 55% of global | Industry data shows NA concentration | ×0.55 |
| **Company Size** | Mid-market (50–500 units) = 60% of market | Enterprise is smaller segment | ×0.60 |
| **Regulatory Urgency** | Compliance-driven = 40% premium | ASC 842 added new compliance burden | ×1.40 |

**Calculation:**
- Global TAM: $1.05B (from analyst report)
- × Geography (55%): $577M
- × Company Size (60%): $346M
- × Regulatory Premium (140%): $484M
- **Top-Down TAM = $400M–$550M**

---

## Method 2: Bottom-Up Market Sizing

### Step 1: Count Potential Buyers

Estimate how many companies in your target segment could be customers.

| Segment | Total # in Market | % with Problem | # Addressable |
|---|---|---|---|
| [Company type 1] | [X] | [Y%] | [X × Y%] |
| [Company type 2] | [X] | [Y%] | [X × Y%] |
| **Total** | | | [Sum] |

**Example:**
- Mid-market companies in US: 200,000
- % with commercial leases: 65% = 130,000
- % currently underserved (not using adequate solution): 70% = 91,000
- **Addressable Market = 91,000 companies**

### Step 2: Estimate Willingness-to-Pay (WTP)

What would your average customer pay annually for this solution?

**Method A: Survey-Based WTP**
- Run Van Westendorp Price Sensitivity Meter with 50+ target customers
- Ask: At what price is this too cheap? Too expensive? Bargain? Getting pricey?
- Find the price point where maximum % would buy

**Method B: Comparable Product WTP**
- Research similar products' pricing
- Adjust for your positioning (premium vs. budget)

**Method C: Cost of Problem × ROI**
- How much does the problem cost customers per year? (time, money, errors)
- Customers typically pay 20–30% of problem cost to solve it
- Example: If problem costs $200K/year, WTP is $40K–$60K/year

| Approach | WTP Result | Confidence |
|---|---|---|
| Survey | $[X]/month | High |
| Comps | $[X]/month | Medium |
| Problem Cost | $[X]/month | Medium |
| **Average** | **$[X]/month = $[X]/year** | **Medium-High** |

**Example:**
- Van Westendorp: $300/month peak
- Comparable (AppFolio): $250–$400/month
- Cost of missing a deadline: $40K, so 25% = $10K/year = $833/month
- Average conservative: $300/month = $3,600/year

### Step 3: Calculate Bottom-Up TAM

**TAM = Addressable Customers × Annual Spend**

- 91,000 companies × $3,600/year = **$328M**

**Confidence check:**
- Does this make sense? At 91,000 customers, annual spend of $3,600 = $328M
- Is this realistic? Yes, mid-market CRE software typically $200–$500/month

---

## Method 3: Triangulation

### Compare the Two Methods

| Method | TAM Range | Midpoint |
|---|---|---|
| **Top-Down** | $400M–$550M | $475M |
| **Bottom-Up** | $280M–$400M | $340M |

**Divergence:** 1.4× (within acceptable range of 2–3×)

**Converged TAM:** $340M–$550M (midpoint: **$445M**)

**Confidence Level:** Medium-High (both methods align; independent reasoning paths)

### If Methods Diverge >3×

**Investigate:**
1. Are you segmenting the market differently? (One model includes enterprise, other doesn't)
2. Are WTP assumptions different? (One assumes $500/month, other assumes $150/month)
3. Is the addressable market size wrong? (One model assumed 50% adoption of addressable, other assumed 20%)

**Resolution:**
- Dig into the gap; don't average until you understand why they diverge
- If still unclear, do primary research (customer surveys, competitive pricing analysis)

---

## SAM — Serviceable Addressable Market

**SAM** is the subset of TAM you can realistically reach given your distribution, positioning, and go-to-market approach.

### Method: Apply Realistic Constraints

Start with TAM, then apply constraints:

| Constraint | TAM Segment | % Addressable | Remaining |
|---|---|---|---|
| **TAM** | $445M | 100% | $445M |
| **Geography** | US only | 55% | $245M |
| **Company Size** | Mid-market (50–500 leases) | 60% | $147M |
| **Maturity** | Using inadequate solutions (not CoStar, not best-in-class) | 70% | $103M |
| **Budget Availability** | Can afford $250–$500/month | 80% | $82M |
| **SAM** | | | **$80M–$150M** |

**Rationale:**
- You're not going after enterprise (different GTM)
- You're not going after DIY (different positioning)
- You're focusing on mid-market with spreadsheets or outdated systems
- You need customers who can afford the price point

---

## SOM — Serviceable Obtainable Market (Year 1–3 Projection)

**SOM** is what you actually capture by Year 3 given realistic growth rates, churn, and market education.

### Build Your 3-Year Customer & Revenue Model

| Year | Customers | CAC | ARPU | Revenue | Notes |
|---|---|---|---|---|---|
| **Y1** | [X–Y] | $[X] | $[X]/mo | $[X]M | Founder-led sales, early adopters |
| **Y2** | [X–Y] | $[X] | $[X]/mo | $[X]M | 10 sales reps, word-of-mouth |
| **Y3** | [X–Y] | $[X] | $[X]/mo | $[X]M | Market leadership, 20 sales reps |

**Example for Compliance Lease Tool:**

| Year | Customers | CAC | ARPU | Revenue | Notes |
|---|---|---|---|---|---|
| **Y1** | 200–300 | $500–$1K | $300/mo | $7.2M–$10.8M | Founders' network + early adopters |
| **Y2** | 1,500–2,000 | $2K–$3K | $350/mo | $63M–$84M | Self-serve activation + 10 sales reps |
| **Y3** | 5,500–6,700 | $3K–$4K | $400/mo | $264M–$320M | Market saturation in addressable segment |

### Calculate Market Penetration

- Y3 customers: 5,500–6,700
- Addressable market: 91,000
- **Penetration:** 6–7.4%

**Is this realistic?**
- <5% penetration = conservative (most markets get 5–15%)
- 10%+ penetration = aggressive (requires market dominance)
- 6–7% = realistic for strong execution

### SOM = Revenue at Year 3

**SOM = $264M–$320M in cumulative revenue by Year 3**

Or more conservatively: **$10M–$25M in annual revenue run-rate by Year 3** (depending on how you count)

---

## Key Assumptions to State Explicitly

1. **Customer Count Assumptions**
   - [ ] How many customers do you expect to acquire per year?
   - [ ] What % come from founder-led vs. self-serve?
   - [ ] What % come from paid vs. word-of-mouth?

2. **Churn Assumptions**
   - [ ] What % of customers do you expect to churn monthly? (industry average for mid-market SaaS: 3–5%)
   - [ ] Does churn vary by customer segment?

3. **ARPU Growth Assumptions**
   - [ ] Will customers expand to higher-priced tiers?
   - [ ] Will you add usage-based pricing?
   - [ ] How much will ARPU increase per year?

4. **Competitive Assumptions**
   - [ ] Will competitors enter and compress TAM?
   - [ ] Will switching cost increase over time (customer lock-in)?

5. **Market Growth Assumptions**
   - [ ] Is the market growing, stable, or shrinking?
   - [ ] Will regulatory changes expand TAM? (e.g., ASC 842 expanding compliance software TAM)

---

## Sanity Checks

### Market Size Check

- **Is TAM > $100M?** (venture scale) → Yes if TAM is $400M–$550M ✅
- **Is SAM > $50M?** (sustainable segment) → Yes if SAM is $80M–$150M ✅
- **Is SOM achievable?** (7% penetration is realistic) → Yes if Year 3 = 5,500 customers ✅

### Growth Rate Check

- **Year 1 to Year 2:** 200→1,500 customers (7.5× growth)
  - Is this realistic? For founder-led to sales-assisted transition, yes
- **Year 2 to Year 3:** 1,500→5,500 customers (3.7× growth)
  - Is this realistic? For market education phase, yes (slower than Y1–Y2)

### Unit Economics Check

- **CAC < LTV?** 
  - CAC (Y1): $500–$1K
  - LTV (assuming 3-year retention, churn <5%): $300 × 36 = $10,800
  - Ratio: CAC/LTV = 5–10% ✅
- **Revenue per customer covers CAC?**
  - ARPU: $300/month = $3,600/year
  - CAC: $2K–$3K
  - Payback period: 8–10 months ✅

---

## Common Mistakes to Avoid

1. **Using only top-down (analyst reports).** Reports are often high-level and don't account for your specific segment. Always triangulate.

2. **Over-optimistic growth rates.** "We'll get 10% penetration in Year 3" requires sustained execution and favorable market conditions. Be conservative (5–7%).

3. **Forgetting to account for churn.** If you acquire 1,000 customers in Year 1 but lose 20% to churn in Year 2, you don't have 1,000 in Year 2.

4. **Ignoring willingness-to-pay validation.** Survey 50+ customers on price before committing to $500/month pricing.

5. **Conflating TAM with addressable market.** TAM is global/total. SAM is what you can reach. SOM is what you'll actually get. Don't confuse them.

6. **Assuming competitors won't move fast.** Always build in competitive threat assumptions (market contraction if incumbents enter).

---

## Final Output

**When complete, your market sizing should include:**

- [ ] TAM (two methods, converged)
- [ ] SAM (explicit constraints applied)
- [ ] SOM (3-year revenue projection with assumptions)
- [ ] Sanity checks (unit economics, growth rates, penetration)
- [ ] Confidence level (high/medium/low) with reasoning

---

**Version:** 1.0 | **Last Updated:** [Date]
