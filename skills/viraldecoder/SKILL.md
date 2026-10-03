---
name: viraldecoder
description: How to use the ViralDecoder MCP tools - analyze a public Instagram Reel, YouTube Short or TikTok link (hook, why it went viral, a script for the user's own video), browse trending short videos by niche, and reuse past analyses. Load this before the first ViralDecoder tool call.
---

# Using ViralDecoder

ViralDecoder works on the user's own ViralDecoder account. The first tool call opens a
sign-in page in the browser (Google or an email link); the user approves access once.

## Tools

| Tool | Use it for |
|---|---|
| `analyze_video` | Analyze one public video by URL. Uses one analysis from the user's monthly plan; repeating the same URL does not. |
| `get_analysis` | Result of an analysis by `job_id`: hook and its score, why it went viral, adapted script, description, hashtags, transcript. |
| `my_library` | The user's finished analyses, newest first. |
| `list_niches` | Niche slugs for `trending_videos`. |
| `trending_videos` | Fast-growing videos from the trend feed. `sort`: `hot`, `x_factor` (views vs the author's usual), `views`, `fresh`. |

## How to call them

- `analyze_video` returns the result if it is ready within a few seconds. Otherwise it returns a
  `job_id`: wait 30-60 seconds, then call `get_analysis` with it. Do not call `analyze_video`
  again for the same link.
- Before `trending_videos` with a niche, call `list_niches` and pass a slug from it.
- The analysis is written in the language set in the user's ViralDecoder settings. If it does not
  match the conversation, quote it as returned and offer a translation.
- When the monthly limit is reached, the tool answers with a link to the plans page. Pass the link
  on as is; plans are bought only on viraldecoder.online.
- The connector cannot search all of Instagram, YouTube or TikTok, post anything, change settings
  or delete data.
