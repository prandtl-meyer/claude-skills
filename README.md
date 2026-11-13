# Claude Skills

A collection of custom skills for [Claude](https://claude.ai) by Daniel — built to extend Claude's capabilities for critical thinking, analysis, and professional work.

## What are Skills?

Skills are instruction sets that teach Claude a specific, repeatable workflow. Once installed, Claude consults the skill whenever the right context arises, producing more consistent and rigorous outputs than a standard prompt.

To install a skill: go to **Settings → Skills** in Claude and upload the `.skill` file.

---

## Skills in this repo

### 🔍 [may-contain-lies](./may-contain-lies/)

A critical thinking evaluator based on Alex Edmans' framework from *May Contain Lies*.

Given any claim, study, article, or argument, Claude will:
- Check for **confirmation bias** and **black-and-white thinking** before even looking at the evidence
- Walk the claim up the **Ladder of Misinference** — four rungs where reasoning typically breaks down (accuracy, representativeness, causation, universality)
- Evaluate **source credibility** and incentives
- Deliver a **calibrated assessment** — not a binary verdict, but a reasoned conclusion about what the evidence actually supports

**Trigger phrases:** "run the ladder on this", "evaluate this claim", "may contain lies check", "Edmans-style evaluation"

📥 [Download may-contain-lies.skill](./may-contain-lies/may-contain-lies.skill)

---

### 🧭 [decision-log](./decision-log/)

A two-phase decision journaling facilitator based on Ryder Carroll's Bullet Journal Decision Log framework, designed to separate decision quality from outcome luck ("resulting").

When making or reviewing significant choices, Claude will:
- Filter decisions by reversibility (**Hat, Haircut, or Tattoo**) so you only log choices that warrant structured reflection
- Guide you through **Phase 1 (Pre-Result)** before you act — challenging binary options, documenting rationale, evidence, opportunity costs, and a future-self regret check
- Walk you through **Phase 2 (Post-Result)** once outcomes are clear — auditing initial assumptions, running the counterfactual test, and critiquing your process rather than hindsight luck
- Generate a clean, two-page **Markdown Decision Log** ready for your notebook or knowledge base

**Trigger phrases:** "log a decision", "help me make a haircut decision", "start a decision log", "review a past decision"

📥 [Download decision-log.skill](./decision-log/decision-log.skill)

---

## Contributing

If you build on these skills or have suggestions, feel free to open an issue or PR.

## License

MIT — use freely, attribute if you share.
