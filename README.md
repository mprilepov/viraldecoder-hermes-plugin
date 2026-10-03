# ViralDecoder for Hermes Agent

Why short videos go viral, and a script for yours.

This plugin connects Hermes Agent to [ViralDecoder](https://viraldecoder.online) through its
hosted MCP server. Share a link to a public Instagram Reel, YouTube Short or TikTok video and
ask Hermes to analyze it: you get the opening hook and its score, why the video spread, and a
script for your own video built on the same structure, plus a description and hashtags. You can
also browse trending short videos by niche and pull up the analyses you have already made.

## What's inside

- `mcp.json` - the hosted ViralDecoder MCP server, `https://viraldecoder.online/mcp`
  (Streamable HTTP, OAuth sign-in).
- `skills/viraldecoder` - a short guide for the agent on calling the tools.

No Python code, no hooks, no background processes.

## Install

```bash
hermes plugins install viraldecoder
```

On the first ViralDecoder tool call Hermes opens a sign-in page in your browser. Sign in with
Google or an email link and click Allow. A free ViralDecoder account is created on first sign-in.

## Plans

The free plan includes 3 video analyses a month; browsing trends and your past analyses
doesn't use them. Paid plans are sold only on viraldecoder.online. When your monthly analyses
run out, the tool says so and links to the plans page.

## What to know before installing

- Network calls: the plugin talks only to `viraldecoder.online`. To analyze a video, the
  ViralDecoder service fetches the single public video you linked through a third-party data
  provider (Apify), extracts frames and audio, and then deletes the video file.
- The trend feed is built from public videos of creators that ViralDecoder tracks.
- Credentials: OAuth tokens are handled by Hermes's own MCP sign-in; the plugin stores nothing.
- Each `analyze_video` call uses one analysis from your monthly plan.
- You can disconnect at any time in ViralDecoder settings, under Connected apps.

Privacy policy: https://viraldecoder.online/privacy · Docs: https://viraldecoder.online/claude ·
Support: support@viraldecoder.online

## License

MIT
