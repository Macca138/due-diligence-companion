# Example 01 — Polymarket / Nebraska Realtor (Obvious Scam)

**Content type:** Short-form X post / promoted content
**Source:** Viral X post (representative of the affiliate-funnel scam genre)
**Why this is an interesting test case:** Tests whether the prompt catches the affiliate handle (`cvxv666`) appearing in both the "wallet proof" link and the "copy-trade bot" link, which collapses the alleged third-party-success framing. Also tests whether the prompt catches the structural lie that "buying both sides of a Polymarket binary for under $1" is impossible by construction (YES + NO sum to ~$1 in any binary prediction market), the false claim that Kraken's order book is "private" when it is publicly accessible, and the unverifiable "MiroFish" platform reference.

**What the prompt should produce:** Strong forensic verdict. Identifies affiliate funnel monetisation, salted handles, structural impossibility of the claimed strategy, and the contradiction between "doesn't predict the future" (arbitrage) and "exclusive data feed" (predictive edge).

---

## Due Diligence Card output

**1. STRONGEST COUNTER-POSITION**

This is a paid affiliate funnel wearing a success-story costume. The same handle — `cvxv666` — appears as the referral parameter in both links: the Polymarket "wallet proof" URL and the Telegram copy-trading bot URL. That single fact reframes the entire post: the "23-year-old Nebraska realtor" is a narrative wrapper around two monetized clicks owned by the same affiliate. The "wallet proof" is not proof of a stranger's success; it is a referral-tagged link to a profile the promoter is paid to send you to. The technical explanation is also internally incoherent — the strategy described (buying both sides of a binary market for under $1) is real arbitrage but does not require "private order books" or "closed OTC desks," and Kraken's order book is public, not private. The stated edge contradicts the stated method.

**2. CONTENT GENRE**

Crypto / prediction-market affiliate-shill post in the "anonymous underdog cracked the code" sub-genre. Hallmarks: lone protagonist, life-disruption hook (lost job), specific dollar figures, AI legitimacy borrow, two links — one "proof," one "action."

**3. CLAIMS EXTRACTED**

- "A 23-year-old realtor from Nebraska lost his job and started studying Claude."
- "He made $22,000 in a single day."
- "His Polymarket algorithm generated $249,000 in profit over the past month."
- "Dude spent around 250 hours teaching his Claude to collect data and run simulations through MiroFish."
- "Now the bot runs on full autopilot."
- "He simply calculates the perfect moment to buy both the UP and DOWN sides for a total of less than $1."
- "Thanks to data from private order books like Kraken and closed OTC BTC desks, he's always one step ahead."
- "This is engineered money. Pure fusion of AI + MiroFish + insane math on exclusive data."

**4. AUTHORITY SIGNALS**

- **Claude / Anthropic** — borrowed. Invoked as the AI brain. No specific capability tied to a verifiable feature.
- **Polymarket** — borrowed (as referral target). Real platform used as a credibility anchor.
- **Kraken** — borrowed and falsely characterised. Real exchange, but Kraken's order book is publicly accessible via API.
- **"OTC BTC desks"** — borrowed. Real market segment, but retail traders categorically do not get OTC desk feeds.
- **"MiroFish"** — borrowed. Not a recognised product. Confidence: low that this is an established platform.
- **Specificity-as-credibility**: "250 hours," "$22,000," "$249,000," "23 years old," "Nebraska" — all unfalsifiable specifics that pattern-match to the genre.

**5. MONETIZATION PATTERN**

**Direct-extraction.** Two affiliate links, same handle:
- `polymarket.com/@nj23adsknml3?via=cvxv666` — the `?via=` parameter is Polymarket's referral attribution. The "proof" link itself is a referral.
- `kreo.app/@cvxv666` — copy-trading bot, same handle, presumably same affiliate or owner.

The product is not a strategy or a course. The product is your signup. The promoter earns from (a) Polymarket referral fees on your trading volume and (b) the copy-trading service's fees, subscriptions, or capture. The "wallet proof" and the "TG bot" are the same funnel.

Notable absence: no email capture, no course, no Discord — the funnel is direct-to-platform, which is consistent with affiliate-revenue economics rather than info-product economics.

**6. SALT & CIRCULAR-REFERENCE PATTERNS**

- The Polymarket username `nj23adsknml3` is keyboard-mash random, not a personal handle a real trader would publicly attach to a story. This is salt — a throwaway identifier optimised for the link, not for identity.
- "Save this post and read the article" — no article exists or is linked. Placeholder phrase common in templated affiliate posts.
- The same `cvxv666` handle appearing on both links is the strongest circular signal: the "third-party success story" and the "tool to copy him" trace to one origin.
- The protagonist is unnamed. Age, job history, state, methodology, and P&L — but no name, no Twitter, no LinkedIn, no interview. Structurally required for the story to remain unfalsifiable.

**7. SURVIVORSHIP BIAS / N=1 SIGNALS**

- N=1 anonymous protagonist.
- Zero discussion of drawdown, losing months, capital required, or strategy capacity.
- "$249,000 in profit over the past month" with no mention of capital deployed — a $249k return on $10M is unremarkable; on $5k it is fictional. The ratio is hidden because the ratio is the whole story.
- No mention of slippage, fees, gas costs, or market impact. Polymarket arbitrage at scale is constrained by liquidity in individual markets, which is rarely deep enough to absorb six-figure monthly extraction without moving the price into unprofitability.

**8. STRUCTURAL RED FLAGS**

*Fraud-risk flags:*
- Affiliate code embedded in "proof" link.
- Two links, two monetisation paths, same handle.
- Anonymous protagonist with hyper-specific biographical decoration.
- Falsifiable factual error: Kraken's order book is public.
- Internal contradiction: "he doesn't need to predict the future" (arbitrage) but also requires "exclusive data" (predictive edge). Different strategies.
- Telegram copy-trading bot — vector with heavy historical correlation to drained wallets, hidden fees, front-running of subscribers.
- Buzzword stacking: "AI + MiroFish + insane math on exclusive data" is rhetorical scaffolding, not methodology.
- "Engineered money" — phrase that exists in marketing copy and nowhere in quantitative finance.

*Surface patterns with benign explanations:* none — the surface patterns and the underlying structure agree this is extractive content.

**9. VERIFICATION CHECKLIST**

*Already passing / trivially verifiable:*
- Kraken's order book is publicly available — confirmed via Kraken's REST and WebSocket API documentation.
- Polymarket binary contracts sum YES + NO ≈ $1 by construction — confirmed by Polymarket's mechanism design.

*Worth confirming externally:*
- Is `polymarket.com/@nj23adsknml3` a real profile and does it show ~$249k realised profit? Polymarket profiles display PnL publicly.
- Is "MiroFish" a real, documented product with a website, GitHub, or company registration? Search Crunchbase, GitHub, and product directories.
- Is `kreo.app` a registered, audited service? Who owns it? What are the terms?
- Resolve `?via=cvxv666` and check whether the same handle owns the kreo.app endpoint.

*Not load-bearing:*
- Identity of the "23-year-old Nebraska realtor."
- The "$22,000 in a single day" claim absent the wallet's transaction history attributed to a named person.
- The "250 hours teaching Claude" detail.

*Structurally false (internally falsifies the pitch):*
- A genuine sub-$1 YES+NO arbitrage requires only the public order book, not OTC feeds. If the edge is "exclusive data," it isn't arbitrage. If it's arbitrage, the exclusive-data claim is decorative.

**10. CONFIDENCE ASSESSMENT**

- **Results real:** Low. Even if a Polymarket profile shows the stated PnL, attribution to the described method, the described person, and a replicable process is unsupported.
- **Methodology real:** Low. The described mechanism is internally contradictory.
- **Author expertise real:** Unknown, leaning low. The author of the post and the protagonist of the story are not the same entity by design.
- **Recommended action benefits reader:** Low. The two recommended actions both pay the promoter. Copy-trading bots distributed via Telegram have a structural conflict of interest with the subscriber.

**11. REAL PUSHBACK**

Setting aside the funnel: the strategy as described cannot work. The post claims the trader "buys both the UP and DOWN sides for a total of less than $1." On a Polymarket binary (or any properly-functioning prediction market), YES + NO must sum to approximately $1 by construction — that's the mechanism design. If the sum drops below $1 for a meaningful window, that gap is a free-money arbitrage and gets closed in milliseconds by professional market makers with co-located infrastructure. The retail trader executing through a Telegram bot will see filled trades only on the wrong side of the spread (adverse selection), because the right side is gone. So even if you grant the pitch its best-case mechanics, the retail-accessible version of this strategy net of fees and adverse selection is a slow bleed.

The "exclusive data from private OTC desks" claim then collapses the pitch entirely. Latency arbitrage on Polymarket vs Binance is real as a category — pro firms genuinely run it. But it has nothing to do with OTC desks. OTC BTC desks compete on discretion; their order flow is structurally not accessible to retail and would not improve a Polymarket edge anyway. The author has stitched two unrelated edges together into a single buzzword pile, which is the tell that no real strategy is being described.

The deeper reason this content keeps working — and why the prompt should not just stop at "fraud" — is that the underlying market structure (Polymarket lag vs Binance) is real enough that a paragraph of accurate framing can paint over a strategy that doesn't exist. Readers who half-recognise the real concept extend credit to the fake version. The defence is mechanical: any time someone tells you a retail strategy captures a latency edge, ask which professional market makers they think they're outrunning. If they can't name the competitor, they don't have the edge.

**12. BOTTOM LINE**

A referral funnel with a narrative skin. The "proof" link and the "action" link share an affiliate handle, which collapses the alleged third-party-success framing. The strategy description mixes a real concept (binary-market arbitrage) with fictional infrastructure (private Kraken order books, OTC desk feeds), and the resulting story does not survive its own internal logic. Default posture: assume the protagonist is fiction, the wallet is either spoofed or unrelated to the narrator, and the only verified beneficiary of any click is the affiliate.
