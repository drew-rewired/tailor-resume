# Changelog

All notable changes to the Tailor Resume skill are documented here.

---

## [1.1] — 2026-08-21

### Added
- **Existing-resume path in onboarding** — first launch now asks whether you already have a resume to paste in or point to a file, and extracts the structure directly instead of always starting from a blank Q&A. Confirmed Experience is still asked every time regardless of path, since that section is never on a formal resume by definition.

---

## [1.0] — 2026-08-21

- Initial release
- `/tailor-resume` — match score, keyword gap analysis, tailored summary, bullet priority ranking, action items, projected post-edit score
- `/tailor-resume-setup` — conversational add/edit of your resume file at any time
- Automatic first-launch onboarding — no template file to fill in by hand; the skill builds `~/.tailor-resume/master-resume.md` from a short conversation
- Confirmed Experience section — captures real, undocumented experience so it's never wrongly flagged as a gap
- Pattern indexing and score-based conditional output to reduce token use across multi-JD sessions
