---
name: word-vomit-jargon
description: Rewrite a technical update, log, ticket note or choice as five short, explain-like-I'm-5 labeled lines (Term → What → Why now → Impact → Ask), under 600 characters, in a curious and humble voice. Use when the user says "word vomit jargon", "/wvj", "you're doing the jargon again", or when giving the user status, findings or a decision.
license: MIT
compatibility: Any AI agent or chat assistant that reads Markdown instructions. No tools required.
metadata:
  author: Jerry Reinitz
  version: "4.0"
  source: https://github.com/JR91387/vomit-jargon-ai-skill
---

# Word Vomit Jargon

Explain it so a smart 5-year-old gets it and the reader learns something. Input: the text given, or your last reply.

## Mindset: curious and humble
- If they didn't get it, you explained it badly. Never imply they're slow.
- Wonder what they already know; start there, not at the jargon.
- Say "I'm not sure" plainly. Don't defend, don't pad, don't show off.

## Output: five labeled lines, under 600 characters total

```
**Term:** the thing, by name.
**What:** what it is and does, in everyday words.
**Why now:** why it came up.
**Impact:** what breaks, and what stays safe.
**Ask:** one thing to do next.
```

- Keep this order. Ask always last.
- Over 600 characters? Cut words, or split into two items.
- Full paths and URLs don't count toward the 600.

## Plain words
- Short, common words. One idea per line.
- Name the real term once, then explain it like a kid's picture: "a lock (a 'do not touch' sign on the row)".
- Say what physically happens, not buzzwords: "the database hides rows you don't own", not "RLS enforcement".
- Define every acronym on first use.

## Grounding
- No vague filler ("high traffic", "seamless", "performance") and no invented numbers, incidents or dates.
- Files as full absolute paths, links as full `https://…`.

## Example
Input: "api.get_my_block_billing is STABLE but inherits a FOR UPDATE check from admin.my_block; make it volatile or drop the lock."

❌ "Lock contention from an inherited FOR UPDATE check in a STABLE function is degrading billing under load."
*Jargon, invented load, no ask.*

✅
**Term:** `api.get_my_block_billing`, a database function.
**What:** It shows a building's bill and promises to only look, never touch.
**Why now:** It asks for a "do not touch" sign on the row, which a look-only job can't hold.
**Impact:** It fails every time; landlords miss renewal dates. No data lost.
**Ask:** Give it a look-only ownership check.

<!-- word-vomit-jargon by Jerry Reinitz, Midwest software engineer · https://jerryreinitz.com · https://github.com/JR91387/vomit-jargon-ai-skill · MIT -->
