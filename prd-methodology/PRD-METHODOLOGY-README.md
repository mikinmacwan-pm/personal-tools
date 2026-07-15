# How I Build PRDs: A Product Operating System for Rigorous Hypothesis Testing

**I'm rigorous about hypothesis testing before committing resources.**

This repository contains my complete product operating system for building PRDs — the methodology, case studies, templates, and evaluation tools I use to de-risk product decisions before engineering gets to work.

The core belief: **Move fast on validation, not building.** Spend 2–3 weeks on deep user research, competitive analysis, and market sizing to identify the kill-the-product assumptions. Test them. Then write a PRD that's defensible because every major decision has been stress-tested.

## What's Inside

- **[HOW-I-BUILD-PRDS.md](HOW-I-BUILD-PRDS.md)** — The methodology guide covering the 3-stage product operating system
- **[case-studies/compliance-lease-tool/](case-studies/compliance-lease-tool/)** — A detailed theoretical case study showing how this methodology applies to a real commercial real estate SaaS problem
- **[templates/](templates/)** — Reusable templates for PRDs, market sizing, and user research
- **[tools/](tools/)** — Evaluation frameworks and responsible AI assessment checklists

## Quick Start

1. **New to this approach?** Start with [HOW-I-BUILD-PRDS.md](HOW-I-BUILD-PRDS.md) (3,000+ words). It walks through the 3 stages with decision frameworks at each gate.

2. **Want to see it in action?** Read the [Compliance Lease Tool case study](case-studies/compliance-lease-tool/README.md). It shows exactly how I applied this methodology to a concept-stage product in commercial real estate.

3. **Ready to build your own PRD?** Use the [PRD Template](templates/PRD-TEMPLATE.md) and reference the [PRD Evaluator Checklist](tools/PRD-EVALUATOR-CHECKLIST.md) (26-item rubric) to stress-test your thinking before handoff.

4. **Need help planning validation?** The [User Research Guide](templates/USER-RESEARCH-GUIDE.md) includes a 45-minute interview script, JTBD extraction method, and synthesis approach for 3–5 interviews.

## The Core Framework

This product operating system has **5 stages**:

| Stage | Focus | Output | Decision |
|---|---|---|---|
| **Market Hypothesis** | Is the market real, big, and timed right? | TAM/SAM/SOM, competitive map, timing signals | Go/No-Go on market |
| **Validation** | Can we reach customers? Do they have the problem? Do they want it? | 3–5 validated personas, WTP signals, de-risked assumptions | Go/No-Go on problem |
| **Specification** | Is the solution buildable, defensible, and complete? | Full PRD with 0 blockers on evaluation rubric | Go/No-Go on PRD |
| **Execution** | Does the MVP ship with target metrics? | Working product hitting 95% F1 accuracy, <5% churn targets | Go/No-Go on MVP |
| **Scale** | Can we reach unit economics and repeat the GTM motion? | 9–13% segment penetration, CAC payback <12 months | Go/No-Go on GA |

## Why This Approach Works

1. **Assumption-first thinking.** Every product has 3–8 assumptions that kill it if wrong. This methodology ranks them by risk and tests Tier 1 assumptions in Week 1–2.

2. **Evaluation is a thinking tool.** The 26-item PRD evaluation rubric isn't a gate — it's a design tool. It finds 8–10 gaps pre-handoff that would otherwise cost 2–3 sprint cycles to fix.

3. **Differentiation must be defensible.** We explicitly check: "Why can't a competitor copy this in 6 months?" If the answer is weak, we pivot the positioning.

4. **Confidence scoring matters.** Not all assumptions have equal evidence. We track Tier 1 (kill-the-product), Tier 2 (major pivot), and Tier 3 (feature reprioritization) separately so stakeholders know what's proven vs. what's still risky.

## Key Principles

- **Move fast on validation, not building.** User research, market sizing, and competitive analysis should complete in 2–3 weeks. PRD writing in Week 3–4.
- **Prioritize de-risking over polish.** A rough PRD that kills 8 assumptions is worth more than a beautiful PRD that assumes them.
- **Rank assumptions by risk.** Not all unknowns are equal. Tier 1 kills the product. Tier 3 is nice-to-know. Test Tier 1 first.
- **Build go/no-go frameworks before building anything.** Define success criteria at each gate (MVP, Beta, GA) *before* engineering starts work.
- **User research is not optional.** 3–5 deep interviews per persona beat 50 survey responses for directional decisions. Do both for confidence.
- **Competitive threat modeling matters more than expected.** Spend as much time modeling "why can't competitors catch up" as you do on feature design.
- **Validate workarounds, not solutions.** What do users do *today* when your product doesn't exist? That's your real competition and your strongest differentiation vector.
- **Market sizing is art + science.** Never trust a single model. Top-down + bottom-up + triangulation. If they diverge >3×, you don't understand the market yet.
- **Write for execution, not beauty.** A PRD is read by engineers, not stakeholders. Prioritize clarity and specificity over narrative polish.
- **Confidence scoring is not an afterthought.** Every metric and assumption should be tagged with confidence level. >80% evidence = high confidence. 30–50% = medium. <30% = requires validation.

## Repository Structure

```
how-i-build-prds/
├── README.md (this file)
├── HOW-I-BUILD-PRDS.md (3,000+ word methodology guide)
├── CHANGELOG.md (version tracking)
├── .gitignore
├── case-studies/
│   └── compliance-lease-tool/
│       ├── README.md (case study overview)
│       ├── hypothesis.md (market sizing, TAM/SAM/SOM, competitive gap)
│       ├── validation/
│       │   ├── market-research-summary.md
│       │   └── user-research-summary.md
│       ├── assumptions-ranked.md (Tier 1/2/3 assumptions with evidence)
│       ├── go-no-go-framework.md (7 decision gates with triggers)
│       ├── validation-plan.md (Week 1–4 de-risking plan)
│       └── lessons-learned.md (10 meta-lessons from the PRD process)
├── templates/
│   ├── PRD-TEMPLATE.md (blank 14-section PRD ready to fill in)
│   ├── MARKET-SIZING-TEMPLATE.md (TAM/SAM/SOM framework)
│   └── USER-RESEARCH-GUIDE.md (45-min interview script + synthesis)
└── tools/
    ├── PRD-EVALUATOR-CHECKLIST.md (26-item rubric: blockers vs. improvements)
    └── RESPONSIBLE-AI-ASSESSMENT.md (4-pillar responsible AI framework)
```

## For Recruiters

This repository demonstrates three things about how I think about product:

1. **Rigor in hypothesis testing.** The Compliance Lease Tool case study shows how I validate assumptions before committing engineering resources — not just shipping fast, but thinking deeply about what could go wrong and de-risking it.

2. **Scalable PM methodology.** The frameworks and templates here are not one-off doc tools — they're a replicable operating system I've used across 3 different concept-stage products. That scales.

3. **Communication and judgment.** A 3,000+ word guide, detailed case study, and structured evaluation frameworks show I can explain complex product thinking to engineers, stakeholders, and new teams.

**For L6+ recruiting conversations:** This is what rigorous looks like — not speed, but judgment. The signal is not shipping, it's thinking.

## Using This Repository

- **For your own product:** Use the PRD Template + User Research Guide to validate before writing. Reference the PRD Evaluator Checklist when you're done. If you hit 0 blockers, you're ready.
- **For your team:** Adapt the evaluation rubric to your domain. Host the methodology guide as internal documentation.
- **For your org:** This system scales from pre-product validation through launch. Use it at Stage gates: Market Hypothesis → Validation → Specification → Execution → Scale.

## Feedback

This is a living document. If you find gaps, edge cases, or have suggestions for improving the methodology, open an issue or a PR.

## License

This work is shared as-is for educational and product planning purposes. Feel free to adapt, extend, and use the frameworks.

---

**Version:** 0.1.0 | **Last Updated:** July 2026 | **Author:** Mikin Macwan
