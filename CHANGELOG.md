# Changelog

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
