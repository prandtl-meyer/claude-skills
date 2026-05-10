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

## Contributing

If you build on these skills or have suggestions, feel free to open an issue or PR.

## License

MIT — use freely, attribute if you share.
