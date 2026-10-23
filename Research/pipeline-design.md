# Pipeline design (local, RTX 3060 Laptop 6 GB, i5-11400H, 15.7 GB RAM)

Date: 2026-10-22. [S] sourced, [I] inference, [U] unverified. Nothing was installed or run for this note.

## Flow
yt-dlp (download) -> ffmpeg (extract 16 kHz audio) -> faster-whisper (CUDA, word timestamps) -> sentence/segment candidates -> scorer (regex heuristics + small LLM) -> top-N -> face-aware 9:16 reframe -> caption burn-in (word-timed) -> ffmpeg export. Store everything per video as JSON (transcript.json, candidates.json) so each stage is resumable. [I]

## Components
| Stage | Library | Licence | GPU VRAM |
|---|---|---|---|
| Download | yt-dlp | Unlicense (public domain) [U: from memory, not verified this session] | none |
| Media | ffmpeg | LGPL/GPL depending on build [U: from memory] | none (NVENC encode optional) |
| ASR | faster-whisper (SYSTRAN) | MIT [U: from memory] | README benchmark (large-v2, 13-min audio, RTX 3070 Ti 8 GB): fp16 ~4.5 GB, int8 ~2.9 GB, batch 1; batched ~6 GB fp16 / ~4.5 GB int8 [S: https://github.com/rrrodzilla/faster-whisper mirror of SYSTRAN README]. large-v3 ~6 GB fp16 / ~4 GB int8 is from a blog, unverified [U: https://vexascribe.com/faster-whisper]. Use `compute_type="int8_float16"` (documented type) [S: https://www.pypi.org/project/faster-whisper/0.10.1/]; `word_timestamps=True` [S: https://pypi.org/project/faster-whisper/]. Measure on your GPU. |
| Scene cuts | PySceneDetect or ffmpeg scene filter | BSD-3 [U] | none |
| Face detect | MediaPipe Face Detection | Apache-2.0 [S: https://inference-models.roboflow.com/models/mediapipe-face] | CPU is fine |
| LLM scoring | Ollama or llama.cpp with a 3-8B model, 4-bit quant (e.g. Qwen2.5 / Llama 3.x) | model licences differ, check each [U] | a 7-8B Q4 is roughly 5 GB, tight on 6 GB; a 3-4B Q4 ~2.5 GB is safer [I, rule of thumb, unverified] |
| Captions | ASS subtitles via ffmpeg `subtitles`/`ass` filter, word-level karaoke tags | n/a | none |

Key VRAM rule [I]: run stages sequentially, never Whisper and the LLM at the same time on 6 GB. Unload Whisper (free the model object) before starting the LLM. Whisper medium/large-v3 int8 and an LLM do not fit together.

## Whole-pipeline alternative
SupoClip (AGPL-3.0) already does LLM clip pick + face-centred crop + word-synced subtitles but relies on cloud LLMs by default (Ollama supported) [S: https://github.com/FujiwaraChoki/supoclip]. Good as a reading reference. Because of AGPL, copy ideas, not code, if you plan to sell. [I, not legal advice]

## Build order (smallest working version) [I]
1. v0 (one script): yt-dlp a video -> faster-whisper -> words.json. Check timestamps are sane.
2. v1: sentence split + sliding window candidates (25-65 s) + regex hook score + speech density; export the top 5 as plain 16:9 clips with ffmpeg (`-ss/-to`, re-encode for accurate cuts). No LLM yet.
3. v2: add the small-LLM pass (hook, payoff, self-contained, 0-10, JSON) on the top ~20 candidates only (saves time).
4. v3: 9:16 reframe: sample frames at ~2 fps, MediaPipe face box, smooth the x position (moving average / dead zone so the crop does not jitter), ffmpeg crop with a keyframed expression or per-chunk crop.
5. v4: ASS word-by-word captions burned in; hook-title overlay for first 2-3 s.
6. v5: tune weights against clips you rate by hand (see virality-scoring.md).

## Unverified
Exact latency on your machine; large-v3 VRAM; licence strings marked [U] should be re-checked on each repo's LICENSE file before use. CUDA libs (cuBLAS/cuDNN versions) for faster-whisper: check the current README. Python 3.13 wheel support for each package: check before installing (some ML packages lag new Python versions). [U]
