# The words

Words I need to understand, use correctly, and recognise when someone else is
using them to sound clever.

**How to read this:** plain meaning first. Where it's useful, a sentence I could
actually say out loud. ⚠️ marks words that are contested, dated, or make you
sound worse rather than better.

**The rule that matters more than the list:** never use a word in front of a
client that I couldn't explain in one plain sentence if they asked. Being the
person who says *"honestly, that term gets used three different ways — here's
what I mean by it"* reads as more senior than fluent jargon. Every time.

---

## 1. How the models actually work

**Token** — a chunk of text, roughly ¾ of a word. Models read and write in tokens,
and that's what you pay for. "This costs a lot of tokens" = "this is expensive".

**Context window** — how much the model can hold in mind at once. Everything in
the conversation, plus the files it's read. When it's full, things get dropped.

**Context engineering** — deciding *what goes into that window*: which files, which
examples, in what order. This has largely replaced "prompt engineering" as the
serious version of the skill.
> *"Most of the quality comes from context engineering — what the model can see
> when it answers, not how cleverly you phrase the question."*

**Grounding** — tying the model's answer to a real source instead of its memory.

**RAG** (retrieval-augmented generation) — fetch the relevant documents first, put
them in the context, then answer. The standard way to make a model answer from
*your* material rather than from the internet in general.

**Hallucination** — confident invention. Not a bug you fix; a property you design
around.

**Eval** — a repeatable test for AI output. You define what "good" looks like and
score against it, every time, instead of eyeballing it.
> *"We should have an eval for that — otherwise we're just hoping it stayed good."*

This is the most underrated word on this page. Very few designers say it. Saying
it correctly signals you've actually shipped something.

**Inference** — the model running. "Inference cost" = what it costs to use.

**Fine-tuning** — retraining a model on your data. Expensive, rarely the answer.
Usually what someone needs is better context, not fine-tuning. Knowing *that*
is the useful part.

**Non-deterministic** — same input, different output. The reason AI features need
evals and guardrails rather than a test that checks for one exact answer.

---

## 2. Agents

**Agent** — a model that can take actions in a loop: decide, use a tool, look at
the result, decide again. Not just text in, text out.

**Tool use / function calling** — giving the model things it can *do* (search a
file, call an API) rather than only things to say.

**MCP (Model Context Protocol)** — an open standard for plugging tools and data
sources into an AI. Think of it as a socket: build the connector once and any
compatible AI can use it. From Anthropic, now widely adopted.
> *"We'd expose the design system over MCP so whatever tool they're in can read
> it — that's cheaper than maintaining three integrations."*

**Agent skill** — a folder of instructions an agent loads only when relevant.
Keeps the context window clean.

**Subagent** — a separate agent given one job, so its work doesn't clutter the
main conversation.

**Orchestration** — coordinating several agents or steps.

**Guardrails** — the rules and limits around what an agent is allowed to do.

**Human in the loop** — a person approves before something irreversible happens.
An old safety concept, suddenly very relevant, and genuinely a *design* decision:
where you put the approval is a UX call.

**AX / Agent Experience** ⚠️ — designing for the agent as a user: can it find your
thing, use it correctly, recover when it fails. Coined by Netlify's CEO around
2025. **Still unsettled** — mostly defined by vendor blogs, and some practitioners
push back hard ("we design for people, full stop"). It splits into two different
things people muddle:
- designing *for* agents (your docs, your API, your design system — readable by a machine)
- designing *agents* (what the thing says and does to a person)

Use it, but define which one you mean in the same breath. That's the move.

**Agentic** ⚠️ — "has agents in it". Massively overused. Say what the thing
actually does instead.

---

## 3. Design systems in code

**Design token** — a named design decision stored as data. `color.text.primary`
instead of `#23201C`. The thing that lets one decision reach every platform.

**DTCG** — the W3C Design Tokens Community Group format. The agreed file format
for tokens; version 2025.10 is the first stable one. Saying "DTCG format" instead
of "a JSON file with the colours" is a real signal.

**Primitive / semantic / component tokens** — the three tiers.
`color.sand.500` (raw) → `color.surface.calm` (meaning) → `button.bg` (specific).
Nobody should use the raw ones directly in the product.
> *"The problem isn't the palette, it's that there's no semantic layer — so every
> theme change is a find-and-replace."*

**Style Dictionary** — the common tool that turns one token file into CSS,
iOS, Android, whatever.

**Code Connect** — Figma's feature for mapping a Figma component to its real code
component, so what the developer gets is the actual code.

**Single source of truth** — one place a decision lives. Everything else reads
from it. Old term, still the whole argument.

**Component API** — the props a component accepts (`variant`, `size`, `disabled`).
Designing the API *is* design work, and it's the vocabulary developers think in.

**Machine-readable documentation** — docs structured so an agent can use them, not
just a human skim them. This is the shift.

**llms.txt** — a plain-text index of your docs, for AI. Like `robots.txt`, but for
helping rather than blocking.

**AGENTS.md** — a vendor-neutral instructions file in a repo: how an agent should
behave here, what the rules are. (`CLAUDE.md` is the Claude-specific equivalent.)

**Tool-gating / structural coercion** — forcing an agent to look something up before
it answers, instead of politely asking it not to guess. The 2026 research finding:
the best design systems redesign the task so the model *can't* go off-system.
Prohibition doesn't work; structure does.
> *"Telling the model 'don't invent components' doesn't hold. Making it call a
> search tool before it answers does."*

**AI-ready** ⚠️ — vague on its own. Only means something if you name the artifacts:
tokens in DTCG, an `llms.txt`, an `AGENTS.md`, a validator.

---

## 4. Shipping

**Repo (repository)** — the project folder, with its full history.

**Commit** — a saved version, with a note about why.

**Branch** — a safe copy to try something in.

**Pull request (PR)** — "here's my change, have a look before it goes in." Where
code review happens. The closest thing to a design critique.

**Merge** — accepting it. **Revert** — undoing it.

**Main** — the real version.

**CI/CD** — automated checks and automated releases. "It's in CI" = a robot is
testing it right now.

**Deploy** — putting it where people can reach it. **Staging** vs **production** —
the rehearsal vs the real thing.

**Semantic versioning (semver)** — `2.4.1` = breaking.feature.fix. Bumping the first
number means you broke something on purpose.

**Changelog** — what changed, for humans. A design system without one isn't a
design system, it's a folder.

**Open source / MIT licence** — public, free to use. Relevant because your public
repo *is* the portfolio now.

---

## 5. The work itself

**Spec-driven development** — write the spec first, precisely, then let the agent
build from it. **Spec-driven design** is the designer's version: the designer
authors the spec rather than receiving it.
> *"I've moved from handing over mockups to authoring the spec the agent builds
> from. The mockup is an attachment to it now, not the deliverable."*

This is the sentence that does the most work for you in a room.

**Design engineer** — designs *and* builds in code. The role that took your
assignment. Worth naming without flinching.

**Scraping** — automated extraction of data from websites by reading the pages.
Legally and ethically grey: terms of service, copyright and personal data all
apply. The grown-up version of the sentence is *"we'd check whether there's an API
or a licence before scraping anything"* — that's what a client wants to hear.

**API** — a defined way for one piece of software to ask another for something.

**Headless** — the content/data layer with no fixed front end, so many surfaces can
use it. Same idea as tokens: separate the decision from the rendering.

**Technical debt** — shortcuts you'll pay for later.

**Intent debt / cognitive debt** ⚠️ (new, from research Futurice cites) — what you
lose when the *reasoning* behind a decision isn't written down, so nobody can tell
later whether it still applies. Genuinely useful, and almost nobody is saying it yet.
> *"The risk with generated code isn't the code. It's intent debt — six months in,
> nobody knows why it works that way."*

**SDLC** — software development lifecycle. "Agentic SDLC" = the same lifecycle with
agents doing more of the middle.

**Prototype vs production** — looks real vs is real. The distinction AI is currently
blurring, and the one clients most need a designer to hold.

---

## 6. ⚠️ Words that cost you credibility

| Word | Why |
|---|---|
| **Vibe coding** | Informal, slightly self-deprecating. Fine among peers, bad in a pitch — it says "I didn't read what it wrote." |
| **Prompt engineering** | Dated. The serious term is *context engineering*. |
| **AI-powered / AI-native** | Means nothing by itself. Say what it does. |
| **10x** | Nobody measured it. |
| **Disruptive / game-changing** | Instant discount on everything else you say. |
| **"X is dead"** | Figma isn't dead, design isn't dead. Anyone saying it is selling something. |
| **Agentic** | Overused to the point of noise. |
| **Leveraging** | Using. |

---

## 7. The five that are actually worth owning

If I only properly learn five, these — because they're correct, current, and
most designers can't use them precisely:

1. **Context engineering** — what the model can see
2. **Eval** — how we know it stayed good
3. **Semantic token layer** — why the theme change isn't a find-and-replace
4. **Tool-gating** — why "please don't guess" doesn't work
5. **Intent debt** — why writing down the *why* is the job now

Each one has a sentence above. Learn the sentence, not the definition.
