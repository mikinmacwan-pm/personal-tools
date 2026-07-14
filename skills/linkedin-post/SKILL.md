---
name: linkedin-post
description: Create career-advancing LinkedIn posts for PM roles. When you have an idea or observation from work, learning, or a project, use this skill to validate whether it's worth posting (depth of insight + seniority signal + recruiter relevance), then develop it into a polished, ready-to-approve post with image instructions and hashtags. Triggers on phrases like "I should post about this", "LinkedIn post for", "should I write about", or when you want to validate a post idea before investing time.
compatibility: null
---

# LinkedIn Post Writer for Career-Advancing Content

## Purpose

This skill helps you decide if an idea is post-worthy and, if it is, develops it into a polished LinkedIn post that signals your seniority and attracts recruiter attention for senior PM roles ($500K+).

## When to Use

Use this skill when:
- You have had a realization from work, a bootcamp, or a project and think "I should post about this"
- You want to validate an idea before spending time writing
- You want to filter out posts that are "table-stakes PM knowledge" — insights everyone already has
- You are iterating on an idea you previously tried

## How It Works

### Input

Provide a raw idea or observation. This can be:
- A quick thought: "I used 5 different skills in combination to build PRDs and realized something about workflow design"
- A partial reflection: "I was working on evals and noticed that two PMs looked at the same output and disagreed completely about whether it was good"
- A question: "Why do agents fail in production even when demos work?"
- An experience: "I spent 1000+ hours as a crisis counselor and it changed how I think about AI product design"

### Validation Gate: Is This Post-Worthy?

The skill evaluates your idea against three criteria:

**1. Depth of Insight**
Does the idea reveal something non-obvious or counterintuitive? Does it go beyond surface-level tips that "all PMs know"?

Bad: "Always define success criteria upfront" (table-stakes)
Good: "Evals are product specifications disguised as tests — and that is why two PMs can look at the same output and completely disagree" (reveals a structural insight)

**2. Seniority Signal**
Does this idea demonstrate that you have solved hard problems at scale? Does it show leadership, nuance, and real-world complexity?

Bad: "Here is my workflow for using 5 skills" (procedural, not seniority-signaling)
Good: "The hardest problem in AI products is not generating answers—it is defining what a good answer looks like. And only after you define that can your team build evals." (shows you have led difficult product decisions)

**3. Recruiter Relevance**
Would a hiring manager looking for a $500K+ PM role care about this insight? Does it position you as someone who solves hard problems in AI product, monetization, scaling, user trust, or go-to-market?

---

### Output: If Validated ✓

If your idea passes all three criteria, the skill produces:

**1. Polished Post (max 400 words)**
- Readable in 3-5 minutes
- Opens with the insight or question
- Grounded in real experience or concrete examples
- Includes specific details (metrics, customer outcomes, architectural decisions) where relevant
- Closes with a soft CTA or reflection question
- Ready for your approval before moving to image creation

**2. Image Instructions**
- A detailed but token-efficient prompt for a separate image generation skill
- Specifies: diagram type (whiteboard sketch, flowchart, comparison, etc.), key elements, visual hierarchy, style (hand-drawn, minimalist, technical)
- Designed to be clear enough that an image generation skill can execute without back-and-forth

**3. Hashtags (3-5)**
- Mix of domain-specific (#AIProductManagement, #LLM, #Evals) and recruiter-focused (#ProductManagement, #CareerGrowth)
- Chosen to surface your post to both peers and hiring managers

**4. CTA Framing (Optional)**
- Soft engagement hook: "What is your approach?" or "What would you add?" or "Have you run into this?"
- Positioned at the end, does not oversell

---

### Output: If Not Validated ✗

If your idea does not pass validation, the skill:

1. **Explains why** — Which criteria it failed (depth, seniority signal, recruiter relevance) and why
2. **Offers reframing suggestions** — How you might reshape the idea to make it post-worthy
3. **Does NOT reject outright** — Gives you a foothold to iterate

Example:
> "This idea is procedural (here is how to use 5 skills together) rather than insightful. To make it post-worthy, focus on the *realization* you had: Did combining these skills reveal something about how product teams should operate? Did it show you something about tool sprawl, or about knowledge silos? Once you identify the insight, the workflow becomes the evidence that supports it."

---

## Workflow

This skill is part of a larger semi-automated pipeline:

```
1. linkedin-post skill
   ↓ (outputs: post text + image instructions)
2. YOU review and approve
   ↓ (if approved, manually trigger next step)
3. image-generation skill (separate)
   ↓ (outputs: diagram/visual)
4. YOU review and iterate on image
   ↓ (when satisfied)
5. Manually copy-paste to LinkedIn
```

This skill handles step 1. It does not automatically invoke the image skill — you approve the text first.

---

## Writing Style & Tone

Posts should match your voice:

- **Grounded in real experience** — Cite actual projects, metrics, or examples
- **Reveal non-obvious insights** — Go beyond what most PMs know
- **Show leadership and nuance** — Demonstrate that you have navigated hard tradeoffs
- **Connect personal to professional** — Your crisis counseling experience informs your AI design thinking (when relevant)
- **Ask questions to engage** — Do not just declare answers; invite readers into your thinking
- **Concrete before abstract** — Lead with the story/example, then zoom out to the principle
- **No apostrophes** — Write contractions out (do not, is not, are not, will not)
- **No negative/positive pairs** — Avoid "This X is not Y. It is Z." structures. State directly instead.

Avoid:
- Generic tips
- Overly promotional language
- Surface-level observations
- Disconnected from real work

---

## Example

**Input:** "I realized something important during agent testing. We had two different success metrics for the same agent: one team cared about answer accuracy, another cared about escalation rate. The agent was optimizing for one at the expense of the other. Should I post about this?"

**Validation:** ✓ Depth (non-obvious insight about how metrics shape behavior), ✓ Seniority (shows you have led prioritization decisions), ✓ Recruiter (relevant to AI product leadership)

**Output Post:**
> "Shipping an agent is easy. Knowing if it actually worked is much harder.
>
> Two teams looked at the same agent output. One said, 'Looks good.' The other said, 'This should have escalated.'
>
> They were not disagreeing about quality. They were optimizing different specifications. And that is when I realized: the model does not decide what 'good' looks like. Your product team has to.
>
> If your eval only measures answer correctness, you build an agent that gets really good at answering—even when answering is the wrong move. But once you define what behavior you actually want (answer vs. clarify vs. escalate), your team can build evals that reward exactly that.
>
> That is why I think of evals as product specifications disguised as tests.
>
> What gates do you use before shipping an agent? What is the bar you have found actually works?"

**Image Instructions:**
> "Whiteboard-style diagram showing two PMs with thought bubbles: one saying 'Looks good' (checkmark), one saying 'Should escalate' (X). Between them, a box labeled 'SAME OUTPUT'. Below: three labeled boxes (Answer | Clarify | Escalate) with an arrow pointing to 'Eval Rewards Which Behavior?' Simple, hand-drawn style, light and clean."

**Hashtags:** #AIProductManagement #Evals #ProductLeadership #LLM #AgenticAI

---

## Notes

- Posts are designed to surface to both peers (domain-specific hashtags) and recruiters (career-focused hashtags)
- The validation gate is strict — ideas must signal seniority and be relevant to senior PM roles
- If an idea fails validation, the skill helps you iterate, not dismiss
- This is the text + strategy layer; image creation is a separate skill invoked after your approval

---

## Implementation: How to Execute This Skill

### Step 1: Parse the Input

Read carefully what the user has provided. It may be:
- A casual thought or observation
- A detailed context (article + perspective + key insights)
- A half-formed draft
- Multiple pieces of context

Extract the core insight(s), the supporting details, the audience context, and any explicit goals or tone guidance they have mentioned.

### Step 2: Validate Against Three Criteria

**Criterion 1: Depth of Insight — Does this reveal something non-obvious?**

Ask yourself:
- Is this something most senior PMs already think about, or does it surface a new angle?
- Does it go beyond surface-level tactics ("always X") to reveal WHY something matters?
- Does it connect dots that are not usually connected?
- Would a thoughtful person in this space read it and think "huh, I had not framed it that way"?

Red flags: procedural tips, generic advice, obvious observations, summaries without synthesis.

Green flags: second-order thinking, nuanced tradeoffs, structural insights, counterintuitive framings.

**Criterion 2: Seniority Signal — Does this demonstrate senior leadership experience?**

Ask yourself:
- Does this show the author has *solved* hard problems, not just *encountered* them?
- Does it demonstrate strategic thinking, not tactical execution?
- Does it show navigation of tradeoffs, stakeholder complexity, or organizational dynamics?
- Would a hiring manager for a $500K+ role see evidence of the depth they are looking for?

Red flags: how-to guides, tips and tricks, workflow descriptions, generic insights about product management.

Green flags: strategic decisions, organizational knowledge, competitive moat thinking, long-term vision, customer/business context.

**Criterion 3: Recruiter Relevance — Would a $500K+ PM hiring manager care?**

Ask yourself:
- Does this position the author as someone who thinks about hard, high-leverage problems?
- Are those problems relevant to AI product, enterprise strategy, scaling, competitive advantage, or go-to-market?
- Would this signal that they are the kind of person who sees second- and third-order effects?
- Would a tech executive, CTO, or board member find this useful?

Red flags: niche topics, low-leverage problems, engineering-focused insights, topics disconnected from business/strategy.

Green flags: enterprise strategy, competitive positioning, organizational learning, AI governance, business model questions.

### Step 3: Decision Point

**If all three pass:** Go to Step 4 (Write the Post)

**If any criterion fails:** Go to Step 5 (Provide Feedback)

### Step 4: Write the Post (if Validated ✓)

#### Post Structure

Open strong with the insight or a concrete situation that illustrates the insight. Do not start with context or preamble.

**Word count:** Max 400 words. Aim for 250-350 for readability.

**Structure:**
1. **Hook (1-2 sentences):** Lead with the insight or a concrete moment that crystallizes it. Make readers stop scrolling.
2. **Context (2-3 sentences):** Briefly ground the reader. Provide just enough context so the insight lands.
3. **Development (3-5 sentences):** Unpack the insight. Show why it matters. Use examples or reasoning.
4. **Implication or second-order thinking (2-3 sentences):** Show what this means for product leaders, enterprises, or the industry. Connect to strategic thinking.
5. **CTA or Reflection Question (1-2 sentences):** Invite engagement with a thoughtful question. Do not oversell.

#### Writing Rules

- **Use the author's voice:** Conversational, thoughtful, strategic, optimistic. Not sensational or hype-y.
- **Concrete before abstract:** Lead with the story/example, then zoom out to the principle.
- **Show, do not tell:** Use scenarios, examples, decisions to demonstrate seniority.
- **Avoid jargon where plain speech works:** "organizational knowledge" not "epistemological substrate."
- **Ask real questions:** Genuine engagement hooks, not rhetorical devices.
- **Ground in real work:** Reference actual decisions, tradeoffs, or customer interactions where relevant.
- **No apostrophes:** Write contractions fully (do not, is not, have been, will not)
- **No negative/positive pairs:** Avoid "This X is not Y. It is Z." Rewrite as direct statements.

#### Output Format: Post

```
[Polished LinkedIn post, max 400 words]
```

### Step 5: Generate Image Instructions (if Validated)

Create a concise but detailed prompt for a separate image generation skill. The prompt should:
- Specify diagram type (whiteboard sketch, 2x2 matrix, flowchart, comparison, timeline, etc.)
- Name the key elements to include
- Describe visual hierarchy and layout (what is emphasized, what is background)
- Specify style (hand-drawn, minimalist, technical, metaphorical, etc.)
- Be 2-3 sentences max, token-efficient but unambiguous

The image should:
- Reinforce the main insight visually
- Be readable at small size (LinkedIn thumbnail)
- Match the hand-drawn/whiteboard style
- Not be decorated fluff — every element should reinforce the core idea

#### Output Format: Image Instructions

```
[Detailed but concise prompt for image generation skill]
```

### Step 6: Generate Hashtags (if Validated)

Choose 3-5 hashtags. Mix strategy:
- 1-2 domain-specific (#AIProductManagement, #EnterpriseAI, #LLM, #Evals)
- 1-2 recruiter-focused (#ProductLeadership, #ProductStrategy, #CareerGrowth)
- Optional: 1 timing/context-specific if relevant

Hashtags should surface the post to both peers (who find it interesting) and recruiters (who are searching for the person).

#### Output Format: Hashtags

```
#Hashtag1 #Hashtag2 #Hashtag3 #Hashtag4 #Hashtag5
```

### Step 7: Provide Feedback (if Not Validated ✗)

If the idea does not pass, explain clearly and constructively:

1. **State which criterion(s) it failed:** Be specific. Is it lacking depth? Seniority signal? Recruiter relevance?

2. **Explain why:** Give concrete reasons. Reference the validation criteria above.

3. **Offer reframing suggestions:** Give the author a path forward. How could they reshape this idea to make it post-worthy? What angle should they dig into? What insight could they extract?

4. **Be encouraging, not dismissive:** The goal is to help them iterate, not discourage them.

#### Output Format: Feedback

```
## Not Ready for Posting

**Failed criteria:** [Depth / Seniority Signal / Recruiter Relevance]

**Why:** [Specific explanation]

**How to reframe:**
- [Suggestion 1]
- [Suggestion 2]
- [Suggestion 3]

Try again with one of these angles and see if it passes.
```

### Step 8: Final Output Format

**If Validated:**
```
## ✓ Post Validated & Ready

### LinkedIn Post
[polished post]

### Image Instructions
[detailed prompt]

### Hashtags
[hashtag list]

### Notes
[optional context on what makes this work]
```

**If Not Validated:**
```
## ✗ Needs More Development

[feedback section from Step 7]
```

---

## Key Principles for Execution

- **Be honest about validation.** If an idea is procedural or surface-level, say so. Do not polish mediocre ideas.
- **Err toward strict validation.** The point is to filter out posts that waste time. Better to reject a borderline idea than publish something that does not signal seniority.
- **Make feedback actionable.** When you reject an idea, give the author something to work with. They should be able to iterate.
- **Match the voice.** The post should sound like the author: thoughtful, strategic, grounded in real experience, opinionated but not sensational.
- **Max 400 words is a hard limit.** Trim ruthlessly. Every sentence should earn its space.
- **Image instructions should be concise.** Do not write a 500-token prompt to a separate skill. 2-3 sentences, clear and specific.
