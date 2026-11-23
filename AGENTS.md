# How to work in this repo

This file is the front door for any AI agent working here (Claude Code, Copilot,
Cursor). `CLAUDE.md` just points at this file.

> **Status: stub.** This gets written properly in week 4, by testing it — ask an
> agent to build a screen, watch where it goes off-system, and tighten the rules.
> A rule that was never tested is decoration.

## What this project is

MamAI — a small tool for a new mother whose days never repeat, by a product
designer learning to work with agents. See `docs/product.md`.

## Read these first, in this order

1. `docs/product.md` — what this is and who it's for
2. `docs/specs/` — the feature specs. Build only what a spec describes.
3. `design-system/` — tokens and components. See the rules below.
4. `docs/decisions.md` — what was already decided, and why. Don't re-open it.

## Rules

- **Never invent a colour, spacing value, font size or radius.** Every visual
  value comes from `design-system/tokens.json`. If the token you need doesn't
  exist, stop and say so — do not improvise one.
- **Never invent a component.** The components are listed in
  `design-system/components.md`. If you need one that isn't there, stop and ask.
- **Don't build what no spec asked for.** No extra features, no "while I was here".
- **Record decisions.** Anything that changes direction gets a line in
  `docs/decisions.md` — date, what was decided, why, what was rejected.
- **Plain language in all docs.** This repo is read by a designer, not a developer.
  No jargon without a short explanation next to it.

## Tone

Calm, warm, unhurried. The reference is Google's People + AI Guidebook —
peaceful and organised, no noise. If a screen feels busy or urgent, it's wrong.
