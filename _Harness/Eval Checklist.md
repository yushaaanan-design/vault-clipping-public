---
tags: [harness, eval]
up: "[[README]]"
---
# Eval checklist (run before calling a step done; record the result in the run-log)

## Pipeline smoke test (10 minutes, run after changing any script)
- [ ] `python -X utf8 C:\dev\clipping\yt.py --no-warnings --cookies C:\dev\clipping\yt-cookies.txt --js-runtimes node --skip-download --print "%(title)s" https://www.youtube.com/shorts/tfiLeyu02oo` prints the title (cert + cookies + JS runtime all OK).
- [ ] cycle on a 2-row queue produces `features.json`, `sheet.jpg`, `comments.json` and removes the mp4.
- [ ] `first_words` in features is not empty for a clip with speech.
- [ ] no usernames in `comments.json` (keys are only text and likes).

## Quality checks for clip output (when the real clipper exists)
- [ ] First 3 seconds contain the hook; clip starts on a word boundary and ends after the payoff.
- [ ] I LOOKED at the frames (contact sheet), not only the transcript.
- [ ] Length is checked against the evidence so far (best performers were 10-20 s, small sample).
- [ ] User review result recorded (kept / deleted and why) so the next score is calibrated.

## Measuring that the harness is improving
Per work chunk, note in the run-log: tool calls that failed and had to be retried, user corrections, and whether a known lesson was violated. Fewer repeats of lessons already in [[Lessons]] = the harness works.
