# Backlog

The nightly build takes the top unchecked item in **Now**, unless an open GitHub issue (Carol's feedback) takes priority. Each item says why it matters and how to know it's done.

## Now (ranked)

- [ ] **N1. Session review screen.** Why: after a run, Carol wants to see what she said vs. the correct French and hear it again. Done when: tapping a session on Today opens a list of every exchange (English prompt, what she said, the correction), each French line has a play button (TTS), and there is a test for it.
- [ ] **N2. Track conjugation by person.** Why: "être" being solid hides that she misses *nous sommes*/*ils sont*. Done when: grading also returns the subject person (je/tu/il/nous/vous/ils) for verb errors, progress stores per-person correct/wrong counts per verb (with a migration for old data), the exercise prompt asks for the weakest persons, and the Words tab shows a small per-person indicator for verbs.
- [ ] **N3. Hands-free resume.** Why: after an auto-pause on a run, she shouldn't need to touch the phone. Done when: while auto-paused (not paused by a tap), the app listens in short windows for « reprends » / « continue » for up to 2 minutes, resumes on hearing it, then stops listening. Covered by a test.
- [ ] **N4. Faster feedback.** Why: the wait while Gemini grades is the main lag. Done when: grading uses the lowest-latency settings available, and if the answer is a near match (only article or ending differences) the app says « Presque » immediately while the grade loads. Time from end of speech to first feedback audio is logged in the session record, and the review screen shows the average.
- [ ] **N5. Listening drills.** Why: comprehension matters for talking with his family. Done when: about every 4th exercise is reversed (the French voice says a sentence, she says the English meaning, graded leniently), it's toggleable in Settings, and there is a test.
- [ ] **N6. Mini conversation to finish.** Why: practice putting sentences together without a script. Done when: an optional 2-minute closing segment has the tutor ask simple questions using only known words, with short replies and gentle correction. Turns are logged.
- [ ] **N7. Progress over time chart.** Why: motivation. Done when: Today shows a small line chart of solid plus familiar items per day, built from a daily snapshot stored in progress (with a migration).
- [ ] **N8. Mishearing tracker.** Why: words the recognizer keeps getting wrong point to pronunciation problems. Done when: repeat-after-me misses and grader pronunciation tips are counted per word, and Today shows "Words to practice saying" (top 5) with play buttons.
- [ ] **N9. Rate-limit resilience.** Why: free-tier 429s shouldn't end a run. Done when: on a 429 the app keeps running from already-fetched exercises using local exact-match grading only, tells her once out loud, and switches back when calls succeed.
- [ ] **N10. Backup reminder.** Why: iOS can clear website data. Done when: if there has been no export in 14 days, Today shows a one-tap Export prompt.
- [ ] **N11. Next unit: passé composé.** Why: after the core verbs, the past tense is the next big unlock. Done when: once 15 or more verbs are familiar or solid, the curriculum unlocks a passé composé track (avoir/être auxiliaries plus past participles of known verbs) as new items, with teach and drill prompts aware of the tense.
- [ ] **N12. Offline app shell.** Why: faster startup on a bad signal. Done when: a service worker caches the static files (never API calls), the microphone and voice still work from the home-screen icon on iOS, and the version shown in Settings updates after each deploy.

## Done

- [x] 2026-10-19: v0.1.0, first version: hands-free session loop, teaching new items, repeat-after-me, translation drills, Gemini grading, spaced repetition, Words tab with "already know", Settings, export/import, end-to-end test.
