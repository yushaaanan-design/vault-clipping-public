---
tags: [formats, findings]
up: "[[Format Library (auto)]]"
---
# Findings so far (written 2026-10-23 night; update as more clips are read)

Source: `C:\dev\clipping\db\clips.db` (table `reads` = by-eye labels, table `measures` = numbers). 86 clips read frame by frame across 19 streamers, including 12 Jynxzi flop/mid control clips. Labels: FACT = seen or measured, INFERENCE = my reading, UNVERIFIED = not tested. Small samples: treat everything as a hypothesis to test, not a rule.

## 1. The measured hook numbers do not explain views (FACT)
Over 1,054 measured clips in 36 groups (same streamer, same side), view percentile versus first-word time, cuts in the first 3 s, first-3-second loudness, question or number in the first words: all |rho| under 0.07 (noise). Only face size (+0.13 pooled, +0.22 on outside clips) and face height (-0.18 outside) show a weak link. See [[Hook Measurements (auto)]]. INFERENCE: among clips that already reached 100K+, what separates them is what the picture and title say, which signal numbers cannot see.

## 2. Jynxzi: flops versus hits, read by eye (FACT, n = 12 flop/mid vs 25 hits in Wave 1)
- 5 of 9 flops use a crude innuendo title with matching all-caps stage-direction captions (*INSPECTS TITS*, *MUTES MIC*, double C, jiggle, man titties). They average about 163K views. Same template (facecam top, game bottom, big caps at the seam) as the 1M+ clips, so the layout is NOT the difference.
- Flop titles promise something the picture does not deliver in the first seconds (Gamer Shower, toxic donation, Reacts to his gyat: the clip shows an unrelated R6 reaction). Hits state a claim that the opening shot shows (compare Wave 1: hacked, dunk, ranked-luck).
- Flops end on or contain a YouTube SUBSCRIBE animation and a meme photo insert (2 clips); one is a 6 s airplane window clip with one gag; one is a busy meme montage.
- Mids (1.5M): the face is cropped at the nose (eyes not visible) or the clip is a plain clutch narration; they still do 10x the flops. INFERENCE: topic and stakes (1v3 clutch, nearly banned) carry them.
- INFERENCE: what separates flop from hit for this streamer is topic and payoff (a visible event the title names), not edit style.

### 2b. Correction after labelling 110 clips (2026-10-23 late)
- The column `title_promise_met` (1 = the first seconds show what the title promises) is now filled for 38 clips. Pooled: promise met 27 clips avg 3.2M views, not met 11 clips avg 1.4M. That gap is CONFOUNDED by streamer (big channels dominate the "met" group). Inside one streamer the median gap is small: Jynxzi met (n=7) 175K vs not met (n=7) 139K; other streamers have 1-2 clips per side. So the title-promise idea is NOT confirmed; it stays a hypothesis. A fair test needs 10+ labelled clips per side inside each of several streamers.

### 2c. Measured: Jynxzi flop/mid (n = 14) versus Wave 1+2 hits (n = 51) (FACT, from `measures`, 2026-10-23 late)
Medians: views 155K vs 9.4M; length 23 s vs 25 s (no difference); cuts 6 vs 7; cuts in first 3 s 0.5 vs 0; first word at 0 s in both; face area 7.2% vs 9.5%; **words per second 2.06 vs 2.91; voiced share 0.67 vs 0.88**. So hit clips are denser in speech (more of the clip has a voice, more words per second); the flops have more quiet gaps. INFERENCE: the flops lean on captions and faces over game audio with less continuous commentary. Caveats: n = 14, the flops are one streamer in one content family (innuendo titles); audio-first-3-seconds was never measured for flops; this does not show cause. Next test: same comparison for other streamers' low-tail clips once each has 15+ read clips.

### 2d. Check over all 422 measured Jynxzi clips (Spearman vs views, FACT)
face_area_pct +0.27, length in seconds -0.31 (shorter goes with more views), audio silence share -0.17, cuts +0.12, voiced_share -0.01, words_per_sec -0.02. So the speech-density gap in 2c does NOT hold as a general trend (rho about 0); it only separates the 14 flops from the hits. What does hold across Jynxzi's whole catalogue: a larger face on screen and a shorter clip go with more views. Still correlation, not cause; the 2c flops are one content family.

## 3. Hook types by average views across all streamers (n small; views not normalised)
- Clips with a stated claim or burned-in title in the first 3 s (title-claim, on-screen-claim, text-headline-curiosity, celebrity-callin) average 5M to 12M views among the read top clips.
- `no-hook-longform` (silent opening, raw stream slice, a menu or a walk) averages about 400K (n = 6) and is the dominant pattern of the outside clips that are uploads of raw stream captures.
- Counter-example: raw stream slices can still reach 15M when the topic carries it (Last of Us rabbit scene, Rekkles Reddit thread), so the topic outranks polish for outside clips.

## 4. Formats seen (counts, read clips)
Most common: react-game-screen (facecam top, gameplay bottom, word captions at the seam) about a quarter of the clips; then raw-stream-slice (outside), split-callin-celeb (phone call with a famous guest), react-politics-verdict, explainer-fact-react (headline box plus facts over gameplay), avatar-react-chat-flood (VTuber), irl-clip-subtitled (public scene with speaker-coloured captions). Full table with measured medians: [[Format Library (auto)]].

## 5. Caption and layout conventions (FACT, repeated across streamers)
- Word-by-word captions at the seam of a vertical split, white default, one accent colour for the key word or for the second speaker.
- Colour per speaker when two people talk (magenta guest, white host, blue/yellow for calls).
- Static burned-in title across the whole clip appears on the biggest clips (Lacy 18M, Adin 17M, CaseOh 2.5M) and on many flops, so it is not sufficient alone.
- Stage directions in asterisks (*SITS DOWN*, *MUTES MIC*) are common to both hits and flops.

## 6. Open questions (not tested yet)
1. Does the title-picture match in the first 3 s predict views? Needs a labelled column (title_promise_met, 0/1) for every read clip.
2. Do clips with a visible face reaction (eyes and mouth visible, face larger than 10% of the frame) beat cropped-face clips inside the same streamer?
3. Is length (15-35 s) a real effect once streamer and topic are controlled? Pooled rho for seconds is -0.08 (weak).
4. Audio was only measured, never listened to; tone of voice and jokes are invisible here.
5. The control group is small (12 flop/mid, all Jynxzi). Need flops for other streamers (lower tail of each channel) and more per-streamer reads.

## 7. Next steps
Add columns title_promise_met and face_visible to `reads` and fill them for the 86 rows; continue reading toward 25 own + 25 outside per streamer and the lowest-viewed clips of each channel; rerun `build_training.py` and `measure_hooks.py`.

### 2e. Label tests at 236 rows (2026-10-23 night, FACT)
- face_visible: 87 clips with a readable face average 2.75M views, 26 without 2.77M: no difference. So a visible face is not what separates clips (it only matters weakly in the measured face_area number).
- title_promise_met: pooled 82 met avg 3.1M vs 31 not met avg 1.8M, but within the same streamer and side the medians point the same way in only 3 of 5 comparable groups (Jynxzi flop 139K vs 157K goes the other way). Still NOT supported; keep as an open hypothesis.
- Other repeated patterns in the labels: (a) series templates repeat and keep winning (the 2B2T headline-box clips of ohnePixel: 14.6M, 13.1M, 11.8M, 5.9M, 5.2M); (b) avatar-instead-of-face gameplay (TheBurntPeanut) reaches 5-11M with a 3-s green title or no caption at all; (c) outside raw-stream-slice clips depend on event size (chess PogChamps 25M, rabbit scene 15M) not on edit; (d) small channels with strong gags (Buddha RP 32K) stay small, so channel size dominates absolute views.
