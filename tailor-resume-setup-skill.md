# Tailor Resume Setup
# CURRENT VERSION: 1.2
# Invoke with: /tailor-resume-setup

Lets the user review or update their resume file at `~/.tailor-resume/master-resume.md` conversationally, without hand-editing markdown.

## Version check (do this first, silently)

Run: `curl -fsSL https://raw.githubusercontent.com/drew-rewired/tailor-resume/main/version.txt`

Compare the result to `1.2` (the version in this file's header). If they differ, prepend one line to your first response: "A newer version of this skill is available. Update: `curl -fsSL https://raw.githubusercontent.com/drew-rewired/tailor-resume/main/tailor-resume-setup-skill.md -o ~/.claude/commands/tailor-resume-setup.md` then restart Claude Code." If the check fails for any reason (offline, blocked) or the versions match, say nothing about it and proceed normally. Never let this check block or delay the actual task.

## Behavior

**If `~/.tailor-resume/master-resume.md` does not exist:** Tell the user no resume is on file yet and run them through the onboarding conversation defined in `tailor-resume.md` (the same flow that runs automatically on first `/tailor-resume` launch), then save the file.

**If it exists:** Read it in full, show a short plain-language summary (name/title, number of jobs, number of bullets, whether a Confirmed Experience section exists and how many items are in it), then ask what they want to do:

1. **Add or edit a job** — collect title, company, dates, and bullets the same way onboarding does; new bullets continue the existing B-numbering, never restart it.
2. **Add to Confirmed Experience** — ask what they do that isn't captured yet, same prompting style as onboarding step 5.
3. **Edit the summary or core skills** — show the current text, ask what should change.
4. **Start over completely** — confirm before wiping anything ("this replaces your whole file — sure?"), then run full onboarding fresh.
5. **Just show me the file** — print the current contents as-is.

Apply whatever they choose, save the updated file, and confirm what changed in one or two plain sentences. Never invent content they didn't provide. Never silently drop existing bullets or Confirmed Experience items when adding new ones — this is an edit, not a rewrite, unless they explicitly chose option 4.
