# TEAM.MD schema

This document defines what each section of a TEAM.MD file is for, what it should contain, and what the constraints are. Use it as the reference when filling in the template or proposing changes to the schema.

---

## File-level constraints

- **Maximum 150 lines.** AI instruction compliance degrades past this point. If your file is longer, cut it.
- **Every line should earn its place.** Ask: would removing this line cause the AI to make a mistake? If not, cut it.
- **Machine-readable first.** TEAM.MD is written for an AI to consume, not for humans to read. Plain declarative statements. No aspirational language.
- **Committed to repo root.** The file must live at the root of the repo alongside `CLAUDE.md` to be loaded automatically by Claude Code.

---

## Header

```
# TEAM.MD
> Team context for AI tools. Read this before responding to any request from a member of this team.
> Last updated: [YYYY-MM-DD] · Owner: [name]
```

**Last updated:** date of the last substantive change. Helps identify staleness.
**Owner:** the person responsible for keeping the file accurate. Should be the team lead or a nominated deputy. One person — not "the team."

---

## Section 01 — Who we are

**Purpose:** Orients the AI to the team's function and scope. Prevents the AI from making assumptions about what the team does or doesn't own.

**Format:** 2–3 sentences of plain prose.

**What to include:**
- What the team owns (not what it aspires to)
- What outcomes it's responsible for
- Approximate headcount if relevant to calibrating output

**What to avoid:**
- Mission statements or vision language
- Org chart positioning ("we report to the CXO")
- Anything that would be true of every team ("we collaborate and communicate")

**Good example:**
> We're the People & Ops team at Acme Co. We own the employee lifecycle (hiring to offboarding), internal communications, and organisational effectiveness for ~200 staff.

**Bad example:**
> We are a high-performing team dedicated to delivering exceptional people outcomes and driving organisational excellence.

---

## Section 02 — Team members

**Purpose:** Tells the AI who the humans are, what each person owns, and how to calibrate outputs for them. This is what lets Claude write "a summary for Sarah" without being told who Sarah is.

**Format:** Markdown table with four columns.

| Name | Role | What they own | How they work best |

**Column constraints:**

- **Name:** use the name people actually go by in day-to-day work
- **Role:** job title or functional descriptor — whichever is more meaningful in context
- **What they own:** specific accountabilities, not a job description. Think: what decisions does this person make?
- **How they work best:** the most important column, and the most commonly done badly. Must be specific and behavioural — not adjectives.

  ✓ `Prefers data with sources cited; sceptical of unsupported claims`
  ✓ `Likes options presented with trade-offs, not a recommendation`
  ✓ `Warm communicator; use narrative structure, not bullet points`
  ✗ `Analytical`
  ✗ `Detail-oriented`
  ✗ `Strategic thinker`

**Maximum rows:** no hard limit, but past 8–10 people the table starts degrading signal. For larger teams, include only people the AI is likely to interact with or produce output for.

---

## Section 03 — How we make decisions

**Purpose:** Decision rights are the single most common thing AI gets wrong in a team context. This section prevents the AI from treating everyone as equally authoritative, or from producing outputs that bypass the right approver.

**Format:** Bullet list. Max 6 bullets.

**What to include:**
- Named individuals with their specific decision domains
- Any financial or scope thresholds (e.g. "over $5k")
- Escalation rules — when does something need to go up?
- A default for ambiguous situations

**What to avoid:**
- Collective decision-making language ("we decide together") — too vague to act on
- Org chart descriptions
- Principles without specifics ("we value autonomy")

**Good example:**
- **Sarah** has final call on anything people-facing or externally communicated.
- **Marcus** owns all vendor and tooling decisions over $5k.
- When in doubt: flag it to Sarah rather than assume.

**Bad example:**
- Decisions are made collaboratively with input from all stakeholders.

---

## Section 04 — Communication norms

**Purpose:** Tells the AI how to calibrate tone and format for different contexts and audiences. Prevents generic output when the team has specific expectations.

**Format:** Bullet list. Max 5 bullets. Bold the channel or context at the start of each bullet.

**What to include:**
- Internal vs external tone distinction
- Named channels with their expected register
- Review gates — who must see something before it goes out
- Any strong preferences about format (e.g. "no bullet points in external comms")

**What to avoid:**
- Generic communication values ("we communicate openly and honestly")
- Anything that applies to every professional team

---

## Section 05 — How we use AI

**Purpose:** Two-sided: tells the AI what it's being used for (so it can lean in) and what requires human review (so it knows when to flag rather than complete).

**Format:** Two subsections, each a bullet list. Max 5 bullets each.

### What we use it for
Active use cases where AI adds value on this team. Be specific about the task type.

✓ `Drafting: first-pass job descriptions, policies, staff communications`
✗ `Writing things`

### What we don't use it for (without explicit human review)
Tasks where AI output must be reviewed by a named person before use. Name the reviewer where possible.

✓ `Final versions of anything going to staff or leadership — Sarah reviews`
✗ `Important communications`

---

## Section 06 — AI guardrails

**Purpose:** The most important section. Encodes the data and process constraints that protect the team and organisation. These are rules, not preferences.

**Format:** Two subsections.

**Never include in prompts:** data types or combinations that must never enter an AI context window. Be specific about combinations, not just categories.

✓ `Individual employee names combined with performance or health information`
✓ `Salary or compensation data`
✗ `Sensitive information` (too vague — what counts as sensitive?)

**Always do before sending AI output externally:** required human steps before output leaves the team. Name the reviewer.

✓ `Get Sarah's sign-off if it's going above team level`
✓ `Check any statistics cited — AI hallucinates numbers`
✗ `Review carefully` (who? how?)

**Optional — On tone:** a single sentence about the quality bar for AI output before it's used. Only include if the team has a strong and specific preference.

---

## Section 07 — Key workflows

**Purpose:** Makes repeating team processes explicit and machine-readable. Tells the AI where it helps and where humans stay in the loop.

**Format:** One `###` subsection per workflow. Each is a numbered step list. Max 5 workflows, max 5 steps each.

**What to include:**
- The 3–5 workflows the team runs most frequently
- Where AI contributes in each step
- Where a named human must review or approve

**What to avoid:**
- Documenting every workflow — only the ones where AI involvement needs guidance
- Steps that don't touch AI at all (unless they're a required human checkpoint)

**Good example:**
```
### Writing a job description
1. Owner writes the role brief — not AI
2. AI expands into full JD format using jd-template.md
3. Marcus checks scope and level alignment
4. Sarah approves before posting
```

---

## Optional section — Things to know about our context

Use this for operational facts that would change how an AI responds: tools and systems in use, fiscal calendar, key annual milestones. Only include facts that are specific and stable enough to be useful.

---

## Optional section — What "good" looks like on this team

3–5 short declarative statements that capture the team's quality bar. These shape tone and judgment across every response. Keep them plain and behavioural — not values-speak.

✓ `Clear is better than clever`
✓ `AI is a tool, not a team member — humans own outcomes`
✗ `We strive for excellence in everything we do`

---

## Proposing changes to the schema

Changes to the schema are welcome via PR to `eugedelta/team-md`. The bar for a schema change is:

1. A real team tried the existing schema and found a genuine gap
2. The proposed addition would cause Claude to make fewer mistakes, not just feel more complete
3. The change doesn't push the file past 150 lines in typical use

Additions that are "nice to have" but don't change AI behaviour will be declined.
