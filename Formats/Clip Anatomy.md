---
tags: [formats, central, anatomy]
up: "[[Index]]"
---
# Clip anatomy (the central note: structure, hook, captions, text, design, audio)

One place for how a viral short is built, per element, with counts and the waves they came from. Updated after every wave; each wave adds a column or a dated section, never overwrites. Sources: [[Viral Library/Wave 1 Top 25 Own Channel]] (his own channel, 25 clips read frame by frame), Wave 2 (outside creators, pending), the 6 clips the user gave (see [[Viral Library/viral-patterns]]). Labels: FACT (counted/measured), SEEN (read by eye from frames), HEARD-DATA (measured from the audio signal, I do not listen), INFERENCE, USER.

## 1. Families (what kinds of clip exist)
| Family | Wave 1 count (of 25) | Wave 2 (outside) |
|---|---|---|
| A facecam over gameplay (A1 reacting to a clip, A2 his own play) | 14 (+2 cheap re-uploads) | pending |
| B IRL / collab / talk, no gameplay | 9 | pending |
| C cheap TikTok re-upload (small strip, watermark) | 2 | pending |

## 2. Structure (time)
- One idea per clip; setup, escalation, payoff; shock face or scream near 60-80% of the length; proof text near the end. FACT: 15 of 25 have 5 or fewer cuts. Length 10-60 s, no link to views. Irony and reversal is the strongest shape.
- Talk clips cut to follow the speaker (13-17 cuts in 18-21 s); gameplay-reaction clips hold shots longer.

## 3. Hook (first 3 s)
- Premise stated in a pinned label or title from frame 1 (about 10 of 25); in-the-middle shout or line (6); a question (2); a prop, parcel or cat in the face (3); a famous name carried in the label (4).
- Audio side of the hook: see section 7.

## 4. Captions (the spoken words on screen)
- Word by word, 1-3 words per beat, white italic comic font, heavy black outline, centred on the seam or mid-frame (about 13 of 25). Optional yellow emphasis word, asterisk action text (*SMASHES XBOX*, *CASTLES WINDOW*).
- Speaker-coded colours when two people talk (white host / yellow guest; yellow him / purple grandma).
- Some clips caption only the key callouts, not every word (#8).

## 5. Text overlays (what is written, not spoken)
- Pinned neon-blue comic title for superlative claims (F06): "200 IQ CLUTCH VS CASEOH & SKETCH", "BEST STRAT OF THE YEAR", "GIVES A CLIP A 10/10 FOR THE FIRST TIME".
- Pinned white rounded label with the premise or a quoted line ("Jynxzi accidentally reacts to his own clip", "can we get 5 big booms", "Open walls with sledge").
- Retention and proof text: a red "watch till end" tag; game text as proof (WON ROUND 4, LOST ROUND 1, 1 VS 1); red circles drawn on the screen (#22).
- Titles are curiosity hooks and often do not describe the clip (FACT, 2 of 25 clearly mismatched).

## 6. Design and positioning
- Family A: 9:16 canvas, face zone top 32-42% (eyes to chin fill the width), seam at y about 0.35-0.42, gameplay below, caption or pinned label ON the seam. Sub-type A1 shows the phone clip-player UI (play ring, heart, View comments).
- Family B: the couch, room or desk fills the frame, captions at mid-height, hard cuts, no transitions.
- Family C: thin strip, black bars, watermark, one label: 9.7M and 9.4M views, so polish is not the driver.
- Outros: TV-static glitch or SUBSCRIBED animation appear on some clips; none of the top performers needed them.
Full spec list: [[Formats/Design Systems]].

## 7. Audio (measured, not listened to)
Method (2026-10-22): per-second loudness (dB), loudest second, how many seconds are 8 dB louder than the clip's typical level (scream or effect peaks), loudness of the first 3 s versus the rest (a loud or quiet hook), silence share, dynamic range (95th minus 10th percentile), mean spectral centroid (higher = brighter, screamier). Series saved per clip in `study/data/<id>/audio.json`. I do not hear music or sound effects; the signal numbers cannot tell music from speech, so the speech share still comes from the transcript. Results for the top 25: filled in below once measured.
- Wave 1 result (25 clips, measured): no volume-jump hook (first 3 s louder in 8, quieter in 7, same in 10); screams are not required (10 of 25 have no peak); the loudest second is in the first third in 10 clips and the last third in 10 (front-loaded or end-loaded); little dead air (silence share vs views -0.52, weak); typical level -39 to -8 dB and louder is not better; wide quiet-to-loud contrast is common (median 20 dB). Rule: continuous voice, at least one clear contrast moment, end soon after the loudest moment. Details: [[Viral Library/Wave 1 Top 25 Own Channel]] section 10.
- Wave 2 audio: pending.

## 8. Comments (what the audience does)
Top comments quote one specific line or moment, add missing context, or correct a detail. A moment that produces a quotable line is a moment people comment on.

## 9. Rules of thumb so far (to be tested on flops and the outside wave)
1. Say the premise in text in frame 1.
2. One idea; build tension; land the payoff in the last 10-20%.
3. Tight face, word-by-word captions on the seam; colour-code speakers.
4. Look for the moment people can quote.
5. Do not assume polish or short length wins: the evidence so far says neither.

## Wave log
- 2026-10-22 Wave 1: top 25 own-channel clips (read frame by frame; audio measured after).
- Wave 2: top 25 outside clips (queued first in the study cycle; to be read next).

## Wave 2 column (outside top 25, added 2026-10-22; see [[Viral Library/Wave 2 Top 25 Outside]])
1. Basics: median 22 s, median 7 cuts, 7 of 25 with 5 or fewer cuts.
2. Layout: 18 split or stack, 6 full-frame, 1 landscape.
3. Hook: person mid-line in frame 1 (about 20 of 25); pinned title in 4.
4. Captions: word-by-word in 23 of 25; asterisk stage directions in about 8.
5. Design: tint flash on the punchline in about 18 of 25.
6. Structure: one idea, payoff in the last 20-30%.
7. Audio: first 3 s median -0.3 dB vs typical; no dead air (24 of 25 at 0%); 9 clips with no peaks.
