# Example 02 — Coinman2 / 28 Tools Article (Sophisticated Scam)

**Content type:** Long-form listicle / "alpha drop" article
**Source:** Crypto Twitter "28 tools under the hood of bot that made $1M on Polymarket" article
**Why this is an interesting test case:** Tests whether the prompt catches sophisticated salt patterns — specifically self-cited GitHub repos by `cvxv666` and `txbabaxyz` recommended inside the same article that promotes the `kreo.app/@cvxv666` Telegram bot. Also tests whether the prompt distinguishes the kernel of real edge (Polymarket-vs-Binance latency arbitrage is a real category) from the structural impossibility of capturing it via a copy-trading subscription. This is the hardest detection job in the calibration suite — the article uses real concepts, real public repos, and plausible numbers as scaffolding around fabricated authority and a self-recommendation funnel.

**What the prompt should produce:** Catches both self-citation patterns (cvxv666 and txbabaxyz). Identifies the contradiction between latency arbitrage as a category (real) and capture via copy-trade bot (structurally impossible, since copies arrive after the leader). Flags the unverifiable "Claude vs OpenClaw 48-hour controlled experiment" as fabricated authority. Notes that the article points at someone else's wallet rather than the author's own.

---

## Due Diligence Card output

**1. STRONGEST COUNTER-POSITION**

This is a referral-funnel disguised as a technical breakdown. The "28-tool stack" is decoration; the actual product is three things stacked behind it: a Polymarket signup with the author's referral tag (`?r=antopotoshka`), a Telegram copy-trading bot (`kreo.app/@cvxv666`), and follower acquisition (`@antpalkin`). The GitHub handle `cvxv666` who runs the copy-trading service also authors one of the "recommended" repositories in the stack — that is a circular reference, not an independent recommendation. Every concrete instruction in this piece routes to a place where the author earns money or attention. The trading thesis — buying mispricings between Polymarket and Binance during 2.7-second pricing lags — is real as a category but is precisely the kind of latency-arbitrage edge that a retail reader executing through a Telegram copy-bot has approximately zero chance of capturing, because by the time the signal reaches them the trade is already settled. The "tonight you can make $1,000" framing is mechanically incompatible with the mechanism the article describes.

**2. CONTENT GENRE**

Crypto-Twitter "alpha drop" listicle. Subgenre: backronymed tool-stack post. A near-identical structural template (six layers, twenty-something repos, one hero wallet, two CTAs at the bottom) circulates monthly across Polymarket, Hyperliquid, and memecoin niches.

**3. CLAIMS EXTRACTED**

*Quantitative claims (verbatim, not endorsed):*
- Wallet `0x55be7aa03ecfbe37aa5460db791205f7ac9ddca3` / `@coinman2` has "$1,003,450 PnL" across "3,062 predictions," joined Nov 2024, biggest win "$113.8K."
- Polymarket "weekly volume exceeded $2 billion in early 2026."
- Polymarket pricing lag was "12 seconds" in 2024, compressed to "2.7 seconds" in Q1 2026.
- "Claude: +1,322% return. OpenClaw: fully liquidated" over 48 hours from $1,000 starting capital.
- Bots generated "approximately $206,000" vs humans "roughly $100,000" in an unspecified tracked period.
- Bot makes "200–500 [trades] per day."

*Mechanism claims:*
- Edge comes from Polymarket lagging Binance.
- Sizing via Kelly Criterion, execution via CLOB API, sub-50ms latency on Binance WebSocket feed.

*Recommendation claims:*
- Reader can replicate "tonight" by copy-trading via `kreo.app/@cvxv666`.
- The 28 listed repositories collectively constitute the stack that produced the $1M wallet.

**4. AUTHORITY SIGNALS**

- **Anthropic / Claude** — borrowed. Invoked as "the primary strategist" with no evidence beyond the assertion. Anthropic has not published anything resembling the cited "controlled experiment."
- **Binance, Polymarket CLOB** — referenced (correctly as a category, used to lend technical legitimacy).
- **Kelly Criterion** — borrowed. Real concept name-dropped without showing it was actually applied or how parameters were estimated.
- **"OpenClaw framework"** — borrowed and likely fabricated. Not recognised as an established framework. A reader cannot reproduce a benchmark against a thing they cannot find.
- **Specific wallet address + on-chain phrasing** — "The blockchain doesn't lie" is rhetorical inoculation. On-chain visibility verifies that trades happened, not that the described strategy caused them, that the wallet is the author's, or that the PnL methodology is honest.
- **GitHub repository roll call** — borrowed. Listing real repos (e.g., `tradingview/lightweight-charts`, `OpenBB-finance/OpenBB`, `QwenLM/Qwen3-Coder`) borrows their credibility. None of these repos endorse the article or the wallet.
- **Unnamed "researchers" and "developers"** — borrowed, fabricated. "Researchers traced the gap." "Developers reverse-engineered the approach within weeks." Zero attribution.

**5. MONETIZATION PATTERN**

**Direct-extraction.** Three monetization vectors, in descending probable revenue order:

1. **Polymarket referral**: `polymarket.com/@coinman2?r=antopotoshka` — `antopotoshka` is the referrer code, paying the author a cut of the new user's fees/volume. Note this is paired with `@antpalkin` as the author's follow handle. The phonetic similarity (anto-/ant-) suggests these are the same person operating under two names.
2. **Telegram copy-trading bot**: `kreo.app/@cvxv666` — almost certainly a paid subscription, fee-per-trade, or revenue-share model. Crucially, copy-trading services route the *copier's* capital through trades that are by definition *later* than the leader's, eliminating any latency edge the article claims is the source of profits.
3. **Follower acquisition**: `@antpalkin` — building an audience to monetize via future drops.

The actual product is not a strategy. The product is *you*, the reader, signing up to one of three funnels.

**6. SALT & CIRCULAR-REFERENCE PATTERNS**

This is the most telling section.

- **Self-citation in the "stack"**: `github.com/cvxv666/ClaudeAgentOneClick` is listed as a recommended tool. The handle `cvxv666` is the same handle as the copy-trading service `kreo.app/@cvxv666` promoted twice in the article. The author is recommending their own repo as part of an "objective" stack roll-up.
- **Probable second self-citation**: `github.com/txbabaxyz/mlmodelpoly` ("Binance Collector") and `github.com/txbabaxyz/polyrec` are both authored by the handle `txbabaxyz`. Two entries in a 28-item list from the same single-author handle is a structural tell that the list is padded with the author's (or an associate's) own repos rather than curated on merit.
- **Referral-code salt**: `?r=antopotoshka` is appended to a wallet-profile link where the referral parameter has nothing to do with viewing the wallet — it is hidden inside what reads as a "look at this trader" link.
- **Two-name structure**: `antopotoshka` (referral) + `@antpalkin` (follow) + `cvxv666` (copy-bot + repo). Three handles, plausibly one or two operators. Worth checking whether all three resolve to the same person.

**7. SURVIVORSHIP BIAS / N=1 SIGNALS**

- **One wallet, post-hoc selected**: Polymarket has hundreds of thousands of wallets. Picking *the* winner after the fact and reverse-engineering a story around it is the textbook definition of survivorship bias. The article admits this implicitly: "When traders first saw the growth trajectory on-chain..." — i.e., the wallet was identified *because* it had already won.
- **"Claude vs OpenClaw" benchmark is N=1 vs N=1 over 48 hours**: Even if the experiment occurred, a single 48-hour run on a single $1,000 stake is statistically meaningless. Crypto-prediction markets routinely produce 10x+ moves on individual contracts, so a +1,322% / -100% split between two runs is well within noise.
- **"Bots vs humans, $206K vs $100K"**: Selection criteria for which bots and which humans is not stated. Unfalsifiable.
- **No drawdown, no sample period, no Sharpe**: A claim of "$1M PnL across 3,062 predictions" with no mention of maximum drawdown, win rate, average bet size, or time period is a profile of the result, not the process.

**8. STRUCTURAL RED FLAGS**

*Fraud-risk flags:*
- "Bookmark this" / "SAVE THIS POST" — engagement-bait framing; useful posts don't need to beg.
- "0.01% actually try… and eat" — cult/elite-tier framing engineered to make scepticism feel like cope.
- Pre-empting the "fake" objection ("crypto Twitter said fake. But the blockchain doesn't lie.") is a standard inoculation against the correct objection.
- "Make your first $1,000 tonight" + a 28-tool stack containing repos most readers cannot deploy is internally contradictory.
- The article never states *the author's own* PnL. It points at someone else's wallet.
- Two CTAs with identical links suggest A/B-tested funnel optimization, not a writeup.
- "Then they asked Claude to rebuild it from scratch" is narrative filler with no underlying claim that can be checked.
- 28 repositories with no architectural diagram showing how they actually compose. The list is a noun pile.

*Surface patterns with benign explanations:* listing public GitHub repos (OpenBB, lightweight-charts, etc.) is fine in itself — these are real, useful tools. The fraud signal is not the listing; it is the embedding of the author's own repos within the same list.

**9. VERIFICATION CHECKLIST**

*Already passing / trivially verifiable:*
- Polymarket runs on Polygon as a CLOB with on-chain settlement (confirmed via Polymarket's documentation).
- `tradingview/lightweight-charts`, `OpenBB-finance/OpenBB`, `QwenLM/Qwen3-Coder` are real repositories with significant star counts.
- Polygon block times average ~2 seconds, putting a hard floor on Polymarket settlement latency.

*Worth confirming externally:*
- Look up `0x55be7aa03ecfbe37aa5460db791205f7ac9ddca3` on Polymarket / Polygonscan. Confirm: account creation date, total trade count, realized vs unrealized PnL, drawdown profile, whether PnL is concentrated in a small number of bets.
- Resolve `?r=antopotoshka` and `@antpalkin` and `cvxv666` and check whether they are the same operator across X, GitHub, and Telegram.
- Check whether `github.com/cvxv666/ClaudeAgentOneClick` exists, what it contains, whether stars/forks/commits suggest a working tool or a placeholder.
- Check `github.com/txbabaxyz/*` repos for the same.
- Verify Polymarket weekly volume figure for early 2026 via Dune dashboards or Polymarket's own analytics page.

*Not load-bearing:*
- The exact figure for Polymarket pricing lag (12s → 2.7s).
- Specific repo star counts.

*Uncheckable by design:*
- The "Claude vs OpenClaw controlled experiment" — no paper, no preprint, no lab cited. "OpenClaw" itself is unverified as an established framework.
- "Bots generated ~$206K vs humans ~$100K" — universe undefined.
- Sub-50ms latency claim about a third party's bot.

*Structurally false / category errors:*
- The implied claim that copy-trading via Telegram bot captures the same edge as a co-located latency-arbitrage operation. Latency arbitrage by definition cannot be copied profitably to a downstream subscriber.
- The implied causal link from "here are 28 repos" to "this wallet made $1M." Listing tools is not evidence they were used.

**10. CONFIDENCE ASSESSMENT**

- **Wallet exists and shows large positive PnL**: moderate-high. On-chain wallets matching this profile are common to find; the specific address is checkable.
- **The described strategy (Polymarket-vs-Binance latency arb) is what produced the wallet's PnL**: low. Asserted, not shown.
- **The 28-tool stack reflects the wallet's actual implementation**: low. No causal link offered.
- **Author's expertise as a prediction-market quant**: low. The piece is a list and a narrative, not analysis.
- **Recommended actions benefit the reader**: low. Both recommended actions pay the promoter.
- **Author and copy-bot operator (`cvxv666`) are the same operator or coordinated**: moderate-high. The same handle appears as both a "recommended repo" author inside the stack and as the destination of the copy-trading CTA.

**11. REAL PUSHBACK**

Setting aside the funnel structure: the article describes a real category of edge — latency arbitrage between Polymarket and Binance — and then proposes a delivery mechanism (Telegram copy-trading) that is mechanically incompatible with capturing that edge. If the leader's bot fires on a 2.7-second pricing window, the copier's order arrives after the window has closed, after the spread has corrected, and after the professional MMs have already taken the fill. What the copier actually buys is adverse selection: their orders fill only when they're on the wrong side of the trade, because the right side has been taken by faster participants.

This is the structural defeater of the entire genre, not just this article. Any "copy my latency arb" pitch is making a claim that violates the mechanism it relies on. The fact that the article describes the edge in technically accurate terms (Polygon block times, CLOB API, Kelly sizing) makes it more dangerous, not less — the technical accuracy launders the structural impossibility.

The other underreported issue: even the leader's bot, if it exists, faces a capacity ceiling that the article never mentions. Polymarket short-duration crypto contracts have shallow order books; at any given moment a few thousand dollars of size can move the price into unprofitability. A bot extracting $1M of PnL across 3,062 predictions is averaging ~$330/trade — which is plausible for a small operation but not for a strategy you can scale by adding subscribers. Adding copiers behind a leader bot doesn't increase capacity; it dilutes it. So even if the leader's PnL is real, the product being sold to the copier is structurally a smaller share of a smaller pie, net of fees.

**12. BOTTOM LINE**

The article is structured as education and functions as customer acquisition. The trading thesis it gestures at is real as a category; the evidence that *this* article's author or *this* wallet's owner is profitably executing it is absent. The single most informative fact in the piece is that one of the "objectively recommended" GitHub repos in the 28-tool stack shares a handle with the Telegram copy-trading service the article tells you to sign up for — that is the article telling you what it actually is. Treat the 28-tool list as a decorative surface, not a blueprint.
