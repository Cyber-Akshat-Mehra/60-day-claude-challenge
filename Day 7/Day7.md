Prompt:- 

You are a Claude AI Expert, Productivity Consultant, and AI Workflow Architect.
Your goal is to recommend the best Claude model and effort settings for me based on my profile and daily tasks.
First ask me these questions:
1. What is your current situation?
(Student / Professional / Freelancer / Founder)
2. What are your primary activities?
(Examples: Coding, Content Creation, Learning, Research, Marketing, Resume Building, Career Preparation, Business Planning)
3. How often do you use Claude?
(Occasionally / Daily / Heavy User)
4. What type of outputs do you need most?
(Fast Answers / Learning Support / Coding Help / Deep Research / Business Strategy / Creative Work)
After collecting my answers:
Think step by step.
1. Analyze my profile.
2. Analyze my typical use cases.
3. Identify which Claude model fits me best.
4. Identify when I should use Haiku, Sonnet, and Opus.
5. Identify which effort setting I should use most often.
6. Recommend situations where I should switch to High or Max effort.
7. Suggest an optimal Claude workflow for my daily tasks.
Finally generate:
# My Claude Usage Strategy
## Recommended Primary Model
## Why This Model Fits Me
## When to Use Haiku
## When to Use Sonnet
## When to Use Opus
## Recommended Effort Level
### Low
### Standard
### High
### Max
## My Personalized Claude Workflow
Provide a table:
Task | Best Model | Best Effort | Reason
## Biggest Mistakes I Should Avoid
## Final Recommendation
If I could use only ONE model and ONE effort level for most of my work, what would you recommend and why?
Present the output in a clean, visual, beginner-friendly format.




Result:-
# My Claude Usage Strategy

**Your profile:** Student · Coding · Occasional use · Creative Work + Deep Research

---

## Recommended Primary Model
**Claude Sonnet 5** — your daily driver, with occasional trips to **Opus 4.8** for the hardest research or creative work.

## Why This Model Fits Me
- You're an occasional user, not running agentic pipelines all day — Sonnet 5 gives strong coding and reasoning without burning through usage limits fast.
- Your two big use cases (coding + creative/research) are exactly Sonnet's sweet spot: fast enough for iterative coding, capable enough for long creative pieces and research synthesis.
- Opus is worth reserving for the few moments a semester where you have a genuinely hard problem (a nasty bug, a big research synthesis, a thesis-level essay) — not a daily need for a student on occasional usage.

## When to Use Haiku
- Quick syntax questions, one-line fixes, formatting a citation, "what does this error mean"
- Fast lookups where you already know the answer is simple
- Not really necessary for you day-to-day given your usage is occasional — but good if you're ever rate-limited and need a lightweight fallback

## When to Use Sonnet
- **This should be ~80% of your work.** Writing/debugging code, drafting essays or stories, structuring a research paper, explaining concepts, brainstorming
- Great balance of quality and speed for coursework-paced tasks

## When to Use Opus
- A coding bug you've been stuck on for a while and Sonnet keeps missing the edge case
- Deep research synthesis across many sources for a major paper/thesis
- High-stakes creative work (a piece you'll actually submit/publish) where you want the best possible draft
- Anything where being wrong is costly (exam prep on a topic you can't verify yourself)

## Recommended Effort Level

### Low
Quick fact-checks, boilerplate code, simple formatting — anything low-stakes where speed matters more than depth.

### Standard *(High — this is the actual default)*
**Your everyday setting.** Coding help, essay drafts, explaining concepts, most homework — this is where you should live most of the time.

### High *(xhigh, for coding-specific work)*
When debugging something genuinely tricky or working through a multi-step coding assignment — Anthropic's own guidance is to reach for this tier specifically for coding/agentic work.

### Max
Reserve for: a research paper synthesis with many sources, a hard algorithm/proof, or a final polish pass on something you're submitting. It costs meaningfully more time and tokens, so don't leave it on by default.

---

## My Personalized Claude Workflow

| Task | Best Model | Best Effort | Reason |
|---|---|---|---|
| Debugging code / assignments | Sonnet 5 | High (xhigh) | Coding benefits from deeper reasoning; Sonnet handles it well |
| Quick syntax/error questions | Sonnet 5 or Haiku | Low | Fast, low-stakes, no need for deep thinking |
| Creative writing (stories, essays) | Sonnet 5 | Standard/High | Strong prose quality without Opus-level cost |
| Deep research (thesis, big paper) | Opus 4.8 | Max | Needs the most careful synthesis across sources |
| Brainstorming / outlining | Sonnet 5 | Standard | Fast iteration matters more than max depth |
| Final polish before submission | Opus 4.8 | High or Max | Higher stakes, worth the extra quality |

---

## Biggest Mistakes I Should Avoid
- **Leaving effort on Max by default** — it's slower and burns your usage limits faster; fine occasionally, wasteful as a habit.
- **Jumping straight to Opus for everyday coding** — Sonnet 5 at high/xhigh effort handles most coding tasks just as well, and lets you use Claude more before hitting limits.
- **Using Low effort on real research/writing tasks** — you'll get shallower, less reliable synthesis exactly when you need rigor most.
- **Forgetting to bump effort back down** after a hard problem — an accidental Max session left running can eat your usage for the day.

---

## Final Recommendation

**If you could only pick ONE model + ONE effort level:**
> **Claude Sonnet 5 at High (Standard/default) effort.**

It's the best all-around fit for a student who codes, writes, and researches occasionally — strong reasoning for coding and analysis, 
solid creative writing quality, and it won't burn through your usage the way running everything on Opus/Max would. 
Switch up to Opus + Max only for the handful of times a term you hit something genuinely hard.
