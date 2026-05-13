---
name: may-contain-lies
description: >
  Evaluates claims, studies, statistics, articles, or arguments using Alex Edmans'
  critical thinking framework from "May Contain Lies". Use this skill ONLY when
  the user explicitly asks for an Edmans-style evaluation, critical analysis, or
  asks to "run the ladder" on something, or asks whether a claim "may contain lies".
  Applies to news articles, academic studies, research papers, data claims,
  anecdotes used as evidence, expert opinions, and any argument where the user
  wants rigorous scrutiny. Do NOT trigger on casual conversation or factual questions
  the user is not asking to have evaluated.
---

# May Contain Lies — Edmans Critical Thinking Evaluator

This skill evaluates claims, studies, and arguments using the framework from Alex Edmans'
*May Contain Lies*. The core structure is:

1. **Twin Biases** — psychological blind spots before even looking at evidence
2. **Ladder of Misinference** — four rungs where reasoning typically breaks down
3. **Source Evaluation** — credibility and incentive checks
4. **Assessment** — a calibrated verdict (not a binary true/false)

---

## Output Format

Structure your response as follows. Use headers for each section. Within each section,
write in clear, conversational prose — avoid robotic checklists. Highlight only the
rungs or biases that are actually relevant; don't force every criterion if it doesn't
apply. End with an **Assessment** rather than a verdict unless the evidence is
overwhelmingly conclusive in one direction.

```
## Twin Biases
[Confirmation bias and black-and-white thinking analysis]

## Ladder of Misinference

### Rung 1 — Statement → Fact (Accuracy)
### Rung 2 — Fact → Data (Representativeness)
### Rung 3 — Data → Evidence (Causation)
### Rung 4 — Evidence → Proof (Universality)

## Source Credibility
[Only include if source information is available or inferable]

## Probing Questions
[2–3 questions the user should ask to independently verify]

## Assessment
[Calibrated conclusion — express as a degree of confidence or recommendation,
not a binary verdict, unless overwhelming proof warrants one]
```

---

## Step 1: Twin Biases

Before examining the substance, flag psychological blind spots.

### Confirmation Bias
Ask: *Do we want this conclusion to be true?* Look for:
- **Naïve acceptance** — believing a pleasing claim without scrutiny
- **Motivated scepticism** — rejecting an unpleasant claim and inventing dismissals
- **Biased search** — only seeking information that confirms the initial hunch

Note whose confirmation bias is at stake: the original author's, the user's, or the
public's. All three are worth flagging.

### Black-and-White Thinking
Ask: *Is the claim extreme or universal?* The world is usually:
- **Moderate** — something is good up to a point, or bad only beyond a threshold
- **Granular** — a category contains varied forms; generalisations mislead
- **Marbled** — good and bad are inextricably mixed; you cannot take one without the other

---

## Step 2: The Ladder of Misinference

Work up the ladder rung by rung. A claim fails the moment it can't survive a rung —
but note *where* and *how badly* it fails, not just *that* it fails.

### Rung 1 — Statement → Fact (Accuracy Check)
- Is the claim actually accurate and backed by publicly verifiable evidence?
- If a study or statistic is cited, does the source actually say what is claimed?
  Check for misquotation, cherry-picked figures, or conclusions not supported by
  the data presented.
- Does the underlying data measure what it claims to measure, or is it a proxy
  that drifts from the stated concept?
- Watch for: self-reported data, circular logic, missing the big picture, superlatives
  that invite obvious counterexamples.

### Rung 2 — Fact → Data (Representativeness Check)
- Is this an isolated anecdote or a systematic pattern? Flag the **narrative fallacy**
  if a single story is being used to imply a general truth.
- Is the sample representative, or is it selected (only successes, only extremes,
  only willing participants)?
- Is there a valid **control group**? Without one, there is no baseline.
- Is the result **statistically significant**, or could it be noise?

### Rung 3 — Data → Evidence (Causation Check)
- **Data mining**: Did researchers try many measures, inputs, or subgroups until
  something worked? Were continuous variables arbitrarily bucketed to manufacture
  a result?
- **Common causes (endogeneity)**: Is there a third unobserved factor driving both
  the input and the output? Flag especially if the input was a voluntary choice or
  correlates with other traits.
- **Reverse causation**: Could the supposed output have actually caused the input?
- **Consider the opposite test**: If the study found the inverse, what alternative
  explanations would you reach for? Do those same explanations apply here?
- *Data only becomes evidence through an RCT, a valid natural experiment, or a
  credible instrumental variable that rules out the alternatives.*

### Rung 4 — Evidence → Proof (Universality Check)
- Even internally valid evidence may lack **external validity**.
- What was the specific population, setting, and time period? Are there reasons the
  finding would not transfer to the user's context?
- **Restriction of range**: Was the study conducted on an extreme subset (elite
  athletes, crisis conditions, a single country) that makes the input irrelevant or
  unrepresentative for a general population?

---

## Step 3: Source Evaluation

Use when source information is available or can be inferred.

- Is the study published in a top peer-reviewed journal, or is it unvetted (preprint,
  press release, think-tank report)?
- Are there **systematic reviews or meta-analyses** on this topic, rather than a
  single paper?
- What are the author's **incentives and credentials**? Would they have published
  if they found the opposite result?
- Does the author acknowledge limitations and alternative explanations, or do they
  over-claim?

---

## Step 4: Assessment

Do **not** default to a binary true/false verdict. Express the conclusion as a
calibrated recommendation:

- What is the most defensible interpretation of the available evidence?
- At which rung does the claim most seriously break down?
- What would it take to strengthen the claim to the next rung?
- Is the claim *useful as a working hypothesis* even if not proven, or is it
  *too weak to act on*?

Only issue an unambiguous "this claim is unsupported" or "this claim is well-founded"
if the evidence is overwhelming in that direction.

---

## Step 5: Visual Summary

After completing the written assessment, produce a visual summary using the
`visualize:read_me` + `visualize:show_widget` tool pair. This is **mandatory** —
it turns the written analysis into an at-a-glance scorecard.

### What to render

Call `visualize:read_me` (modules: `["chart"]`) first, then call `show_widget`
with an HTML widget that contains **all three panels** below in a single card:

#### Panel A — Ladder Scorecard (left/top)
A vertical ladder with four rungs. For each rung assign one of three ratings:

| Rating | Meaning | Colour |
|--------|---------|--------|
| ✅ Pass | Claim survives this rung | Green (`#22c55e`) |
| ⚠️ Weak | Partial or uncertain | Amber (`#f59e0b`) |
| ❌ Fail | Claim breaks down here | Red (`#ef4444`) |

Draw the ladder as stacked horizontal bars or pill badges. Label each rung
with its short name (Accuracy / Representativeness / Causation / Universality).
Next to each label add the rating icon and a ≤ 8-word reason pulled from
the written analysis.

#### Panel B — Bias Flags (right/top)
Two indicator chips:
- **Confirmation Bias** — colour-coded green (low concern) / amber (possible) /
  red (strong concern) based on the analysis.
- **Black-and-White Thinking** — same three-colour scale.

Each chip shows the bias name and a one-line note.

#### Panel C — Confidence Meter (bottom, full-width)
A horizontal progress bar from 0 % ("Unsupported") to 100 % ("Well-founded").
Place the needle based on the written Assessment:
- Unsupported → 0–20 %
- Weak / speculative → 20–40 %
- Mixed / uncertain → 40–60 %
- Reasonably supported → 60–80 %
- Well-founded → 80–100 %

Label the bar with the percentage and a ≤ 6-word verdict string (e.g.
"Plausible hypothesis, causation unproven").

### Styling constraints
- Use CSS variables for colours where possible so the widget respects the
  user's theme.
- Keep the overall card width ≤ 700 px; no horizontal scroll.
- Background: transparent or `var(--background)`.
- Font: inherit (system sans-serif).
- No external dependencies — pure HTML/CSS/JS only.

### Loading messages
Use neutral, descriptive loading messages (this is an analytical/potentially
sensitive context): e.g. `["Building scorecard", "Rendering ladder"]`.

---

## Notes on Tone and Scope

- Be precise about *which* rung is at issue, rather than vague about "more research
  needed".
- When the user provides a short claim with no supporting study, do the best you can
  with Rungs 1–2 and flag explicitly that Rungs 3–4 cannot be assessed without
  the underlying methodology.
- Never manufacture criticism for its own sake. If a claim survives scrutiny at a
  given rung, say so clearly.
- The goal is calibration, not scepticism for its own sake.
