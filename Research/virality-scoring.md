# Virality scoring

Date: 2026-10-22. [S] sourced, [I] inference/proposal, [U] unverified.

## How existing open-source clippers score (what is actually known)
| Project | Licence | Method | Source |
|---|---|---|---|
| SupoClip | AGPL-3.0 | LLM picks 3-7 clip-worthy segments from transcript; each clip gets hook, engagement, value, shareability scores (0-100 per a launch write-up). Formula/prompt not on the README page; read `backend/` and `docs/architecture.md`. | https://github.com/FujiwaraChoki/supoclip [S]; weights [U] |
| AI-Youtube-Shorts-Generator (Anil-matcha) | not checked [U] | Whisper (cloud or faster-whisper) then LLM ranks vs a "virality framework": hooks, emotional peaks, opinion bombs, revelations, conflict, quotable lines, story peaks, practical value; outputs viral score, hook line, reason | https://github.com/Anil-matcha/AI-Youtube-Shorts-Generator [S via search summary] |
| short-video-generator-AI (OStudi) | MIT | faster-whisper + LLM scoring vs virality framework | https://www.sourcepulse.org/projects/32873366 [S, search summary] |
| Choppity (commercial) | n/a | composite of hook strength, contextual framing, story coherence, emotional pull; plus 5 goal badges | https://choppity.featurebase.app/help/articles/1679666-viral-score-hooks-and-how-clips-are-ranked [S]; weights not published |

Takeaway [I]: the "virality score" in these tools is an LLM's opinion of the transcript against a rubric, not a model trained on real view data. Nobody publishes validation. AGPL (SupoClip) means: reading it for ideas is fine, copying code into a closed product is not. Not legal advice.

## What predicts short-form performance
- Platform metrics creators watch: viewed-vs-swiped (hook), average % viewed / completion, rewatch (loops), shares. Third-party guides only; YouTube does not publish its ranking weights. [S: https://1of10.com/blog/youtube-shorts-analytics/ , https://subscribr.ai/youtube-strategy/youtube-shorts-analytics-metrics-viral] Which of these the algorithm weights most: [U].
- Research: highlight detection uses crowd engagement as ground truth. Mr. HiSum (NeurIPS 2023): 31,892 videos with labels from YouTube "most replayed" stats aggregated over 50,000+ users per video, used as frame-importance scores. https://proceedings.neurips.cc/paper_files/paper/2023/hash/7f880e3a325b06e3601af1384a653038-Abstract.html [S]. AHA (arXiv 2509.16421, preprint, not peer reviewed) does online highlight detection on TVSum and Mr. HiSum, claims 64.19 mAP@50 on Mr. HiSum. https://arxiv.org/pdf/2509.16421 [S]. These models are visual-first and heavy; relevant to you as an idea (replay peaks = good moments), not as a drop-in. [I]
- Free signal worth using: if the source is on YouTube, the "Most replayed" graph (yt-dlp exposes `heatmap` in video info for many videos) [U: I did not verify the field in current yt-dlp; check `yt-dlp -j <url>` for "heatmap"]. It is the closest thing to real audience data and matches Mr. HiSum's label source.

## Proposed formula (PROPOSAL, tune it) [I]
Per candidate clip, every feature normalised 0-1, score 0-100:

`score = 100 * (0.25*hook + 0.20*payoff + 0.15*emotion + 0.15*self_contained + 0.10*speech_density + 0.10*visual + 0.05*length_fit) - penalties`

| Feature | Definition | Local computation |
|---|---|---|
| hook | strength of first 3 s | regex features + small LLM 0-10 (see hooks.md) |
| payoff | clip has a point/answer/punchline near its end | LLM 0-10: "does the clip resolve what it sets up?" |
| emotion | strong stance, surprise, conflict, humour | LLM 0-10, plus audio RMS variance as sanity check |
| self_contained | understandable without earlier context | LLM 0-10; penalty if starts with pronoun/"and/but/so" |
| speech_density | words per second, minus silence | word timestamps: words/duration, silence share from silencedetect; ManiClips' speechActivityScore analogue |
| visual | face present, stable scene, some motion | face detector on 1 fps frames; scene changes via PySceneDetect; analogues of facePresence, sceneStability, motion |
| length_fit | closeness to 30/45/60 s targets | 1 - min(abs(d-target))/target |
| heatmap (optional) | mean "most replayed" value in window | only if yt-dlp gives it; replace 0.10 of hook/emotion weight |

Penalties (subtract points): cut mid-sentence -30; starts with filler -10; >3 s dead air -10; contains only music -50; near-duplicate of a higher-ranked clip (embedding cosine > ~0.85, threshold is a guess) drop.

How to tune: export 20 clips, rank them by hand, check the Spearman correlation of your ranking with the score, adjust weights; later replace with your real posted-clip analytics (retention, views). Until then the weights are guesses. [I]

## Unverified
Exact weights in any commercial tool; whether LLM scores correlate with real views (no published evidence found).
