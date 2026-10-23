---
tags: [formats, design, central]
up: "[[Index]]"
---
# Design systems of viral clips (central spec note)

How each recognisable format is built: zones, crop, captions, colour, motion, timing. One spec per template, measured from the study frames and verified by looking. Specs become render templates later (HyperFrames is the candidate renderer, see the main vault's github-repos note). Format IDs match [[Format Catalog]].

## Method (set 2026-10-22, user asked how the top 100 will be analysed)
1. **Measure** per clip from the saved frames (no re-download): zone seams (row-gradient peaks, repeated across frames), face box (size, position, zoom vs the original stream), caption region (position, size, colours, outline, pinned vs word by word via text detection / OCR), dominant colours, flashes, layout changes and cuts.
2. **Signature and cluster**: each clip becomes a vector of those numbers; cluster to find the 5-8 real templates; record count and median views per cluster.
3. **Verify by looking**: read representative frames of every cluster; the automatic measures are crude (the old split-screen share read about 1.0 everywhere), so replace or correct them before trusting them.
4. **Write the spec** per template (fields below), with FACT (measured), SEEN (read by eye) and INFERENCE kept apart.
5. **Hits vs flops**: a feature only counts if hits have it and flops lack it or differ.

## Spec fields
| Field | What to record |
|---|---|
| Canvas | resolution and aspect (the study downloads are 360x640 or similar) |
| Zones | top / middle / bottom heights in % and what fills each (face, gameplay, B-roll, list, blurred copy) |
| Seam | y position of the zone boundary, any divider bar |
| Face crop | face box width % of canvas, centre y, how tight vs the stream's facecam |
| Gameplay crop | full width, centre crop, or small window with margins |
| Captions | position (y), font look, size, fill and outline colours, pinned or word by word, words per beat |
| Title / headline | pinned text in the first seconds, wording pattern, colours |
| Inserts | photos, overlays, logos, subscribe buttons, view-count watermarks |
| Motion | cuts per 10 s, zooms, flashes, speed changes |
| Colour | dominant palette, flashes tied to game state |
| Timing | when the hook line lands, when the peak lands, when the payoff lands |
| Evidence | n clips, median views, hits vs flops |

## Specs so far (from 3-6 hand-read clips, SEED level; replaced by measured clusters after wave 1)
- **F01 split-screen reaction**: face zone about the top 41% (seam at y about 0.41 measured on tfiLeyu02oo), gameplay below, one pinned caption at the seam, 2 cuts in 10 s, red/green flashes with game state. SEEN + FACT.
- **F02 zoomed trivia explainer**: face fills the frame, one large caption word per beat in the middle, picture insert lower-left on the key noun. SEEN.
- **F03 countdown list**: pinned headline top, list 5-1 below it, source clip centred, blurred copy behind, view-count watermark. SEEN.
- **Clutch collab (8jyoViylz28, 22M)**: face top with a pinned neon-blue title bar "200 IQ CLUTCH VS CASEOH & SKETCH" at the seam, gameplay below, 5 cuts in 58 s, only 22% voiced (tension, not talking). SEEN.
- **Busy meme edit (rmRu2uxRgJA, flop 124k)**: five different looks in 18 s (facecam, explosion, Twitch overlay, meme photo, SUBSCRIBED button, logo, glitch). SEEN. Flop pattern: many layout changes, no single idea.

## Specs seen across the top 25 own-channel clips (2026-10-22, SEEN by eye; not measured)
- **Family A split screen** (14 of 25): canvas 9:16. Face zone = top 32 to 42%, very tight (eyes to chin fill the width). Seam y about 0.35 to 0.42. Gameplay bottom 58 to 65%, full width. Caption sits ON the seam (word by word) or a pinned label sits on it. Sub-type A1 keeps the phone clip-player UI visible in the gameplay (play ring, heart, View comments): the viewer is shown that he is watching a clip.
- **Word-by-word captions**: centred, 1-3 words per beat, white fill, heavy black outline, italic comic font, size about 5-6% of the frame height, yellow on emphasis words in some clips, asterisk action text for jokes (*SMASHES XBOX*).
- **Pinned neon-blue title** (F06): comic bold italic, light-blue fill, dark-blue outline, on the seam for the whole clip, 2 lines when long, superlative wording ("200 IQ CLUTCH VS CASEOH & SKETCH", "BEST STRAT OF THE YEAR").
- **Pinned white label**: rounded white box, black text, emoji at the end, sits on the seam, states the premise or quotes a teammate.
- **Speaker-coded captions**: one colour per speaker (white for the host, yellow for the guest; yellow for him and purple for the grandma), word by word, mid-height.
- **Full-frame vertical talk (family B)**: the couch or room fills the frame, captions at mid-height, the cut follows the speaker (hard cuts, no transitions).
- **Cheap re-upload (family C)**: thin gameplay or side-by-side strip in the middle or top, black bars, TikTok watermark, one pinned label, optional red circles and a red "watch till end" tag.
- **Timing**: hook visible in frame 1 (pinned label or the face mid-line); escalation; shock face or scream at 60-80% of the length; payoff or proof text in the last 10-20%.
- Replace these with measured clusters later; the measuring pass is in the Resume Protocol.

## Wave 2 (outside house style, SEEN)
- Split: face top about 40-55%, media bottom; captions on the seam; word-by-word white with a yellow accent on the key word; *STAGE DIRECTION* captions in asterisks; tint flash (red, green, grayscale) on the punchline; pop-in memes or thumbnails under the chin; a pinned yellow "JYNXZI + verb + object" title over gameplay in 4 of 25.
