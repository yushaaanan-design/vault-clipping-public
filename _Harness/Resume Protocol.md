---
tags: [harness, resume]
up: "[[README]]"
---
# Resume protocol (read this first after a /clear)

Central harness (global preferences, vault registry, cross-project lessons): `C:\OBSIDIAN VAULT\Codebase and learning\Harness\README.md`. Read its Preferences first.

Goal: be productive in two minutes with ZERO knowledge of the old chat. Read, in order: this note, [[_Project/STATE]], the last 15 lines of [[_Project/run-log]], [[Preferences]], then [[Lessons]] only when something fails.

## What is running (as of 2026-10-22 about 7:30 AM)
- **Study cycle** `python -X utf8 C:\dev\clipping\study\cycle.py` (detached process, log `C:\dev\clipping\study\cycle.log`). Reads `study/queue.tsv` (576 ids: 6 given, 22 flop/mid, 195 own top, 353 third-party). Writes per clip to `study/data/<id>/` (meta.json, comments.json, features.json, sheet.jpg, analysis/) and one line to `study/features.jsonl`; `study/done.txt` is the resume list; `study/failed.tsv` the failures; a `study/STOP` file means YouTube blocked it (stop, tell the user, do not evade).
- Check it: `tail study/cycle.log`, `wc -l study/done.txt`, is a python process running `cycle.py`? (`Get-CimInstance Win32_Process | ? CommandLine -match cycle.py`).
- Restart if it died with no STOP file: `cd C:\dev\clipping\study; python -X utf8 cycle.py > cycle.log 2>&1` in the background (it skips finished ids). If it died because of memory, say so first, do not hammer it.
- A scheduled wake-up checks hourly (prompt describes the aggregate step). If the session was cleared, recreate the check with ScheduleWakeup or just look yourself.

## What to do when enough clips are done (120+, then at the end)
1. Aggregate from `features.jsonl`, `meta.json`, `comments.json`: views vs duration, cuts, face %, first-words, by tier (own_top / outside_top / flop / mid). `split_screen_share` is about 1.0 everywhere and does NOT discriminate.
2. Comments: top-liked comments, word and phrase frequency, in-jokes. Never store usernames.
3. Look at a SAMPLE of `data/<id>/sheet.jpg` (about 10 per tier) with the Read tool to understand layout and story. No per-clip write-ups.
4. Update: [[Formats/Format Catalog]] (evidence levels), [[Formats/Format Trends]] (new dated snapshot), [[Viral Library/viral-patterns]], [[Jynxzi/Jynxzi Playbook]]. Label FACT / USER / INFERENCE.
5. At the very end of the cycle: delete leftover frames (keep sheet.jpg, meta.json, comments.json, features.json). Destructive: state the facts first.

## Pending for the user (do not do for them)
- (done 2026-10-22) REA and Agent Reach are installed; restart Claude Code once so the REA MCP loads.
- Delete `C:\Users\yusha\Downloads\cookies.txt` (an all-sites cookie export).
- Decide rights and permission for Jynxzi footage and how clipping earns ([[Research/platform-rules]]).

## Not started, waiting for the user
Telegram content-analysis bot, ManiClips test on a user video, more streamers, the real automatic clipper (needs the format and virality findings first).

## STATUS 2026-10-22 (later): the user said GO for 25 + 25. WAVE 1 (top 25 own-channel clips) is DONE: Viral Library/Wave 1 working table.md + Wave 1 Top 25 Own Channel.md; catalog, design systems, trends and playbook updated. NEXT: WAVE 2 = top 25 OUTSIDE (third-party) clips by views once the cycle has reached them (outside_top follows own_top in the queue); same method: read each sheet.jpg frame by frame, one compact row each into Wave 2 working table.md, then a synthesis comparing inside vs outside. The user allows reading while the cycle keeps collecting; if RAM or VRAM gets too high, data gathering has priority; do not stop. The hourly wake-up only checks the cycle.

## Wave plan (REVISED 2026-10-22, user: "analyze top 50 of his clips and top 50 of outsiders' clips; do the fundamental frame by frame analysis so I can understand formats, structure, hook, design, text, positioning")
- The old plan (top 100 + clustering first) is CANCELLED. The user wants the fundamental, by-eye analysis, the way the first 6 clips were read.
- **Wave 1 = top 50 clips by views on Jynxzi's own channel.** For each: read `study/data/<id>/sheet.jpg` (one image per second), `meta.json` (title, views, duration), `features.json` (first words, cuts), top comments from `comments.json`. Record ONE compact structured row per clip in `Viral Library/Wave 1 working table.md` (hook in the first 3 s, layout/zones, caption style and position, structure beats, text overlays, what the top comment quotes). This table is the working evidence, not prose notes; write it after every batch of ~8 clips so progress survives a /clear.
- **Then synthesize** from the table: formats, hook types, design/positioning patterns, with counts. Update Format Catalog (evidence levels, new F08+), Design Systems, Format Trends snapshot, Jynxzi Playbook, patterns note. FACT / SEEN / INFERENCE labelled.
- **Wave 2 = top 50 outside (third-party) clips**, same method, then compare inside vs outside.
- Automatic measurements (features.json) are a cross-check only; `split_screen_share` is unreliable.
- Early evidence from hand-read clips (anecdote): a 58 s clip got 22M views, so "short wins" (H1) is not safe; the flop was a busy 18 s meme edit with generic comments.

- 2026-10-22: Wave 1 AUDIO synthesis is DONE (Wave 1 note section 10, Clip Anatomy section 7). cycle.py now measures audio for every new clip (audio.json + audio_* in features.json); study/audio_backfill.py did the first 25. Remaining wake-up tasks: Wave 2 only.

- 2026-10-22: Wave 2 pool = Shorts tabs of the outside creators (study/channel_shorts.tsv, 479 Jynxzi-titled Shorts, top 120 queued FIRST). Wave 2 starts when 25 outside_top clips have meta.json. The cycle was restarted several times; each restart is safe (done.txt).

## NEXT ACTIONS after the 2026-10-22 /clear (written 08:30 AM, read this first)
- The study cycle is a detached process (`python -X utf8 cycle.py`, log `C:\dev\clipping\study\cycle.log`). It keeps running when the chat is cleared. Check it: `tail` the log, `wc -l study\done.txt`, no `study\STOP` file, process alive (`Get-CimInstance Win32_Process | ? CommandLine -match cycle.py`). If it died with no STOP file, restart it (safe, resumes from done.txt). If STOP exists: YouTube blocked it; tell the user, do not evade.
- The scheduled wake-up checks may be lost with the /clear. Re-arm one with ScheduleWakeup (900 s) or just check yourself.
- Queue order now: top 120 outside creators' Shorts (channel Shorts tabs, study/channel_shorts.tsv) FIRST, then the rest (own top clips, remaining outside, flops/mid). `study/queue_before_reorder.tsv` is the original order.
- DONE: Wave 1 (top 25 own channel, read frame by frame) incl. audio; Clip Anatomy note, Format Catalog (F05-F13), Design Systems, Trends, Playbook updated; Business.md has Trading (row 6) and the two 3D segments.
- TODO Wave 2: when 25 outside_top clips have meta.json + sheet.jpg (count them), write `study/wave2_top25.json`, read each `data/<id>/sheet.jpg` frame by frame (batches of 3-4, Read tool), one compact row per clip into `Viral Library/Wave 2 working table.md` (columns of the Wave 1 table + audio numbers: first 3 s vs typical level, peak seconds, loudest second position, silence share), then `Viral Library/Wave 2 Top 25 Outside.md` (inside vs outside comparison) and update Clip Anatomy, Format Catalog, Design Systems, Trends, Playbook, Lessons, run-log. Python heredocs must be alone in their Bash call.
- Known: audio is measured (signal), not listened to; the framing numbers in features.json are unreliable except face area; the cycle measures audio for all new clips.

## NEXT ACTIONS 2026-10-23 night (user: "context from Obsidian and folder, not chat"; write every analysis to disk)
- GOAL (user): store every format, hook, layout, caption style and positioning in a database so we can later learn what performs and what does not (machine-learning style training), then make clips like the good ones. Measure the hook and everything else.
- DATABASE: C:\dev\clipping\db\clips.db. Table reads = by-eye label per clip (clip_id, streamer, side, views, seconds, hook_type, hook_text, layout, caption_style, structure, format_id, emotion, read_by, read_at, note). Table measures = numbers from features.json for all 1,065 clips (cuts, cuts_first3, first_word_s, words_per_sec, face_area_pct, split_screen_share, audio_first3_vs_median, audio_loudest_second, first_words, hook_question, hook_digit). View training = reads joined to measures. Export db\training.csv. Auto note Formats\Format Library (auto).md.
- LOOP PER BATCH: 1) python -X utf8 -I C:\dev\clipping\db\pick.py <streamer> <n_own> <n_outside> (lists unread top clips) 2) Read each C:\dev\clipping\study\data\<id>\sheet.jpg 3) write a JSON list of rows with keys id, hook_type, hook_text, layout, caption, structure, format, emotion, note and run python -X utf8 -I C:\dev\clipping\db\ins.py <file.json> 4) after a streamer: python -X utf8 -I C:\dev\clipping\db\build_training.py 5) log in run-log. Reuse existing format and hook_type names (see the Format Library) before inventing new ones.
- STATUS: first pass done for adinross, buddha, caedrel (8), caseoh_, gofns (2), hasanabi, ironmouse (2), lacy (3), ohnepixel, payo, pikabooirl, sodapoppin (2), summit1g (2), theburntpeanut (2), xaryu, stableronaldo (1). 53 clips read, 16 streamers. TODO: xqc (own channel in DB is CS2 guides, wrong channel; outside e91M0XLX7Jw, CdxejL6SmbE), kaicenat, zackrawrr (no CSV), then deepen every streamer toward 25 own + 25 outside, then read flops and mid-range clips of the study queue as the control group, then compare within each streamer (rank inside the streamer, views are not comparable across channels).
- KNOWN DATA GAPS: payo and buddha outside rows hold unrelated videos (Bollywood songs, religion); 6IC23P_24v8 is a music video (excluded); sheets cannot show tone of voice (audio is only measured, not listened to).
- UPDATE 2026-10-23 late: 78 clips read, tools added: db\measure_hooks.py (run after build_training.py; writes Formats\Hook Measurements (auto).md). pick.py accepts a 4th argument low to list the lowest-viewed clips (control group). Flop and mid tiers: 12 flop + 10 mid in study\data (tier field in features.json), 6 flops + 2 mids read so far.

- UPDATE 2026-10-23 late: 86 clips read. Findings in Formats\Findings so far (hand-written).md (open questions listed there, section 6, are the next work). Hook measurement script: db\measure_hooks.py.

- UPDATE 2026-10-23 late: reads has 167 rows (51 are Wave imports labelled wave-unlabelled, to relabel). Strongest measured contrast so far: Jynxzi flop vs hit speech density (Findings 2c). Exclude payo/buddha outside rows and 6IC23P_24v8, iR_1V-rUMuA (music videos) from any training use.

- UPDATE 2026-10-23 end of night: reads 183 rows. Next: continue by picking with db\pick.py (own top, outside top, and the low tail with the 4th argument low), 8 sheets per batch, ins.py, build_training.py, measure_hooks.py, then log. Findings so far are in Formats\Findings so far (hand-written).md; market note Research\market-analysis-part3.md.
- UPDATE 2026-10-23 night end: reads 256 rows across 19 streamers (Jynxzi 65, others 5-20 each). Label findings so far: Findings 2e. Keep looping: pick.py (own/outside/low), read sheets 8-12 at a time, write the JSON with the Write tool (a heredoc with apostrophes breaks Bash; the GateGuard hook asks for facts on the first write of each new file, state them and retry), ins.py, build_training.py, measure_hooks.py, log.

- AUDIO GAP (user, 2026-10-23: "you have never listened to the audio?"): confirmed. Per clip we only keep audio.json (per-second loudness) and first_words / last_words from whisper; full transcripts were not saved and nobody listened. Fix TODO: re-run faster-whisper on a sample of clips (download audio only) and save full timestamped transcripts into the db (table transcripts), then add speech labels (joke type, hook line, payoff line). Claude cannot hear sound; it can only read transcripts.
- RUNNING (started 2026-10-23): db\transcribe_reads.py in the background; check db\transcribe.log; restart with: cd C:\dev\clipping\db; python -X utf8 transcribe_reads.py (skips finished clips).

- TARGET 2026-10-23: about 2,000 read clips (see run-log: How many clips are enough). Transcription runs in background (about 1 clip/minute on CPU).
- UPDATE 2026-10-23 04:10: transcribe_reads.py now uses the whisper small model on CPU (about 16 s per clip, about 85 minutes for the rest); large-v3-turbo was 1 clip a minute. Restart: cd C:\dev\clipping\db; python -X utf8 transcribe_reads.py (resume-safe).
