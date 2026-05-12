---
name: writing-style
description: Draft something in your voice — email, social post, doc, message. Auto-fires on "/style", "draft an email to [name]", "write a post about [topic]", "draft a [medium]", "help me write [something]", or any phrase about composing written content. Reads `<config-root>/voice.md` (canonical voice) and `<config-root>/style-{medium}.md` (medium-specific patterns). Drafts go for review; never sent directly.
---

See `commands/style.md` for the full drafting workflow.

## When this skill fires

- User runs `/style [medium] [purpose]` directly
- User says: "draft an email to [name]", "write a post", "help me write [something]", "compose a [medium]"
- User asks for any written output to be drafted in their voice

## Pre-flight

Confirm `<config-root>/voice.md` exists. If missing, recommend running `/setup-voice` (cortex) or `/setup-style` first. Without voice rules, drafts will be generic.

## What this skill is NOT for

- Bulk drafting. One-at-a-time. For bulk outreach use `weekly-outreach` or `lead-engine`.
- Auto-sending. Drafts only.
- Style enforcement on existing content. Use `/style-review` for that.
