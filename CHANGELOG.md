# Changelog

## v2.1 — 2026-05-10

Added a portable Claude skill version of the v2 prompt under `skill/`.

- `skill/SKILL.md` — skill definition with five-phase workflow (identify input → acquire content → independent verification → analytical framework → Verdict Card / full DDC output)
- `skill/references/verification-tactics.md` — guidance on which claims are cheap to verify and how to use web search effectively
- `skill/references/youtube-extraction.md` — environment-aware transcript extraction priority chain
- README updated with install instructions for the skill alongside the existing paste-the-prompt path

The skill adds a verification layer the prompt lacks: it runs independent web searches over falsifiable claims before producing the card. Output defaults to a compact Verdict Card; the full 12-section breakdown is available on request.

## v2.0 — 2026-05-08

Initial public release.

### Sections in v2

- Strongest counter-position (forensic for suspect content, intellectual for substantive content)
- Content genre (specific, not generic)
- Claims extracted (grouped by type: empirical / conceptual / attributed)
- Authority signals (classified as borrowed vs referenced)
- Monetisation pattern (direct-extraction / indirect / normal-creator / none)
- Salt and circular-reference patterns (with verification anchors when none)
- Survivorship bias / N=1 signals
- Structural red flags (split into fraud-risk vs benign-pattern resemblance)
- Verification checklist (tiered: passing / worth confirming / not load-bearing, each with concrete action)
- Confidence assessment (4-axis with explicit levels)
- Real Pushback (substantive intellectual critique, runs every analysis)
- Bottom line (no meta-commentary)

### Calibration

Tested across four content types:

1. Obvious scam (X post, affiliate funnel)
2. Sophisticated scam (long-form article, real concepts mixed with fabricated authority, salted GitHub repos)
3. Content marketing (LinkedIn post by self-described growth marketer)
4. Verified legitimate substantive content (Simon Willison blog post)

The prompt called each correctly. See `examples/` for the actual outputs.

### Changes from v1 (internal, not publicly released)

- Added Real Pushback as a dedicated section that runs on every analysis (not just suspicious content)
- Tiered the verification checklist into three groups, each item with a concrete action
- Removed meta-commentary about the analysis itself ("this tool should not over-flag" type language)
- Added soft length budgets per section
- Promoted empirical / conceptual / attributed claim grouping from emergent to explicit instruction
- Added explicit "if no monetisation, say so — don't infer from genre alone"
- Strengthened the borrowed vs referenced authority distinction
- Strengthened the fraud-risk vs benign-pattern split for structural red flags
