# Design systems in code — the basics

From your note: *"I need to know more about how design systems connect with code,
I feel I don't know much about that. What are the basics that I need to know?"*

There are five moving parts. You already understand the first one better than most
engineers do — you just haven't seen it written as data before.

---

## The pipeline, in one line

```
design tool → token file (JSON) → build step → CSS/iOS/Android → components → Storybook → versioned package
```

Every design system you admire is running exactly this. Nothing more exotic.

---

## 1. Tokens — your decisions, as data

A JSON file holding your palette, spacing, type scale and radii. Not a Figma style:
a file.

```json
{
  "color": {
    "sand":  { "500": { "$value": "#B4A58E", "$type": "color" } },
    "text":  { "primary": { "$value": "{color.sand.500}", "$type": "color" } }
  }
}
```

**Two tiers, and the distinction is the whole skill:**

- **Primitive** — the raw material. `color.sand.500`, `space.4`. Nobody applies
  these to a screen directly.
- **Semantic** — the decision. `color.text.primary`, `color.surface.calm`. These
  point at a primitive, and these are what components use.

Why it matters: when you change `color.sand.500`, every semantic token pointing at
it changes, and every component changes with it. One edit, whole product. That's
the payoff, and it only works if nobody skipped the semantic tier.

The format is **DTCG** (W3C Design Tokens Community Group), version 2025.10 — the
first stable one. It defines `$value`, `$type`, the `{curly.brace}` alias syntax
and 13 token types. Use it as a lookup, not a read-through:
<https://www.designtokens.org/tr/2025.10/>

**This is week 3.**

---

## 2. The build step — Style Dictionary

A small program that reads your token file and writes out a version for each
platform: CSS custom properties for web, Swift for iOS, XML for Android.

You configure it once (which files to read, which formats to write) and then forget
it. You do not write it, and you do not need to understand its internals.

Input: `tokens.json`. Output: `variables.css` containing
`--color-text-primary: #B4A58E;` and so on.

---

## 3. Components — code that consumes tokens

A component is a reusable piece of UI. The discipline is one rule:

```css
/* right */
.button { background: var(--color-text-primary); }

/* wrong — this is the bug your AGENTS.md exists to prevent */
.button { background: #B4A58E; }
```

A hardcoded value is a decision made outside the system. That's the whole failure
mode, and it's what you'll be testing for in week 4.

---

## 4. Storybook — the showroom

A web page listing every component in every state (default, hover, disabled,
loading, error), so people can see and poke at them without opening the real app.

For you, it's the thing that replaces a Figma page of component variants — except
it shows the *real* component, so it cannot drift from what ships.

---

## 5. The package — how it gets delivered

The system gets a version number (`1.4.2`) and products install it like any other
dependency. A change you make can be released, or deliberately held back.

This is why "design systems moved into GitHub" — version numbers, pull requests
and release notes are git's native vocabulary. There's nowhere else to put them.

---

## What you own

| Part | Whose job |
|---|---|
| 1. Tokens | **Yours.** Your eye, written as data. |
| 2. Build step | An engineer's, configured once. |
| 3. Component rules | **Yours.** Which tokens are allowed where, and the rules in `AGENTS.md`. |
| 4. Storybook | Shared. You review in it. |
| 5. Package | An engineer's. |

Two of the five are yours, and they're the two that decide how everything looks.

---

## The AI layer on top (week 7)

A design system is "AI-ready" when an agent can read it and build correctly without
guessing. In practice that's four files, and the audit of 21 public systems found
how common each is:

| File | What it does | How many of 21 ship it |
|---|---|---|
| MCP server | Lets an agent query the system live | 18 |
| Agent skill | Teaches an agent how to use the system | 18 |
| `llms.txt` | A compiled index of the docs, for machines | 15 |
| `AGENTS.md` | The rules an agent must follow in the repo | varies |

The pattern separating the leaders is **structural coercion** — designing the task
so the agent *cannot* go off-system, usually by forcing it to call a search or
validator tool before it answers. Shopify's Polaris skill tells the model outright
that it cannot trust its own trained knowledge.

The gap worth knowing about: only **3 of 21** use Figma Code Connect. The
Figma-to-code link is not the solved part of this. That's open ground.

---

## Sources

- [Design Token-Based UI Architecture](https://martinfowler.com/articles/design-token-based-ui-architecture.html)
  — martinfowler.com. The clearest thing written on this, free, and not written for
  people who are already fluent. **Start here.**
- [DTCG Format Module 2025.10](https://www.designtokens.org/tr/2025.10/) — the format spec.
- [State of AI in Design Systems](https://state-of-ai-in-design-systems.netlify.app/)
  — Kaelig Deloumeau-Prigent, data collected 26–28 July 2026. An audit of 21 real
  public systems. Caveat from the author: private repos mean "no public agent files"
  is not "no AI usage," and the maturity ratings are his judgement.
- [zeroheight DS ARC](https://zeroheight.com/arc/) — free tool, scores how readable
  your docs are to an agent. Week 7, once you have docs to test.
