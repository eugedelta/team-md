# TEAM.MD

A file convention for giving AI tools the team context they need to be genuinely useful.

---

## The problem

AI tools are stateless. Every session starts cold. The model knows nothing about who you are, how your team makes decisions, what's sensitive, or how you communicate — unless you re-explain it every time.

Most teams don't. So they get generic output, paste it into Slack, and wonder why it doesn't quite land.

TEAM.MD is the fix. It's a short markdown file committed to your repo that loads automatically at the start of every Claude Code session. It tells your AI tools what they'd need to know to work like a teammate, not a stranger.

---

## What goes in it

A TEAM.MD file has seven sections:

| Section | What it captures |
|---|---|
| **Who we are** | What the team owns and is responsible for |
| **Team members** | Names, roles, ownership, working styles |
| **How we make decisions** | Decision rights, escalation thresholds |
| **Communication norms** | Channels, tone, external review gates |
| **How we use AI** | Active use cases and conscious exclusions |
| **AI guardrails** | What never goes in a prompt; what needs sign-off |
| **Key workflows** | Repeating processes with AI integration points |

Each section is short. Every line should earn its place. The target is under 150 lines — past that, instruction compliance drops and the file starts getting ignored.

---

## How to use it

**Option 1 — Drop the template directly**

Copy `TEAM.MD` from this repo into the root of your team's repo. Fill it in. Commit it.

Then add two lines to your `CLAUDE.md`:

```
Read TEAM.MD at the start of every session for team context.
Apply the guardrails, communication norms, and decision rights described there.
```

That's it. Every Claude Code session in that repo will now load your team's context automatically.

**Option 2 — Run the workshop first**

If you want to build the file as a team — and surface the hidden assumptions about decision rights, AI use, and guardrails while you're at it — start with the Miro canvas.

→ **[Open the TEAM.MD Canvas in Miro](https://miro.com/app/board/uXjVHL5CuAQ/)**

The canvas takes 45–90 minutes with your full team. An AI workflow reads the stickies and writes the TEAM.MD file directly. You leave the session with a committed file, not a doc that sits in Notion.

A facilitator's guide is included in the canvas. No external help needed.

---

## Files in this repo

```
TEAM.MD              ← blank template, ready to fill in
TEAM.MD.example      ← populated example (People & Ops team)
docs/schema.md       ← field-by-field spec with constraints
```

---

## Keeping it current

A TEAM.MD that's six months out of date is worse than none — it actively misleads. A few practices that help:

- **Changes go through a PR.** Not because the process matters, but because the diff is useful. People can see what shifted and why.
- **Review quarterly**, or when the team changes significantly.
- **Test it after every update.** Open a Claude Code session and ask something team-specific. Does the response reflect the updated context? If not, the file isn't doing its job.

---

## The convention

TEAM.MD is a bet that naming matters. `.gitignore`, `README.md`, `CLAUDE.md` — conventions become standards when enough people use the same name. This repo is the stake in the ground.

If you use it, modify it, or build on it, the one ask is that you keep the filename and the core schema intact. That's what makes it interoperable — not any one team's implementation of it, but the shared expectation of what a TEAM.MD file contains.

Proposed changes to the schema are welcome via PR.

---

## About

TEAM.MD was developed by [Eugene Chung](https://deltawork.ai) at [Delta Work](https://deltawork.ai) — a consultancy focused on AI adoption and ways-of-working transformation.

If you want Delta Work to run the canvas workshop with your team, or to help build your AI ways-of-working practice more broadly: [get in touch](https://deltawork.ai/contact).

---

*Delta Work is based in Bondi, on the unceded lands of the Gadigal, Bidiagal, and Birrabirragal peoples. We acknowledge their continuing connection to land, waters, and community.*
