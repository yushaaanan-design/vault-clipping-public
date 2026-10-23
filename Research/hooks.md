# Hooks (short-form video)

Date: 2026-10-22. Tags: [S] = sourced, [I] = my inference, [U] = unverified.

## What a hook is
The first 1-3 seconds of a short: the part that decides whether the viewer stays or swipes. [I] definition, consistent with YouTube Studio's "Viewed vs. Swiped Away" metric, which measures how many people stopped to watch instead of scrolling past [S: https://1of10.com/blog/youtube-shorts-analytics/ , third-party guide, not YouTube itself].
- Commonly quoted targets (70-80% "viewed", ~80% retention at 3 s) disagree between guides and none come from YouTube. [U] Use your own baseline instead. [S: https://subscribr.ai/youtube-strategy/youtube-shorts-low-watch-time-boost]
- A sharp early drop in the retention curve = weak hook; a slow slope = pacing; a drop in the last second = outro/blank space. [S, same guide]

## Hook types (pattern list, my synthesis [I], patterns are folk knowledge in creator guides)
| Type | Example opening | Detect in transcript |
|---|---|---|
| Question | "Why do most startups die in year two?" | first sentence ends in "?" or starts with why/how/what if |
| Bold claim | "This is the worst advice you'll hear." | superlatives, absolutes (never, always, nobody, worst, best) |
| Open loop | "I'll show you the mistake at the end." | "by the end", "the reason is...", "wait for it", promise-then-delay |
| Number/list | "3 things I wish I knew." | digits or number words in first 8 words |
| Contrarian | "Everything you know about X is wrong." | "wrong", "myth", "actually", "stop doing" |
| Story start in the middle | "So he looked at me and said..." | past tense + quote + person pronoun, no setup |
| Direct address | "If you're a student, listen." | "you/your" in first 5 words |
| Pattern interrupt | sudden loud word, cut, zoom | audio/visual, see below |

## Scoring a hook from the transcript (proposal [I])
Take the first ~3 s of words (use word timestamps) plus the first sentence. Features, each 0-1:
1. question present; 2. bold/absolute words; 3. open-loop phrases; 4. number present; 5. "you" address; 6. NOT starting with filler ("so", "um", "okay so", "hi guys", "welcome back") (penalty); 7. starts mid-thought needing context (starts with "and", "but", "because", pronoun without referent) (penalty: viewer lost).
Cheap method: regexes for 1-7. Better: ask a small local LLM "rate this opening 0-10 as a stop-scrolling hook, JSON only" and average with the regex score. Existing tools do the LLM version: SupoClip gives each clip a hook score plus AI-written hook titles [S: https://github.com/FujiwaraChoki/supoclip]; Choppity ranks clips with weak openings lower "even if the middle is gold" [S: https://choppity.featurebase.app/help/articles/1679666-viral-score-hooks-and-how-clips-are-ranked]. How either computes the number is not published. [U]

## Audio / visual cues (all [I], no source tested these as predictors)
- Audio: speech starts within 0.3 s of clip start (no leading silence); energy (RMS) jump or higher pitch variance in first 3 s; no music-only intro. Computable with ffmpeg `silencedetect` / `astats` or librosa.
- Visual: a face visible in frame 0; a scene cut or motion spike in the first 2 s; large on-screen text. Face = MediaPipe/OpenCV on frame 0; motion = frame difference.
- ManiClips uses speech activity, face presence and motion as score fields (from earlier context), which suggests the same idea. [I]

## Practical rules
- Trim the clip start to the first word (cut leading silence, keep ~0.1 s). If the best sentence begins mid-segment, start there, not at the segment boundary.
- Also generate a hook TITLE overlay (text on screen for first 2-3 s) with the LLM; SupoClip does this. [S]
- Generate 3-5 hook variants per story and compare swipe-away rates after ~24 h (creator advice) [S: subscribr link above, third party].

## Unverified
No peer-reviewed source found that proves any specific hook pattern predicts retention. Treat the table as hypotheses to test with your own analytics.
