<div align="center">

### TAILOR RESUME SKILL
**A Claude Code skill that scores your resume against any job description.**

*Know before you apply.*

<br>

<img src="https://img.shields.io/badge/version-1.0-000000?style=flat-square" alt="version">&nbsp;<img src="https://img.shields.io/badge/free-open%20source-111111?style=flat-square" alt="free">&nbsp;<img src="https://img.shields.io/badge/Claude%20Code-skill-CC0000?style=flat-square" alt="Claude Code skill">

<br>

`/tailor-resume` &nbsp;·&nbsp; `/tailor-resume-setup`

</div>

---

**Mac / Linux**

```bash
mkdir -p ~/.claude/commands && curl -fsSL https://raw.githubusercontent.com/drew-rewired/tailor-resume/main/tailor-resume-skill.md -o ~/.claude/commands/tailor-resume.md && curl -fsSL https://raw.githubusercontent.com/drew-rewired/tailor-resume/main/tailor-resume-setup-skill.md -o ~/.claude/commands/tailor-resume-setup.md
```

**Windows**

```powershell
curl.exe -fsSL https://raw.githubusercontent.com/drew-rewired/tailor-resume/main/tailor-resume-skill.md -o "$env:USERPROFILE\.claude\commands\tailor-resume.md"
curl.exe -fsSL https://raw.githubusercontent.com/drew-rewired/tailor-resume/main/tailor-resume-setup-skill.md -o "$env:USERPROFILE\.claude\commands\tailor-resume-setup.md"
```

Restart Claude Code, then type `/tailor-resume`. Onboarding starts automatically the first time — no file to create or edit yourself.

---

## What this is

A Claude Code slash command that takes a job description and scores it against your resume: what keywords already match, what's missing and why it matters, a rewritten summary for that specific role, your bullets ranked by relevance, and a concrete action list before you submit — plus an honest read on whether tailoring is even worth your time for that role.

This is not a resume writer. It never invents experience, tools, or metrics you didn't tell it about. It works with what's actually true and helps you present it in the right order for the role in front of you.

## How it works

**First launch:** run `/tailor-resume` once. There's no template to fill out — you'll be walked through a short conversation (name and title, a summary, your core skills, your work history job by job, and a section for real experience that never made it onto a formal resume). Claude builds your resume file from your answers and saves it to `~/.tailor-resume/master-resume.md` on your own machine. Nothing is uploaded anywhere.

**After that:** just run `/tailor-resume`, paste a job description, and read the brief.

**To update your resume later** — new job, new bullet, forgot to mention something — run `/tailor-resume-setup` any time, or just tell Claude directly ("add this to my resume") in a `/tailor-resume` session. Nothing about the file format needs to be memorized.

### Why the "Confirmed Experience" section matters

Most people have real, regularly-used skills that never made it onto a formal resume bullet — a tool you're fluent in, a type of project you run constantly, something you do that just never got written up. Onboarding asks about this directly and saves it separately, so a job description asking about it gets correctly matched instead of wrongly flagged as a gap.

## What you get back

| Section | What it tells you |
|---|---|
| Match Score | 0-100, with a one-line verdict on why |
| Keywords Present | JD terms your resume already covers |
| Keywords Missing | High-priority gaps, and why each one matters for this role |
| Tailored Summary | Your summary, rewritten honestly for this specific JD |
| Bullet Priority | Every resume bullet ranked HIGH/MID/LOW for this role |
| Action Items | Concrete edits to make before you submit |
| Projected Score | What your score becomes if you make those edits — and a straight answer on whether it's worth it |

## On tokens / cost

This is a plain-text prompt, not an API integration or a fine-tuned model. A typical run reads your resume file (a page or so) plus the pasted job description (usually a few hundred words) and returns a structured brief. You could run this against dozens of job descriptions in a single session before it added up to any meaningful cost. Nothing here requires an API key beyond whatever Claude Code plan you already have.

## Update notifications

The skill checks for a newer version on every launch. If one's available, you'll see a one-line notice with the update command. If the check fails or you're current, nothing appears.

To update manually at any time, re-run the install command above — it overwrites the old file in place.

---

Full changelog: [CHANGELOG.md](CHANGELOG.md)

---

## Disclaimer

Outputs are AI-generated and provided as-is. They may contain errors or inaccuracies. Always review before submitting an application. The creator assumes no responsibility for outcomes resulting from use of this tool's output.

---

*Built by Drew Martinez · [drewmartinez.io](https://drewmartinez.io)*
