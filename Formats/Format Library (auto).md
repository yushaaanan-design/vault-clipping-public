---
tags: [formats, auto]
up: "[[Format Catalog]]"
---
# Format Library (auto-generated, do not edit by hand)

Source: `C:\dev\clipping\db\clips.db` tables `reads` (by-eye labels) and `measures` (from features.json). Rebuild: `python -X utf8 C:\dev\clipping\db\build_training.py`. Labels are SEEN by Claude; numbers are MEASURED. Views are lifetime views, not normalised for channel size or age (see Caveats).

Clips read so far: 364. Streamers covered: 19.

## Formats (by-eye label, with measured medians)

| format | n | own | outside | med views | med sec | med cuts | med cuts in first 3 s | med first word (s) | med audio first 3 s vs typical | examples |
|---|---|---|---|---|---|---|---|---|---|---|
| react-game-screen | 86 | 73 | 3 | 1,382,847 | 39.5 | 5.0 | 0.0 | 0.0 | -0.2 | tfiLeyu02oo, UGn77vArjpw |
| raw-stream-slice | 54 | 3 | 51 | 352,382 | 58.0 | 4.0 | 0.0 | 0.0 | -0.75 | CdxejL6SmbE, ChrgOYMhtxA |
| irl-clip-subtitled | 25 | 23 | 2 | 5,321,800 | 22.0 | 8 | 1 | 0.0 | -0.7 | 0qvSz-4eGk4, P--sCKY6SME |
| duo-react-split | 14 | 6 | 8 | 2,350,000 | 26.0 | 7.0 | 1.0 | 0.0 | -0.95 | L3ncTv1ZXnk, YgQJpRK4gmY |
| gameplay-avatar-captions | 14 | 14 | 0 | 5,647,411 | 34.5 | 1.0 | 0.0 | 0.0 | 0.25 | LdcM1V2lMLM, ryNjsfuAtNg |
| react-clip-player | 13 | 12 | 1 | 1,314,867 | 59.0 | 9 | 0 | 0.0 | 0.2 | 6j_BQCxHn74, o2Xrn8cjog8 |
| irl-selfie | 11 | 7 | 3 | 3,645,981 | 34.0 | 8 | 1 | 0.0 | 1.15 | FZ6lLVMOEiU, hLOa_-uaJok |
| split-callin-celeb | 10 | 6 | 4 | 6,576,910 | 38.0 | 2.5 | 0.0 | 0.0 | 0.9 | ljUdoGj6Wck, a9U1chnLaS4 |
| react-voice-chat | 10 | 8 | 2 | 6,318,471 | 48.0 | 11.5 | 0.5 | 0.0 | -2.2 | lLNreUNtXJg, ib8dm4tCiJc |
| avatar-story-solo | 9 | 9 | 0 | 2,468,727 | 46.0 | 15 | 1 | 0.0 | 0.3 | 19rCkE1Sblc, ZduYoh5k72k |
| react-embedded-clip | 8 | 7 | 1 | 1,555,272 | 42.0 | 8.5 | 1.0 | 0.0 | -1.8 | jSROyVpbmOc, eigpvy382mg |
| react-play-shock | 8 | 8 | 0 | 155,851 | 52.0 | 13.5 | 0.0 | 0.0 | 0.15 | KVWoQE_8-wg, 511nBuRatOk |
| debate-broadcast-clip | 7 | 7 | 0 | 3,884,603 | 60.0 | 17 | 0 | 0.0 | 0.0 | 5Iq5d_hyXA8, C7QaTEewPk4 |
| react-play-breakdown | 7 | 7 | 0 | 372,910 | 48.0 | 5 | 0 | 0.0 | -5.8 | TEubTig3WAs, mWZvCpH6Wrg |
| raw-broadcast-moment | 6 | 0 | 6 | 275,538 | 66.0 | 0.5 | 0.0 | 0.0 | -0.25 | e91M0XLX7Jw, ZqDgOjJVQ_M |
| explainer-fact-react | 6 | 6 | 0 | 8,876,818 | 45.0 | 9.5 | 1.0 | 0.0 | -0.5 | aPhfP8sFoqM, jbnl3v5WgbI |
| react-chat-reading | 6 | 6 | 0 | 400,357 | 62.5 | 7.0 | 0.0 | 0.0 | -1.0 | a_Vey_rQkOc, 7qCOyYDTymw |
| avatar-react-chat-flood | 5 | 4 | 1 | 2,233,345 | 32.0 | 16 | 1 | 0.0 | 0.1 | famphiFyhVU, hCstrbH7WPU |
| rp-gameplay-plain | 5 | 5 | 0 | 3,923 | 56.0 | 1 | 0 | 0.0 | -1.5 | 9b3oEhPLKcU, 0UQIKvkZI2s |
| react-explainer-panel | 4 | 2 | 2 | 2,020,000 | 40.0 | 6.0 | 1.0 | 0.0 | 0.6 | 6hh6BhXoehA, bqqourBjU_A |
| meme-montage-react | 4 | 2 | 0 | 163,994 | 25.0 | 9.5 | 0.5 | 1.19 | -1.9 | ctxNrrM7IuU, -HY4iJc_8Xg |
| ranking-list-clips | 4 | 0 | 4 | 71,912 | 62.0 | 8.5 | 0.0 | 0.5 | -6.55 | dlT1-d71GOk, VqZY6LdhhD4 |
| react-still-image | 4 | 2 | 2 | 707,332 | 19.5 | 3.0 | 0.5 | 0.0 | 0.1 | X3pImNy0ek8, 91_DhLkx5pU |
| reaction-cutaway-show | 3 | 3 | 0 | 3,780,161 | 57.0 | 10 | 0 | 0.0 | 0.2 | C3T1VGjGh9w, qgsj3Zm1Y8g |
| tiktok-reupload-side-by-side | 3 | 2 | 1 | 9,400,000 | 17.0 | 1 | 0 | 0.0 | 1.5 | HgvI8UQSXEk, _qA6nfSQ4sg |
| podcast-story-clip | 3 | 2 | 1 | 2,782,425 | 46.0 | 10 | 1 | 0.0 | -1.2 | AYK4_8F_vKk, Z3upGX3rDRU |
| split-sketch-pov | 3 | 2 | 1 | 4,173,353 | 22.0 | 10 | 2 | 0.0 | -5.8 | KUlZeRqmjow, ZWqlJo2DxAo |
| react-news-debunk | 3 | 3 | 0 | 1,259,624 | 43.0 | 10 | 0 | 0.0 | 0.5 | FTYmV7_9p6Y, jthvtR22Sx4 |
| rp-gameplay-annotated | 3 | 3 | 0 | 33,086 | 39.0 | 15 | 2 | 0.64 | -1.7 | SR_L1yvsKMQ, 2yXIzlKMJDE |
| split-react-video | 2 | 2 | 0 | 13,014,838 | 60.0 | 8.5 | 0.0 | 0.0 | 3.75 | jgvZUmZhYFY, Tc15aUlHgeY |
| duo-couch-qa | 2 | 2 | 0 | 11,500,000 | 19.5 | 13.5 | 2.0 | 0.0 | 0.4 | Bd8KDtw7UxA, 0Z-8Nn_d-PE |
| react-politics-verdict | 2 | 2 | 0 | 6,502,217 | 42.5 | 6.5 | 0.5 | 0.0 | 1.5 | Ax-6RRr8rXw, 7gMq-_zX9iY |
| story-over-static | 2 | 2 | 0 | 1,832,059 | 50.0 | 0.5 | 0.0 | 0.0 | -0.65 | RWMPdkPSU2M, KxlZSsA4kq4 |
| animation-not-clip | 2 | 0 | 2 | 687,571 | 46.0 | 6.5 | 0.0 | 0.0 | -2.45 | fC5G6txHDYg, Qt_O1m32AJA |
| rp-gameplay-chat-overlay | 2 | 2 | 0 | 82,536 | 53.0 | 10.5 | 0.0 | 0.0 | 2.35 | NUURSE_QMnk, Xipb5SwdylQ |
| split-callin-confrontation | 1 | 1 | 0 | 48,630,394 | 31.0 | 2 | 0 | 0.0 | -13.1 | tm6dZ08AABY |
| multi-cam-gag | 1 | 1 | 0 | 36,573,672 | 15.0 | 0 | 0 | 0.0 | -3.4 | IQWt_uS4jP4 |
| headline-card-irl | 1 | 0 | 1 | 17,235,100 | 10.0 | 0 | 0 | 6.02 | -0.1 | cO9I7oW-ifE |
| music-video-not-clip | 1 | 0 | 1 | 14,998,608 | 123.0 | 0 | 0 | 7.16 | -4.3 | 6IC23P_24v8 |
| fullframe-face-over-lobby | 1 | 1 | 0 | 9,400,000 | 28.0 | 3 | 0 | 0.0 | -6.8 | htnX-m6RQq8 |
| ranking-game-split | 1 | 0 | 1 | 8,919,041 | 18.0 | 14 | 1 | 0.0 | -0.7 | HCMDHLbLX9k |
| music-video-teaser | 1 | 1 | 0 | 5,058,330 | 19.0 | 2 | 0 | 7.52 | -11.4 | 7DhdhxqZH_k |
| duo-static-announce | 1 | 1 | 0 | 4,062,961 | 12.0 | 0 | 0 | 0.0 | 0.0 | spodsrCsSng |
| story-confession-split | 1 | 1 | 0 | 1,217,910 | 90.0 | 16 | 0 | 0.0 | 4.1 | yAB67BURvao |
| react-draft-prediction | 1 | 1 | 0 | 1,138,996 | 18.0 | 0 | 0 | 0.0 | -4.4 | 6jDLErLUFo8 |
| react-tweet-take | 1 | 1 | 0 | 734,504 | 36.0 | 3 | 0 | 0.0 | -1.3 | v3HgMOYZTCk |
| interview-clip | 1 | 0 | 1 | 617,770 | 63.0 | 5 | 0 | 0.0 | 4.3 | q_M6ymjWWms |
| story-over-footage | 1 | 1 | 0 | 572,586 | 44.0 | 1 | 0 | 0.0 | 1.1 | -18QlMK4VIA |
| gameplay-fullframe-title | 1 | 0 | 0 | 149,459 | 13.0 | 5 | 0 | 6.94 |  | Z3Wak7mdgZo |

## Hook types (label) with measured hook numbers

| hook type | n | med views | med first word (s) | med cuts in first 3 s | med audio first 3 s vs typical | question in first words | digit in first words |
|---|---|---|---|---|---|---|---|
| on-screen-claim | 82 | 2,336,886 | 0.0 | 0.0 | -0.5 | 25 | 10 |
| no-hook-longform | 56 | 248,171 | 0.0 | 0.0 | -0.9 | 15 | 6 |
| title-card-claim | 28 | 3,385,672 | 0.0 | 0.0 | -1.85 | 7 | 1 |
| title-claim | 25 | 1,412,122 | 0.0 | 0 | 0.15 | 6 | 5 |
| no-hook-slow-ui | 11 | 1,415,919 | 0.0 | 0 | 0.7 | 1 | 2 |
| visual-gag | 10 | 2,084,893 | 0.0 | 0.0 | -0.25 | 2 | 0 |
| text-headline-curiosity | 8 | 8,876,818 | 0.0 | 1.0 | -0.5 | 5 | 2 |
| on-screen-stage-direction | 8 | 5,249,660 | 0.0 | 1.0 | -2.45 | 0 | 2 |
| quote-question | 8 | 2,643,814 | 0.0 | 0.0 | -1.45 | 4 | 0 |
| visual-hook-silent | 7 | 1,962,856 | 0.0 | 0 | 0.4 | 1 | 0 |
| question-opening | 6 | 11,500,000 | 0.0 | 0.5 | -0.1 | 3 | 1 |
| static-title-claim | 6 | 1,839,215 | 0.0 | 0.0 | 0.55 | 2 | 0 |
| debate-confrontation | 6 | 3,905,954 | 0.0 | 0.0 | -0.15 | 1 | 1 |
| quote-chat-reading | 6 | 377,027 | 0.0 | 0.5 | 0.0 | 2 | 1 |
| quote-chat-avatar | 5 | 2,411,528 | 0.0 | 1 | 0.3 | 0 | 0 |
| scene-opening-chatter | 5 | 98,532 | 0.0 | 0 | 2.35 | 0 | 0 |
| quote-claim | 5 | 153,412 | 0.0 | 0 | 0.1 | 0 | 0 |
| bait-title-stage-direction | 5 | 156,837 | 0.0 | 0 |  | 2 | 1 |
| reaction-silent-face | 4 | 5,771,894 | 1.26 | 0.5 | 2.3 | 1 | 0 |
| to-camera-challenge | 4 | 11,100,000 | 0.0 | 1.0 | 6.1 | 0 | 0 |
| ranking-list-title | 4 | 71,912 | 0.5 | 0.0 | -6.55 | 1 | 0 |
| in-media-res-shout | 3 | 32,500,000 | 0.0 | 1 | -2.0 | 0 | 0 |
| celebrity-callin | 3 | 14,071,747 | 0.0 | 0 | 3.7 | 1 | 0 |
| quote-title | 3 | 3,507,167 | 0.0 | 0 | 1.8 | 0 | 1 |
| brag-claim | 2 | 18,350,000 | 0.0 | 0.0 | -2.55 | 0 | 0 |
| quote-card | 2 | 11,586,631 | 0.0 | 0.5 | -6.1 | 1 | 0 |
| chat-roast | 2 | 2,171,823 | 0.0 | 0.0 | -2.0 | 0 | 0 |
| static-title-quote | 2 | 3,186,454 | 0.0 | 1.0 | -0.35 | 1 | 0 |
| award-show-claim | 2 | 2,802,038 | 0.0 | 0.0 | -1.05 | 0 | 0 |
| title-card-question | 2 | 1,328,211 | 1.46 | 0.5 | 29.0 | 1 | 0 |
| news-claim | 2 | 1,512,554 | 0.0 | 0.0 | 1.45 | 0 | 1 |
| story-confession | 2 | 1,398,955 | 0.0 | 0.5 | 3.25 | 2 | 1 |
| play-shock | 2 | 445,440 | 0.0 | 0.0 | -2.3 | 0 | 0 |
| play-praise | 2 | 375,866 | 0.0 | 0.0 | -6.35 | 0 | 0 |
| confrontation-callin | 1 | 48,630,394 | 0.0 | 0 | -13.1 | 0 | 0 |
| dare-setup | 1 | 36,573,672 | 0.0 | 0 | -3.4 | 1 | 0 |
| physical-conflict | 1 | 16,476,588 | 0.0 | 0 | 3.7 | 0 | 0 |
| music-video | 1 | 14,998,608 | 7.16 | 0 | -4.3 | 1 | 0 |
| prank-reveal | 1 | 12,944,265 | 0.0 | 0 | -22.3 | 0 | 0 |
| bait-then-payoff | 1 | 11,604,148 | 0.0 | 0 | 7.3 | 0 | 0 |
| curiosity-mystery | 1 | 11,496,539 | 6.3 | 1 | -16.5 | 0 | 0 |
| game-screen-question | 1 | 10,835,603 | 0.0 | 0 | -2.8 | 0 | 0 |
| reaction-split-listicle | 1 | 8,919,041 | 0.0 | 1 | -0.7 | 1 | 0 |
| verdict-claim | 1 | 7,198,087 | 0.0 | 1 | 2.6 | 0 | 0 |
| name-gag | 1 | 5,806,347 | 0.0 | 0 | 0.4 | 0 | 0 |
| story-opening | 1 | 5,207,987 | 0.0 | 0 | 0.3 | 0 | 0 |
| music-video-teaser | 1 | 5,058,330 | 7.52 | 0 | -11.4 | 0 | 0 |
| podcast-claim-captions | 1 | 4,646,706 | 0.0 | 1 | 0.2 | 0 | 0 |
| reaction-chat-flood | 1 | 4,446,107 | 1.4 | 2 | 2.7 | 0 | 0 |
| title-question | 1 | 3,655,223 | 2.88 | 0 | -14.5 | 1 | 0 |
| selfie-vlog | 1 | 3,645,981 | 0.0 | 1 | -1.7 | 0 | 0 |
| static-title-stage-direction | 1 | 3,370,230 | 0.0 | 2 | -1.7 | 1 | 0 |
| static-ui-no-caption | 1 | 2,203,692 | 5.16 | 0 | -9.9 | 0 | 0 |
| no-hook-title-claim | 1 | 1,728,970 | 2.96 | 0 | -14.2 | 1 | 0 |
| draft-prediction | 1 | 1,138,996 | 0.0 | 0 | -4.4 | 0 | 0 |
| animation-edit | 1 | 1,100,000 | 0.0 | 0 | -1.7 | 0 | 0 |
| quote-chat | 1 | 1,008,798 | 2.04 | 0 | -13.3 | 0 | 0 |
| play-confusion | 1 | 771,416 | 0.0 | 0 | -12.5 | 0 | 0 |
| broadcast-moment | 1 | 741,206 | 0.0 | 1 | 0.6 | 0 | 0 |
| tweet-take | 1 | 734,504 | 0.0 | 0 | -1.3 | 0 | 0 |
| interview-claim | 1 | 617,770 | 0.0 | 0 | 4.3 | 1 | 0 |
| story-opening-number | 1 | 572,586 | 0.0 | 0 | 1.1 | 0 | 1 |
| play-complaint | 1 | 537,372 | 1.12 | 0 | 0.5 | 0 | 1 |
| colour-coded-dialogue | 1 | 403,458 | 0.0 | 0 | 4.3 | 0 | 0 |
| static-title-pov | 1 | 305,362 | 0.0 | 0 | 14.9 | 0 | 0 |
| meme-montage | 1 | 180,781 | 2.84 | 1 |  | 0 | 0 |
| static-title-irl | 1 | 160,962 | 0.0 | 1 | -0.7 | 0 | 0 |
| quote-rule | 1 | 156,554 | 0.0 | 1 | -0.3 | 1 | 1 |
| play-prediction | 1 | 114,203 | 0.0 | 0 | -5.8 | 0 | 0 |
| no-hook-walking | 1 | 40,356 | 1.44 | 0 | -10.6 | 0 | 1 |

## Layouts (first clause of the label, counts)

| layout | n |
|---|---|
| vertical split: facecam top | 49 |
| full-frame vertical gameplay | 8 |
| vertical split: facecam top (hand on chin) | 7 |
| landscape 16:9 stream capture | 7 |
| landscape 16:9 desktop capture | 5 |
| split: face top about 40% | 4 |
| landscape 16:9 gameplay | 4 |
| full-frame vertical third-person gameplay | 4 |
| full-frame vertical first-person gameplay | 3 |
| vertical split: facecam top (glasses | 3 |
| vertical split: facecam top (hood | 3 |
| vertical split: facecam top (grey tee) | 3 |

## Caveats

- Views are not normalised: a 10M clip from a huge channel and a 300K clip from a niche channel are not comparable one to one. Compare inside the same streamer (view `training` has `streamer` and `side`) before comparing formats across streamers.
- The sample is the TOP clips by views, so this shows what the best clips look like, not what separates hits from flops. The flop and mid clips of the study queue are the control group still to be read.
- Data gaps: xqc own channel returned CS2 guides (wrong channel); payo and buddha outside rows hold unrelated videos (alias matches).
