# Things I ask a lot

Your idea, from your notes on the token slide: collect the questions I keep asking
so Claude doesn't have to re-explain and I don't have to re-ask.

**How this works:** Claude adds to this file when you ask something that'll come up
again. `CLAUDE.md` tells Claude to read this file first. When it gets long, it
becomes a skill (see the entry below on the difference).

---

## How do I point Claude at a file instead of pasting it?

Type the path in your message — `docs/product.md` — and Claude reads it itself.
Or press `@` and pick it from the list.

Pasting the contents means the text goes through twice: once in your message, once
when Claude reads it. On a big file that's real money.

---

## CLAUDE.md or a skill — what's the difference, and which is faster?

| | CLAUDE.md | A skill |
|---|---|---|
| When it loads | Every single message | Only when it's relevant |
| Cost | Small, but constant | Zero until it's needed |
| Good for | Short rules that are always true | Longer knowledge used sometimes |
| Example | "Read docs/faq.md first" | "How to write a DTCG token file" |

**Rule of thumb:** if it's under ~10 lines and always applies, CLAUDE.md. If it's
a page of how-to you need occasionally, a skill. This file is in between — it
lives as a file, and CLAUDE.md just points at it, which costs one line.

---

## Where do my presentation notes go?

Into the published page's own database, not the HTML file. Claude reads them with
the artifact data tool. They survive you closing the tab, and they survive
Claude republishing the page.

**Important:** this only works on the **published** page
(claude.ai/artifact/8RBhUZi9sVNVphj2Y8VJ5F). The local preview of
`plan-presentation.html` runs as a `data:` URL, where browsers block storage — notes
typed there look saved and aren't. This already happened once.

---

## What's the difference between git and GitHub?

**Git** is the thing on your computer that saves versions. **GitHub** is the
website that holds a copy and lets other people see it. GitHub Desktop is the app
that does git for you without a terminal.

---

## Why can't Claude read my Instagram links?

Instagram requires a login to read a post, and Claude fetching a reel URL gets
back nothing but the page title. Tested 23 Nov 2026 on two of your links.

**What works instead:** screenshot the reel and drop the image in, or give Claude
the creator's handle so it can find what they've published elsewhere.

Claude *can* read a public Instagram **profile page** (bio, follower count, links)
through the browser pane — that's how yeho.ux was identified. It's the posts and
reels that are walled off.

---

## What's the difference between AX and AXD?

- **AX** (Agent Experience) — how an *agent* handles your site. Machine-facing.
  A technical concern.
- **AXD** (Agentic Experience Design) — a *person's* experience of supervising an
  agent. Human-facing. **This is the design field.**

People conflate them constantly. Knowing the difference makes you sound sharp.
Source: Pritam Roy, *Agent-First Web*, Oct 2026. See
[who-to-follow.md](who-to-follow.md).
