# Contributing

Thanks for your interest. This repo mirrors the RevOps system Ryzo runs in production.

- **Structure:** each skill is a directory under `skills/` with a single `SKILL.md`
  (YAML frontmatter `name` + `description`, then the skill body). Reference files
  a skill needs live alongside it in the same directory.
- **No secrets, ever.** No API keys, tokens, client names, or internal URLs. All
  CRM credentials are bring-your-own via environment variables. CI runs a
  gitleaks scan on every PR.
- **PRs:** keep changes focused, explain the RevOps rationale, and confirm no
  secrets or client-identifying data were added.
