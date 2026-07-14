# LinkedIn Post Skill

A Claude skill for creating career-advancing LinkedIn posts that signal seniority and attract recruiter attention for PM Leadership roles.

## Overview

This skill helps you validate whether an idea is worth posting before investing time writing. It uses a three-criteria validation gate:

1. **Depth of Insight** — Does it reveal something non-obvious?
2. **Seniority Signal** — Does it demonstrate you have solved hard problems at scale?
3. **Recruiter Relevance** — Would a PM hiring manager care?

If your idea passes, the skill develops it into a polished, ready-to-post package:
- Final post (max 400 words)
- Image generation instructions
- Hashtag suggestions
- Optional CTA framing

If it doesn't pass, you get actionable feedback on how to reframe it.

## When to Use

- You have a realization from work, a bootcamp, or a project and think "I should post about this"
- You want to validate an idea before spending time writing
- You want to filter out posts that are just "table-stakes PM knowledge"
- You are iterating on an idea you previously tried

## Example

**Input:** "I realized during agent testing that we had two different success metrics. One team optimized for accuracy, another for escalation rate. The agent optimized for one at the expense of the other."

**Validation:** ✓ Pass (depth, seniority signal, recruiter relevance)

**Output:**
- Polished 400-word post on how metrics shape behavior and why product teams must decide what success looks like
- Image instructions for a whiteboard diagram showing the divergence
- Hashtags: #AIProductManagement #Evals #ProductLeadership #LLM #AgenticAI

## Writing Style

Posts use a specific voice:
- Grounded in real experience
- Reveal non-obvious insights
- Show leadership and nuance
- No apostrophes (write contractions fully: "do not" not "don't")
- No negative/positive rhetorical structures
- Concrete examples before abstract principles

## Installation

Copy the `SKILL.md` file to your Claude skills directory:

```bash
cp SKILL.md ~/.claude/skills/linkedin-post/
```

Or for Cursor:
```bash
cp SKILL.md ~/.cursor/skills/linkedin-post/
```

## Usage

Invoke the skill by mentioning it:
- "Let me use the linkedin-post skill to validate this idea"
- "linkedin-post: I should post about how evals are product specs"
- "Use linkedin-post to check if this is worth publishing"

## Workflow

This skill is part of a semi-automated pipeline:

```
1. linkedin-post skill (validates + writes post)
   ↓
2. You review and approve
   ↓
3. Separate image-generation skill (creates diagram)
   ↓
4. You review and iterate on image
   ↓
5. Manually copy-paste to LinkedIn
```

## Author

Built for Mikin to create strategic AI product management thought leadership content.

## License

MIT
