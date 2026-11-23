# Decisions

Append only. Newest at the bottom. One entry per real decision: what, why, and
what was rejected. If a decision is in here, it is closed — don't re-open it
without writing a new entry that says why.

---

### 2026-11-23 — Notion for thinking, the repo for the artifact

**Decided:** Notes, learning log, canvas and links inbox live in Notion. The
product spec, design tokens, component docs and agent rules live in this repo as
markdown and JSON.

**Why:** Notion is better for thinking and I'll actually open it. But the thing
I want to show clients — an AI-ready design system — is *defined* by files in a
repo: `AGENTS.md`, `tokens.json`, `llms.txt` can't live in Notion. Splitting it
this way also means I learn git by writing, instead of taking a separate git course.

**Rejected:** Notion only (can't produce the artifact). Repo only (I'd stop using it).

---

### 2026-11-23 — MamAI gets its own small design system

**Decided:** MamAI will have a real design system — tokens plus about five
components — rather than building a separate demo design system.

**Why:** It's one project, not two. A real system for a real product is more
convincing than a demo system for a fake one. And MamAI needs a UI anyway.

**Rejected:** A standalone design system demo with no product behind it.

**Constraint:** Keep it tiny. Two token tiers (primitive + semantic), five
components. Resisting the urge to grow it is the skill being practised.

---

### 2026-11-23 — Claude certification is off the table

**Decided:** Not pursuing Anthropic's Claude certification. Target GitHub
Foundations (~$49–99) as the one paid credential, plus free Claude Academy badges.

**Why:** The Claude certification exams are only open to employees of companies
in Anthropic's partner network. Not available to an independent individual.
Checked 23 Nov 2026.

---

### 2026-11-23 — 24–36 hours a week, and the subjects get named

**Decided:** The plan assumes ~25 h/week, not 4–6. Each week names its subject
explicitly (Git & GitHub, spec-driven design, design tokens, agent rules, MCP &
skills, deploying, AI-ready design systems) instead of absorbing them as a side
effect of building.

**Why:** Being able to tell a client "I know X" is the point, not just being able
to do X. Total: ~202 hours over nine weeks.

**Rejected:** The earlier 4–6 h/week shape, which hid the subjects inside the
project work.

---

### 2026-11-23 — Evidence base: the AI in Design Report 2026

**Decided:** The plan's claims are anchored to the Designer Fund / Foundation
Capital survey (900+ designers, published 6 Oct 2026), not to Claude's opinion.
Key figures: 50% have shipped AI-generated code to production; only 20% identify
as design engineers; ~80% say AI assists but does not replace their judgment;
designers who code or prototype with AI were twice as likely to feel more creative
and capable.

**Why:** Lola said plainly that she trusts practitioners over Claude, and she is
right to. Everything suggested from here needs a source.

**Caveat on the source:** Anthropic is a report partner and several quoted voices
work there. The percentages are survey data, not their claims.

---

### 2026-11-23 — Notes live in the published artifact's database

**Decided:** The presentation is a published artifact
(claude.ai/artifact/8RBhUZi9sVNVphj2Y8VJ5F). Notes and progress ticks are stored
in its database, not in browser storage.

**Why:** The local preview runs as a `data:` URL, where browsers block storage.
The first five notes were typed into a page that silently saved nothing; they were
recovered from the open tab and restored. Storage in the artifact database also
means Claude can read the notes directly.

**Rule:** type notes on the published page, not in the local file preview.

---
