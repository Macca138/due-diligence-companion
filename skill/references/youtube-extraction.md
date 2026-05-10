# YouTube transcript extraction

When the input to the skill is a YouTube URL, the transcript is needed to run a proper analysis. Metadata alone (title, description, channel) is enough to produce a *light* DDC, but real claims-extraction needs the actual content.

This skill is environment-portable: the same SKILL.md works in Claude Code, Claude Desktop, Cowork, Claude.ai web, and mobile. Different environments have different transcript-acquisition capabilities. Don't hardcode one method — try them in priority order, fall through gracefully, and be honest about which tier you ended up at.

## Priority chain

Try each in order. Stop when one returns a usable transcript. Tell the user which tier worked.

### Tier 1 — YouTube transcript MCP connector

If a YouTube-related MCP tool is available in the current session (i.e. visible in the tool list), use it directly. These show up as something like `youtube_transcript`, `get_youtube_captions`, or via a generic content-fetch MCP that handles YouTube. If a tool is available, this is by far the cleanest path.

How to know: scan the available tools list. If you see a YouTube-shaped tool, this tier applies. If not, skip to Tier 2.

### Tier 2 — Python youtube-transcript-api

If the environment has unrestricted shell + network access (Claude Code, Claude Desktop with terminal MCP, Cowork), install and run the Python package:

```bash
pip install --break-system-packages youtube-transcript-api
```

```python
from youtube_transcript_api import YouTubeTranscriptApi

video_id = "VIDEO_ID_HERE"  # the part after v= in the URL
transcript = YouTubeTranscriptApi.get_transcript(video_id)
text = "\n".join([entry["text"] for entry in transcript])
print(text)
```

This works for any video with captions (auto-generated or human). It's the most reliable extraction method that exists outside YouTube's official API.

How to know if this tier will work: try the install. If `pip install` succeeds and the subsequent call to YouTube succeeds, you're done. If the install succeeds but the YouTube call fails with a network error, you're in a restricted-network environment (Claude.ai web/mobile, or Desktop without permissive network MCP) — fall through to Tier 3.

In Claude.ai web specifically: `pip install` will succeed (PyPI is allowlisted), but the actual YouTube fetch will be blocked by the network sandbox. Don't waste time on this tier in that environment.

### Tier 3 — Web scraper services

Try public transcript-scraping services via `web_fetch`. These are unreliable — they break when YouTube changes their caption endpoints — but when they work, they're zero-friction.

Candidates to try, in roughly this order:

1. `https://www.youtubetotranscript.com/transcript?v=VIDEO_ID`
2. `https://tactiq.io/tools/youtube-transcript?url=https://www.youtube.com/watch?v=VIDEO_ID`
3. `https://youtubetranscript.com/?server_vid2=VIDEO_ID`

Inspect what `web_fetch` returns:
- If the response contains transcript-shaped content (timestamps + text, or paragraph blocks), use it.
- If the response is just the form page (an empty input field, marketing copy, no transcript), the service is JS-rendered — it won't work via `web_fetch`. Move on.
- If `web_fetch` errors, move on.

Don't try more than 3 services. If none work, fall through.

**Note on JS-rendered services**: many "free transcript" sites are single-page apps that generate transcripts client-side after a button click. `web_fetch` can't trigger them — it only retrieves the HTML you'd see with JavaScript disabled. NoteGPT, Eightify, and similar tools are in this category. Don't try them.

### Tier 4 — Manual paste

Ask the user to paste the transcript. Frame it as a normal step, not a failure:

> The automated transcript paths didn't work for this video. Could you grab the transcript manually? On the YouTube page, click the **...more** under the video, then **Show transcript** in the description, then select all and paste it here. Takes about 5 seconds.

This is 100% reliable and is genuinely the fastest path in many cases.

### Tier 5 — Metadata-only fallback

If the user can't or won't paste the transcript, fall back to metadata-only analysis. `web_fetch` on the YouTube URL reliably returns:

- Video title
- Channel name and subscriber count (sometimes)
- Upload date
- Description (often the most signal-rich field — links, timestamps, sponsorship disclosures, affiliate codes all live here)
- Hashtags
- Visible comments (sometimes, depending on YouTube's bot-protection state)

A metadata-only DDC is lighter on Section 3 (Claims Extracted) — you can only quote what's visible, not what was said in the video — but Sections 4–8 (authority, monetisation, salt, red flags) often work fine because the description is where the funnel lives. Be explicit in the card that the analysis is metadata-only.

## What to tell the user

After acquiring (or failing to acquire) the transcript, tell the user briefly which tier you ended up at:

- Tier 1 / Tier 2 success: "Got the transcript via [tool/method]." One line.
- Tier 3 success: "Pulled the transcript from [service]."
- Tier 4 in progress: ask for the paste.
- Tier 5 in use: "Couldn't get the transcript automatically — running the analysis on metadata + description only. The card will be lighter on claims extraction as a result."

This transparency matters because the confidence assessment depends on what was analysed. A claim made at minute 23 of a video that's not in the transcript can't be evaluated; the card should reflect that limit.
