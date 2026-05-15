# Verification tactics for due diligence

Practical guidance on using web search effectively when running the Due Diligence Companion skill. The point of this layer is to convert items on the verification checklist into actual verified findings before producing the card, so the confidence assessment is evidence-backed rather than informed-guesswork.

## What to verify, in order of cheapness

Run searches in this rough priority order. Stop when a search becomes expensive (5+ queries, no decisive answer) — leave that item on the verification checklist for the user.

### Tier 0 — establish temporal context first

Before any Tier 1 verification, lock down the content's as-of date (see `SKILL.md` Phase 2.5). Every Tier 1/2 search below should be interpreted against that date, not against today. If a search returns a value different from what the content claims, the next question is not "is the content wrong?" — it is "was the content correct at its publication date?".

Practical:

- If a numeric claim doesn't match current data, search for the claim *as of* the publication date, or look for the original primary source the author cited. If the cited source supports the figure at the time of writing, the claim is "accurate as of [date], updated since" — not "factually incorrect".
- For fast-moving domains (AI regulation, model capabilities, government contract values, market figures, headcounts, current events), publication-date answers and current answers routinely diverge by 2x or more without any error by the author. Be especially careful in those domains not to flag stale data as factual error.
- If the as-of date cannot be established, default to current-date evidence and note the limitation in the verification checklist rather than scoring blind.

### Tier 1 — almost free, always do

These take 1 search each and resolve unambiguously. Always check them.

1. **Tool / product / platform existence.** "Does [X tool] exist?" Search the name. If it's a real product the first result is its homepage. If it's not, you'll get nothing relevant or you'll find that the name was repurposed from something else.
2. **Named GitHub repos.** Search for the repo. If the URL is in the content, fetch it. Real repos have stars, forks, contributor history, README quality, and commit timelines. Salted/fake repos are typically empty, recent, single-author, low-effort, or obviously generated.
3. **Author's claimed current role.** "[Person] [company]" — does LinkedIn or the company's site corroborate? Roles change; current state matters more than past.
4. **Public domain / website existence.** If a URL is mentioned, fetch it. Note whether it's a real site, a parked domain, an affiliate landing page, or a Beehiiv/Substack/Medium freebie.
5. **Specific named events / launches.** "[Product] launch [year]" or "[Event] [date]" — was the thing actually announced? Lots of grift content invents events that never happened.

### Tier 2 — usually worth it, 2–3 searches

These take a bit more work but are still tractable.

6. **Person's verifiable history.** Past employers, talks given, papers published, books written. Multiple corroborating sources matter more than any single source. Self-published bios are weak evidence; third-party mentions (conference programmes, news articles, podcasts they appeared on) are stronger.
7. **Whether a methodology / framework actually exists outside this content.** If the author claims to use "the X framework" or "the Y method", search for it. Real methods have prior art, citations, debate. Invented methods exist only in this author's posts and their funnel content.
8. **Affiliate / referral chain.** Click through any URL in the content. Note redirects, tracking parameters (`?ref=`, `?aff=`, `utm_source=`), and where the chain terminates. A free PDF that funnels to a paid course that funnels to a Telegram group is a different beast from a free PDF that funnels to nothing.
9. **Cross-reference handles.** If a content piece quotes a "user testimonial" or names a "collaborator", search the named handle. Salted content frequently has the same handle appearing as both author and recommender across different posts.

### Tier 3 — leave on checklist, don't try to resolve

These are uncheckable from web search alone. List them on the checklist, don't fabricate verdicts.

10. **Specific dollar returns or trade outcomes.** "I made $X from this strategy" is unfalsifiable from outside. Note this as structurally unverifiable.
11. **Private claims about communities or DMs.** "10,000 people in my Telegram" — you cannot count.
12. **Subjective experiential claims.** "This changed my life" — not adjudicable.
13. **Negatives.** "Nobody else is doing this" — you can sometimes find counterexamples but the absence of counterexamples isn't evidence.

## Query patterns that work

- For a person: search the name plus a distinguishing token (employer, project, niche). "John Smith trader" returns noise. "John Smith Tradeify chief of staff" returns signal.
- For a tool/repo: search the exact name in quotes only if the name is generic; bare otherwise.
- For a claim, search the load-bearing noun phrase, not the whole sentence. "Claim: NQ ORB strategy returned 47% in Q1" → search "NQ ORB strategy" and "opening range breakout futures performance" separately, not the whole sentence.
- For an entity that might be fake: search the entity name plus "scam", "review", or "complaint" — *after* checking neutral existence first, so you're not biasing the prior.

## Reading authority signals

The v2 prompt distinguishes **borrowed** from **referenced** authority. Verification helps cement which is which:

- **Borrowed** authority: name dropped without engagement. Author says "I use Claude for this" but doesn't show what they did with it. Verification: does the author appear anywhere in the named tool's actual community / commit history / customer base? If they're a borrower, you'll find no trace of them in the named entity's orbit.
- **Referenced** authority: the author is engaging with the work substantively. Verification: does the named work corroborate? Does the author show technical depth that would be hard to fake?

A useful diagnostic: borrowed authority typically uses words like "leveraging," "powered by," "built on top of," and "harnessing." Referenced authority typically uses words like "I disagreed with X about Y because Z," or names specific limitations/edge cases.

## Spotting affiliate funnels

Standard funnel architecture:
1. **Hook content** — free post, free PDF, free thread. Optimised for engagement.
2. **Lead magnet** — newsletter signup, "free guide", Discord invite. Captures email/handle.
3. **Tripwire** — small paid offer, often time-limited.
4. **Core offer** — course, signal service, copy-trade bot, premium community.
5. **Backend** — high-ticket coaching, mastermind, "VIP" tier.

Each link in the chain typically lives on a different domain, often white-labelled (Beehiiv, Kit, Skool, Whop). Fetch a few URLs from a piece of content and trace the chain. If every link redirects through `?ref=AUTHOR` you're looking at affiliate revenue, not just brand-building.

Funnel domains have telltale signs: short hostnames optimised for SEO ("pdftrendlabapp.com" type names), generic stock-photo design, no real about page, single CTA above the fold, exit-intent popups.

## When the content is substantive

The skill's calibration on the Simon Willison case is the test: legitimate substantive content can have surface patterns that resemble scam content (a sponsorship banner, a newsletter signup, a "save this" prompt). Verification-via-search differentiates:

- For a real engineer or analyst, you'll find: technical depth across multiple unrelated posts; engagement with named work that holds up; consistent identity across platforms over years; people you'd recognise interacting with them in good faith.
- For a borrower, you'll find: surface-level engagement; identity inconsistencies; a trail that starts and ends in the funnel.

When verification points to substantive content, the Real Pushback section becomes the main act. The reader doesn't need a fraud verdict — they need the sharpest intellectual challenge to the argument. Spend more time finding the load-bearing weakness in the actual argument, less on forensic flags.

## Budget guidance

- Light content (short LinkedIn post, single tweet): 3–5 searches.
- Standard content (long LinkedIn post, X thread, blog post): 5–10 searches.
- Heavy content (long-form article, video transcript with many specific claims): 10–15 searches.
- Stop at 20. If you're past 20 and the picture isn't clear, the remaining items belong on the verification checklist for the user.

The goal is decisive evidence on the checkable claims, not exhaustive research. A few decisive searches beat many ambiguous ones.
