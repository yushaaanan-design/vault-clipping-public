---
tags: [data, index]
up: "[[Index]]"
---
# Streamer data index (measured, not yet read by eye)

One CSV per streamer in `C:\dev\clipping\by_streamer\` (columns: views, length, cuts, words per second, face size, split-screen share, audio, likes, title, sheet path). Numbers below are MEDIANS of the clips that finished measuring. They describe each streamer's clips; they are not a reading of why a clip works (that is the 25 + 25 reading, still open, see [[STATE]]).

| Streamer | Own n | Outside n | Own med. sec | Outside med. sec | Own med. cuts | Outside med. cuts | Own split | Outside split |
|---|---|---|---|---|---|---|---|---|
| adinross | 25 | 21 | 32 | 19 | 5 | 5 | 1.0 | 1.0 |
| buddha | 23 | 17 | 51 | 92 | 6 | 9 | 0.58 | 0.08 |
| caedrel | 25 | 13 | 36 | 66 | 3 | 5 | 1.0 | 0.08 |
| caseoh_ | 25 | 10 | 41 | 103.0 | 7 | 18.0 | 1.0 | 0.29 |
| gofns | 25 | 2 | 58 | 62.0 | 13 | 26.5 | 1.0 | 0.25 |
| hasanabi | 25 | 13 | 59 | 61 | 11 | 5 | 1.0 | 0.08 |
| ironmouse | 25 | 15 | 46 | 79 | 11 | 26 | 0.75 | 0.08 |
| jynxzi | 193 | 201 | 34 | 46 | 8 | 6 | 1.0 | 1.0 |
| kaicenat | 0 | 2 |  | 85.0 |  | 35.0 |  | 0.41 |
| lacy | 25 | 14 | 24 | 73.0 | 10 | 3.0 | 0.92 | 0.04 |
| ohnepixel | 24 | 19 | 30.0 | 44 | 7.0 | 6 | 1.0 | 0.17 |
| payo | 23 | 12 | 49 | 101.0 | 1 | 16.0 | 1.0 | 0.08 |
| pikabooirl | 25 | 19 | 67 | 60 | 12 | 7 | 1.0 | 0.0 |
| sodapoppin | 25 | 18 | 51 | 84.5 | 7 | 3.0 | 0.92 | 0.0 |
| stableronaldo | 0 | 18 |  | 85.0 |  | 6.5 |  | 0.21 |
| summit1g | 25 | 15 | 35 | 96 | 4 | 10 | 1.0 | 0.17 |
| theburntpeanut | 25 | 10 | 36 | 51.0 | 2 | 3.5 | 0.33 | 0.29 |
| xaryu | 25 | 14 | 55 | 109.0 | 6 | 11.0 | 0.92 | 0.0 |
| xqc | 17 | 23 | 24 | 57 | 4 | 5 | 0.42 | 0.08 |

Total clips split: 1036. Rebuild with `python C:\dev\clipping\db\by_streamer.py`.
