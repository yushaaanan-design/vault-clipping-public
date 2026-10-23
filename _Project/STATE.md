---
tags: [project, state]
up: "[[Index]]"
---
# State: Clipping (own vault since 2026-10-22)

**Goal (user):** automate the whole clipping pipeline: long video in, best short clips out, with hooks and a virality score the user controls. First streamer studied: Jynxzi (Rainbow Six Siege streamer). The user is building a personal understanding of how his community and clips work.

## Decided
- Own vault `C:\CLIPPING VAULT` (notes only). Raw data, downloads and scripts live outside it in `C:\dev\clipping\` (study/ = the cycle, viral-library/ = the first 6 clips).
- ManiClips (free Windows app, installed at `C:\Program Files\Mani Clips`, never launched) is only a reference: it scores segments (speech, scene stability, face, motion) but picks fixed 30/45/60 s windows. We build our own.
- First automated test (8 clips from the 4:50 h Jynxzi stream) was judged "horrible, no virality" by the user and deleted. Lesson: text-only scoring cannot see what is on screen, so we study real viral clips first.
- User's vision: send reels (YouTube, Instagram, other) to a bot; Claude analyses why each works (hook, framing, marketing, the community's personal bond with the streamer) and learns the user's taste. The Telegram bot for Instagram reels already exists (`C:\dev\reels\bot`) and is a SEPARATE project; the content-analysis bot comes later.
- Skills to approve later: Agent Reach (cloned `C:\dev\agent-reach-repo`), REA (cloned `C:\dev\rea-repo\rea`; setup blocked by auto mode, the user must run `! npx -y rea-agents@latest setup --client claude_code --yes`).

## Current job
- Study cycle (`C:\dev\clipping\study\cycle.py`): top 200 hits inside Jynxzi's channel, top 200 outside, plus flops and mid-range. Each clip: download with top comments, frame-by-frame analysis, framing measurements, contact sheet, video deleted. See [[run-log]].

## After a /clear: read [[_Harness/Resume Protocol]] first.

## Where things are
- [[Viral Library/viral-patterns|Viral patterns]]: what the data says so far.
- [[Formats/Format Catalog|Format catalog]] and [[Formats/Format Trends|Format trends]]: the central list of formats that go viral, compared over time.
- [[Jynxzi/Jynxzi Playbook|Jynxzi playbook]]: how this streamer and his community work.
- `Research/`: hooks, virality scoring, segmentation, pipeline design, platform rules (written 2026-10-22 by a research agent; claims tagged sourced / inference / unverified).

## Open (user decides)
- Rights and permission for Jynxzi footage, how it earns (see [[Research/platform-rules]]).
- Which streamers next (user said there will be a few).
- Market analysis (pay, platforms, countries, Bangladesh setup): [[Research/market-analysis]]

## OPEN: the 25 + 25 per-streamer analysis the user asked for (2026-10-22)
- NOT DONE as of 2026-10-22 11:58 PM. Measuring is done (sheets and features in C:\dev\clipping\study\data), but no streamer's sheets have been read and no streamer note exists. Needed per streamer: compact table row per clip (own + outside), one short synthesis, then a cross-streamer comparison. Status words: measured / read / done (see Lessons).

## Direction (user, 2026-10-23, before clearing the chat)
- Goal: the whole clipping pipeline (research, transcripts, data extraction, analysis, later script writing and editing) runs by itself, NOT dependent on an open Claude session. Claude is turned on only to design, review and decide.
- Claude API is not available to the user right now, so the automatic reader must be a local model (Ollama) or a free hosted tier. A new PC is planned: 8 GB VRAM, possibly 32 GB RAM, possibly Linux (dual boot or Ubuntu). Roles and build order: _Project\Pipeline roles.canvas.
- Per-streamer data now exists: C:\dev\clipping\by_streamer\<streamer>.csv (+ _summary.csv), index note Streamers\Streamer Data Index.md. Measured only; the by-eye 25 + 25 reading is still open (section above).
- Streamers differ in style, so analysis is per streamer first, then a central comparison.

## 2026-10-23 progress: 25+25 reading STARTED. Pilot Caedrel 8/38 read, table reads in clips.db, note Streamers\Caedrel.md. Market Part 3 in Research\market-analysis-part3.md.
