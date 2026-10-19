# Turning on the nightly builder (one time)

Scheduled tasks run in the environment of the Claude session that creates them, so the task has to be created from a Claude Code session that has access to this repo.

1. Open Claude Code (claude.ai/code, or the Code tab in the desktop app) and start a session on the **carolkli/petit-a-petit** repo.
2. Paste the message below.

---

Set up a nightly scheduled task for this repo.

1. First, check that you can pull and push here: make an empty commit on a scratch branch, push it, then delete the branch. If push fails, stop and tell me what access is missing.
2. Create a scheduled task named "Petit à Petit nightly build" that runs every day at 1:52am America/New_York (`CRON_TZ=America/New_York 52 1 * * *`), with push notifications on, and this prompt:

> Nightly build for the Petit à Petit French tutor app (GitHub repo carolkli/petit-a-petit, served by GitHub Pages from main). Clone or pull the repo. Read CLAUDE.md and follow its "Nightly run protocol" exactly: handle open GitHub issues first, then take the top unchecked item in BACKLOG.md, implement only that, add tests, and run `npm test`. If the tests pass, update BACKLOG.md (move the item to Done with today's date), add a plain-language CHANGELOG.md entry, bump APP_VERSION, commit and push to main. If the tests fail and you can't fix them, push to the branch nightly/YYYY-MM-DD and open a PR explaining the blocker, leaving main alone. Never commit secrets, delete or rename curriculum item ids, or break the saved-progress format without a migration. End with a 3 to 5 line summary for Carol: what shipped, what to try on her next run, and what's next. If you cannot access the repo, stop and say exactly what access is missing.

3. Tell me which approval setting the task got. Its runs need to push without asking, so if it isn't set to approve automatically, tell me where to change that.
