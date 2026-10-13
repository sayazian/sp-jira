# SP Tickets — Codex working instructions

This repository is the shared coordination workspace for Standard Pioneer founders. The related ChatGPT Project is called **SP Tickets**. Codex does **not** automatically see its chats or private context; use these checked-in documents and current GitHub issues as the shared context.

## Read first
1. `docs/project-context.md` — goals, collaboration rules and decision practices.
2. `docs/milestones.md` — agreed October–November 2026 baseline and issue mapping.
3. `skills/roadmap.md` — reproducible roadmap visualization.
4. Current issues: https://github.com/sayazian/sp-jira/issues

## Operating principles
- Lightweight structure, no micromanagement. Agree on **outcomes**, let task owners choose **methods**.
- Founders update their own issues before each session. Session coordinator summarizes demonstrated results, decisions, blockers and next-session actions.
- One accountable owner per active issue; unassigned until founders agree. Don't assign people or claim completion without evidence.
- Every issue should describe output, concise milestones (ideally 1–3), acceptance criteria, target session/date and evidence of results.
- Failed experiments with documented findings are useful results; do not misrepresent them as successfully implemented features.
- Do not track hours, commits or ticket counts as proxies for founder performance.
- Treat roadmap dates as **plans**, not proof of completion. Ask before changing agreed scope, ownership or dates.
- This is a founders' operating plan, **not a participant bootcamp**.

## Development and changes
- Prefer minimal, reviewable changes. Read existing files before editing.
- Do not create duplicate GitHub issues; inspect existing issues first.
- Keep `docs/milestones.md`, issue descriptions and `skills/roadmap.md` aligned when an approved schedule change occurs.
- Never commit credentials, tokens, private founder compensation/equity discussions, or confidential customer information. This repository is public.
- When producing the roadmap, use `skills/roadmap.md`; label plans and actuals distinctly.
- For each work session, use this brief structure: **Completed (with evidence)**; **Decisions / blockers**; **Next actions (owner, issue, deliverable, due session)**; **Milestone risks**.

## Cross-environment workflow
- ChatGPT SP Tickets: strategy, founder decisions, drafting and coordination.
- Codex: local file edits, scripts, tests and generated artifacts.
- GitHub issues and committed docs: durable shared source of truth.
- After remote changes: `git pull origin main`. Before pushing local changes, inspect `git status`, commit and `git push`.
- A chat-only decision is not automatically available in Codex: write approved decisions into the appropriate document or issue.
