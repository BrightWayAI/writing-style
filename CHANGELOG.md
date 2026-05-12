# Changelog

All notable changes to writing-style are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/). Versions match `plugin.json`.

## [0.1.0] — Initial release

### Added
- Adaptive writing-style plugin. Learns your voice from real edits over time, complementing cortex's `/setup-voice` (which captures the high-level baseline once).
- **`/setup-style`** — bootstrap interview. Reads `<config-root>/voice.md` if present (cortex setup-voice output). Pulls 5-10 writing samples from Gmail (or asks the user to paste). Analyzes voice, structure, sentence style, common phrases, "what NOT to do." Writes/refines `<config-root>/voice.md` and creates medium-specific files (`style-email.md`, `style-social.md`) if 3+ samples exist per medium.
- **`/style [medium] [purpose]`** — draft something in your voice. Reads voice + medium-specific style files. Presents as draft for review. Never sends directly; Gmail emails are written as drafts via the connector.
- **`/style-learn`** — accepts a draft + final-version pair (provided inline or pulled from sent/published source via connector). Two-stage triage: cheap classifier asks "is this a style pattern?" → expensive synthesis only if pattern detected. After 2+ recurrences of the same pattern, surfaces a style-guide update proposal for user confirmation before commit.
- **`/style-review`** — audit existing style files. Flags contradictions, stale rules, unvalidated patterns, missing rules implied by recent writing history.
- **Per-medium style files** — `<config-root>/style-email.md`, `<config-root>/style-social.md`, `<config-root>/style-{medium}.md` for any other medium. Separated so email rules don't bleed into LinkedIn posts.
- **Config-root path convention** — uses `~/Documents/.claude-plugin-config-root` pointer like every other marketplace plugin. Style files live alongside `identity.md` and `voice.md`.
- **Privacy** — first occurrence of any pattern captured privately (not committed). Second occurrence triggers user-confirmed commit. Drafts are review-then-send-by-user; the plugin never sends anything.
- Reference: `references/analysis-template.md` documents the diff-vs-final analysis format.
