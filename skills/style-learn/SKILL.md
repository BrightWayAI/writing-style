---
name: style-learn
description: Analyze a draft-vs-final pair after you've edited a draft before sending. Detect style patterns. Updates style files only after 2+ recurrences. Auto-fires on "/style-learn", "I just sent the email — see if you can learn from my edits", "compare my draft to what I actually sent", "did you notice the changes I made", or any phrase about feeding back edited content.
---

See `commands/style-learn.md` for the full analysis workflow.

## When this skill fires

- User runs `/style-learn` directly
- User says: "I just sent that — what did I change?", "see if you can learn from my edits", "compare to my final version"
- User mentions having edited a draft externally (Gmail, Drive, LinkedIn) and asks the plugin to look

## Pre-flight

Confirm `<config-root>/voice.md` and (if applicable) `<config-root>/style-{medium}.md` exist. Confirm `<config-root>/plugins/writing-style.user-context.md` exists for the confidence threshold.

## What this skill is NOT for

- One-off corrections (typos, factual fixes). The triage step catches these — they're not style patterns.
- Rewrites. If the final is >50% different from the draft, treat as a new sample, not an edit.
- Auto-committing. All updates pause for user confirmation.
