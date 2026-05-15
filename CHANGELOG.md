# Changelog

## v2.2 — 2026-05-15

Adds temporal-context handling and surfaces calibration outputs as Verdict Cards.

- **Phase 2.5 (Establish temporal context)** added to `skill/SKILL.md`. Before verification, the skill locks down the content's publication date as the reference frame for Claims-real scoring. Stale-but-accurate facts (correct at publication, superseded since) surface as *Updated since publication* rather than as factual errors.
- **Tier 0** added to `skill/references/verification-tactics.md` covering the same principle: a search result that diverges from the content triggers an as-of-date check before being treated as an error.
- **Verdict Card template** in `skill/SKILL.md` gains optional `As of date:` and `Updated since:` lines below the composite score.
- **System prompts** (`skill/SKILL.md`, `prompts/v2.md`, README copy) gain a one-sentence instruction: treat the content's publication date as the reference frame for factual claims.
- **`examples/04-simon-willison.md`** now leads with a Verdict Card (9/10 composite) above the existing full DDC. Makes the calibration score explicitly findable for users verifying the skill's reported behaviour on legitimate content.

Driven by feedback from Meriel Batterley (AI Ethics Researcher / AI Governance Specialist) after running the skill on her own AI surveillance Substack post, where current-date verification flagged a US government contract figure ($10M) as wrong when it was correct at the time of writing and sourcing.

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
