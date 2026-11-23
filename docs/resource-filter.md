# Is this worth my time?

A filter for everything I find. Takes 60 seconds. The point is to make the
decision *once*, quickly, instead of carrying 40 open tabs around all week.

---

## The five questions

Score 1 point each. Be strict — most things score 2.

**1. Who made it, and what do they sell?**
A design-system tool company saying design systems are critical is not evidence.
Vendor content isn't worthless, it's just marketing with a bibliography. Point if
the author has no product in the answer, *or* is openly honest about having one.

**2. Is there a method, or just a vibe?**
Does it say how many, over what period, measured how? "84% of teams" with no
source is a vibe. "We audited 21 public design systems in July 2026, here's the
schema" is a method. Point for a method.

**3. Does it tell me what to do on Monday?**
Can I name one concrete action after reading? If it only changes what I *think*,
it's an opinion piece — sometimes worth it, usually not. Point for an action.

**4. Is it new, or a rename?**
Most "AI design" content is UX fundamentals with new vocabulary. That's not always
bad — new words can be genuinely useful — but if I already do the thing, I don't
need the course. Point only if there's a real new idea or a real new artifact.

**5. Would it survive the tool dying?**
If this tool is gone in 18 months, is anything left? Ideas and formats last
(versioning, specs, tokens, evals). Tool tutorials don't. Point for durable.

### Scoring

| Score | What I do |
|---|---|
| **4–5** | Read properly. Log it. Take one action from it this week. |
| **2–3** | Skim. Write **one line** in the log. Never open again. |
| **0–1** | Delete. Don't save, don't bookmark, don't "read later." |

---

## Red flags — spot these in five seconds

- **No date, no author.** In this field a piece with no date is unusable.
- **"Everything has changed" / "X is dead."** Selling urgency.
- **Round numbers with no source.** "70% of designers will…"
- **A carousel of 10 tools.** Engagement bait. Zero of them will be in your workflow next month.
- **The only evidence is a screenshot of a chat.** One lucky output isn't a method.
- **Comments are all "🔥 this!"** and nobody asked a question.
- **It defines a new acronym and then sells the course on it.**
- **Reposts of a reposted insight.** Find the original or drop it.

## Green flags

- **Dated, and names its method.** Even a rough one.
- **Says what it doesn't know.** "My early tests show promising gains" with no data
  is *honest* — the author telling me the evidence is thin is a point in their favour.
- **Links primary sources** rather than other posts.
- **The author built the thing**, and shows the actual file.
- **It costs them something to say.** Admitting a failed approach, naming a trade-off.
- **It's boring.** Specs, formats, naming conventions. Boring ages well.

---

## The specific traps in my field right now

**Short-form video.** A 40-second reel cannot teach a system. It can only tell me
a thing exists. That's a legitimate use — *but then the job is to go find the real
source, not to save the reel.* A saved reel is a decision deferred, and deferring
decisions is what's making me tired.

**Rules for me:**
- A reel is a pointer, never a resource. Find the original or let it go.
- Nothing gets "saved" on Instagram. It goes in the log or it's gone.
- **Unsave everything currently saved.** All of it. If it mattered, it comes back.

**Design-systems-and-AI content specifically.** Heavy vendor presence
(Figma, zeroheight, Supernova, Knapsack all sell something here). Their research
is often genuinely good — just read it as a vendor with a method, and check the
sample before quoting the number.

**"The future of design" posts.** Ask: is this person building, or commentating?
Both can be useful. Only one is evidence.

---

## Where it goes

One file: `docs/links.md`. One Notion page: **Links inbox**, for things caught on
the phone.

**Friday, 15 minutes:** empty the Notion inbox through this filter, move the 4s
and 5s into `links.md`, delete the rest. Anything in `links.md` untouched for a
month gets deleted too. The log is a tool, not an archive.

---

## Using Claude for this

Send a link with: **"triage this"**

I'll come back with: score out of 5, one line on what it actually says, whether
it's new or a rename, the one action if there is one, and whether the author is
selling something. Then I add it to `links.md` in the right place.

**Cheaper options for the easy ones** — worth using, since tokens are money:
- *"Summarise this article in 5 bullets"* → Gemini or Copilot. No judgement needed.
- *"What does this word mean"* → Gemini. Then add it to `glossary.md` myself.
- *"Is this worth my time, given what I'm building"* → here. That needs to know my project.

The difference: use the expensive tool when the answer depends on **my** context.
Use the cheap one when it doesn't.
