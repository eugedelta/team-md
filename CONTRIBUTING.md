# Contributing to TEAM.MD

Thanks for using TEAM.MD. Here's how contributions work.

---

## What this repo is

TEAM.MD is a file convention — a shared expectation about what a file called `TEAM.MD` contains and how it's structured. The goal is for the name and schema to become standard, the way `.gitignore` or `CLAUDE.md` have become standard.

That means the schema is the stable part. Individual teams will implement it differently, and that's fine. What matters is that a `TEAM.MD` file anywhere contains the same seven sections in the same order, so that anyone — human or AI — knows what to expect.

---

## What's in scope for contributions

**Schema changes** — additions, removals, or modifications to the seven core sections. High bar. See below.

**Template improvements** — better placeholder text, clearer instructions, improved examples in `TEAM.MD.example`. Lower bar.

**Schema documentation** — clarifications, better examples, corrections to `docs/schema.md`. Always welcome.

**Bug fixes** — broken markdown, incorrect formatting, typos. Just open a PR.

---

## The bar for schema changes

The schema should only change when:

1. **A real team encountered a genuine gap.** Not a theoretical need — an actual case where the existing schema caused Claude to produce wrong or unhelpful output.
2. **The addition changes AI behaviour.** The test is: would removing this section cause Claude to make more mistakes? If the answer is "no, it's just good to have," it doesn't belong in the schema.
3. **The change doesn't break the 150-line budget.** Adding a section means the typical populated file stays under 150 lines. Past that, instruction compliance degrades.

Include a brief description of the real-world case in your PR. Schema change PRs without a concrete use case will be declined.

---

## What's out of scope

- Renaming the seven sections. Stability of names matters for tooling and convention.
- Adding team-specific content to the template. That belongs in your own fork.
- Changing the file format from markdown. The convention depends on it.
- Suggestions to make the file longer. The constraint is a feature.

---

## How to contribute

1. Fork the repo
2. Make your change
3. Open a PR with a clear description — what you changed and why
4. For schema changes: include the real-world case that motivated it

---

## Forking for your own use

You're encouraged to fork this repo and adapt TEAM.MD for your team's needs. The only ask: keep the filename `TEAM.MD` and the seven core sections intact. That's what makes it interoperable.

If your fork produces a useful variation — a TEAM.MD for engineering teams, for customer success teams, for agencies — open a PR or raise an issue. If there's enough demand, we may add domain-specific example files.

---

*Maintained by [Eugene Chung](https://deltawork.ai) · Delta Work*
