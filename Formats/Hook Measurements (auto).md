---
tags: [formats, auto, measurements]
up: "[[Format Library (auto)]]"
---
# Hook and clip measurements vs views (auto-generated)

Clips measured: 1064; in groups of at least 8 (same streamer, same side): 1054 in 36 groups. Method: each clip gets a view percentile inside its own (streamer, side) group; Spearman correlation of each feature with that percentile. FACT = measured. Correlation is not cause; the clips are mostly top-of-channel, so the range of views is narrow. Rebuild: `python -X utf8 C:\dev\clipping\db\measure_hooks.py`.

## All groups pooled

| feature | n | Spearman rho vs within-group view percentile |
|---|---|---|
| face_area_pct | 1054 | +0.13 |
| face_y_mean | 933 | -0.10 |
| seconds | 1054 | -0.08 |
| audio_dynamic_range_db | 986 | -0.07 |
| audio_silence_share | 986 | -0.07 |
| words_per_sec | 1054 | +0.06 |
| hook_digit | 1054 | -0.06 |
| voiced_share | 1054 | +0.05 |
| cuts | 1054 | -0.04 |
| first_word_s | 1054 | -0.03 |
| cuts_first3 | 1054 | +0.02 |
| audio_first3_vs_median | 986 | +0.01 |
| first_words_n | 1054 | -0.01 |
| hook_question | 1054 | -0.00 |

## Own channel vs outside clips (same method, split by side)

| feature | own n | own rho | outside n | outside rho |
|---|---|---|---|---|
| cuts_first3 | 580 | -0.01 | 452 | +0.06 |
| first_word_s | 580 | -0.00 | 452 | -0.06 |
| first_words_n | 580 | -0.00 | 452 | -0.03 |
| hook_question | 580 | +0.01 | 452 | -0.03 |
| hook_digit | 580 | -0.04 | 452 | -0.10 |
| words_per_sec | 580 | +0.02 | 452 | +0.11 |
| voiced_share | 580 | -0.00 | 452 | +0.12 |
| face_area_pct | 580 | +0.05 | 452 | +0.22 |
| face_y_mean | 558 | -0.06 | 354 | -0.18 |
| audio_first3_vs_median | 534 | +0.00 | 452 | +0.03 |
| audio_silence_share | 534 | -0.00 | 452 | -0.15 |
| audio_dynamic_range_db | 534 | -0.00 | 452 | -0.16 |
| seconds | 580 | -0.01 | 452 | -0.16 |
| cuts | 580 | -0.02 | 452 | -0.06 |

## Reading guide

- |rho| under about 0.15 is noise at these sample sizes; do not build rules on it.
- Hook features: first_word_s (when the first word is spoken), cuts_first3 (cuts in the first 3 s), audio_first3_vs_median (loudness of the first 3 s against the clip typical level, dB), hook_question / hook_digit (question mark or digit in the first words).
- Known measurement limits: cut counts and framing numbers are unreliable on letterboxed or split clips; audio is measured as signal, not listened to (see Lessons).
