# Links log

Everything that survived the filter in `resource-filter.md`. Scored out of 5.
Anything untouched for a month gets deleted.

---

## Keep — read properly (4–5)

### Faster prototypes miss the point: the case for spec-driven design — 5/5
Tuomas Härkönen, Futurice, 11 Aug 2026 · https://www.futurice.com/blog/spec-driven-design
**Says:** the designer's deliverable moves from the mockup to the spec — markdown
files versioned in git, in the product repo. Names the "Figma trap": mockups show
the happy path and hide edge cases, error states and data rules. Proposes a Product
Knowledge Base (agent instructions, vision, decision log, insights, standards,
feature specs) and five design phases that feed the spec.
**New or rename?** Genuinely new as a *designer* practice. The knowledge base part
is a rename of "wiki" — and he says so himself.
**Action:** write `docs/specs/001-daily-rhythm.md`.
**Selling?** Futurice is a consultancy, so it's thought leadership. He's also
honest that his evidence is thin ("my early tests show promising gains", no data).
That honesty is why it still scores 5.
**Status:** the spine of the 8-week plan.

### State of AI in Design Systems — 5/5
Kaelig Deloumeau-Prigent, data 26–28 July 2026, published Oct 2026 · https://state-of-ai-in-design-systems.netlify.app/
**Says:** an *audit of 21 public design systems* (not a survey of people — important).
18 of 21 ship an official MCP server. 18 ship agent skills. 15 publish `llms.txt`.
Key finding: **tool-gating beats prohibition** — the leaders force the agent to call
a search or validator tool instead of asking it not to guess. Atlassian ships an
~80KB `DESIGN.md`. Shopify Polaris blocks ClaudeBot in robots.txt while Nuxt UI
publishes for discovery. Public sector is sitting it out.
**New or rename?** New. This is the clearest picture available of what "AI-ready"
concretely means.
**Action:** week 4 and week 7 — copy the pattern, don't invent one.
**Selling?** No. CC BY-4.0, states its own caveats, lists what it couldn't see.
**Careful:** it's a snapshot that drifts weekly, and the maturity ratings are one
person's editorial judgement. Don't quote it as settled fact.

### DTCG Format Module 2025.10 — 5/5
Design Tokens Community Group (W3C) · https://www.designtokens.org/tr/2025.10/
**Says:** the token file format. `$value`, `$type`, curly-brace aliases, 13 token
types. First stable version.
**New or rename?** A standard, not an idea. Treat as a reference to look things up
in — reading it cover to cover is a waste of a morning.
**Action:** week 3, while writing `tokens.json`.

### AI & Design Systems course — 4/5
Brad Frost, TJ Pitre, Ian Frost (Southleft + Brad Frost Web) · https://courses.bradfrost.com/courses/ai-design-systems-course
**Says:** ~16–20 h of video on making a design system AI-ready and using AI across
product work. Slack community, bi-weekly jams, certificate of completion.
**Why only 4:** $995–$1,495. Real practitioners, real content, wrong price for now.
**Action:** **parked.** Employer training-budget request in month 4, once there's
a built thing to justify it with.

---

## Keep — skim only (2–3)

### zeroheight DS ARC — 3/5
https://zeroheight.com/arc/ · free tool
Scores your docs against a documentation spec, then runs an agent through eight
tasks and shows where it failed. Vendor tool, but free and the output is concrete.
**Action:** week 7 — run it before and after, screenshot both. That before/after
*is* the Friday proof.

### zeroheight State of AI in Design Systems report 2026 — 3/5
https://zeroheight.com/resources/state-of-ai-in-design-systems/
Survey of ~300 practitioners. Useful numbers (only 17% rate their docs "very
AI-ready"; 48% run an MCP server). Vendor research — fine to cite, but say the
sample size when you do.
**Careful:** its 84%-adoption figure is hard to reconcile with Kaelig's audit,
which found only 3 of 15 public systems actually shipping DTCG token files.
*When two sources disagree this much, that gap is the interesting thing.*

---

## Couldn't open — needs a decision

**~20 Instagram reels and posts** (Oct–Nov 2026), **6 LinkedIn `lnkd.in` links**,
**1 LinkedIn post** (andreaugusto, design systems share), **2 LinkedIn feed URLs**.

I couldn't read any of these — Instagram and LinkedIn block automated reading, so
I genuinely don't know what's in them. What I can say: **20 reels is not 20
resources.** It's one unmade decision, repeated 20 times.

**What to do, once, in 15 minutes:**
1. Open the saved folder. For each one, ask only: *can I name the idea in it right now?*
2. If yes → write the idea as one line in the Notion Links inbox. Then unsave it.
3. If no → it taught you nothing. Unsave it.
4. Anything whose idea you wrote down and still want → find the **original** (the
   article, the repo, the person's actual site) and bring that here to triage.

Then empty the folder completely. This is the single highest-value 15 minutes in
the whole plan, because this pile is what's costing you sleep — not a skills gap.

---

## Dropped

**The "future of design" genre generally** — commentary, not evidence. One useful
exception so far: **yeho.ux** on agent experience, per `context.md`. Keep following
one or two people, not twenty.

---

## To add

Send me a link with **"triage this"** and I'll score it and file it here.
