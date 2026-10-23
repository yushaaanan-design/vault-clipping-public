# Segmentation (choosing clip boundaries)

Date: 2026-10-22. [S] sourced, [I] inference, [U] unverified.

## Goal
Clip of 30/45/60 s that starts at a thought's beginning (ideally on a hook), ends after the payoff, never cuts a word or sentence in half. [I]

## Inputs you already have (from faster-whisper)
Word timestamps, so sentence boundaries (split on . ? ! plus long gaps), pauses between words, and silence (also ffmpeg `silencedetect`, ManiClips-style -35 dB). Scene cuts from ffmpeg `select='gt(scene,0.3)'` or PySceneDetect.

## Algorithms
| Method | Idea | Good for | Cost |
|---|---|---|---|
| Sliding window | for each sentence start, grow to nearest sentence end in [target-5, target+10] s; score all | simplest, always works | cheap |
| TextTiling | boundaries where vocabulary overlap between adjacent blocks dips (Hearst 1997, tuned for expository text; NLTK has an implementation) | finding topic shifts in monologues | cheap, no GPU. https://www.cl.cam.ac.uk/teaching/1617/R216/J97-1003.pdf [S] |
| Embedding-based | embed sentences (e.g. a small sentence-transformer), cut where cosine similarity between neighbouring windows drops | better than word overlap on casual speech | small model, CPU ok [I]; no benchmark verified [U] |
| LLM-based | give timestamped transcript, ask for 3-7 self-contained segments with start/end | what SupoClip does (3-7 segments, LLM choice) [S: https://github.com/FujiwaraChoki/supoclip] | local LLM context limits: chunk long transcripts (e.g. 10-min chunks with overlap) [I] |

## Recommended recipe [I]
1. Build sentence list with timestamps.
2. Candidate generation: sliding window over sentence starts (and TextTiling/embedding boundaries as preferred starts); durations 25-65 s.
3. Snap: start = first word start minus ~0.1 s; end = last word end plus ~0.3 s; if a silence >0.4 s lies within 1 s of the boundary, snap into it. Never cut inside a word.
4. Reject: starts with a continuation word ("and", "but", "so", "because", "which") or a dangling pronoun; ends on a sentence that is a question with no answer after it.
5. Prefer ends right after a payoff sentence (laugh, conclusion, number, punchline); prefer starts at a topic boundary or a question.
6. De-duplicate overlapping candidates: keep highest score, drop others overlapping >50%.
7. Scene cuts: avoid ending a clip in the middle of a fast cut sequence; for a talking-head source this barely matters. [I]

## How ManiClips' fields likely combine (INFERENCE ONLY)
Known: speechActivityScore, sceneStabilityScore, facePresenceScore, mainSpeakerScore, motionScore, hotScore, label "Balanced segment across motion, speech, and visual stability" (from binary strings in earlier context). My guess: fixed-length windows (30/45/60) slid across the timeline; each window gets the sub-scores (speech = non-silent share; stability = few scene cuts; face = share of thumbnails with a face; main speaker = share with a large central face; motion = frame difference); `hotScore` is a weighted sum; the label is a fallback text when no one sub-score dominates. No evidence for weights or whether the windows align to sentences. Notably ManiClips seems to have no text/semantic signal, which is where your tool can beat it. [I]

## Unverified
Embedding-segmentation quality on spoken transcripts; ideal snap tolerances (0.1 s / 0.3 s / 0.4 s are my starting values).
