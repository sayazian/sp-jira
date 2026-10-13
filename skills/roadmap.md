# Roadmap Visualization Skill

## Purpose
Reproduce and update the **Standard Pioneer Development Roadmap** infographic as a single, high-resolution PNG (and optionally SVG/PDF). This is a **repeatable build specification**, not a request to regenerate a loosely similar AI illustration. Every visual element should be generated from structured data.

**Source of truth:** GitHub issues in `sayazian/sp-jira`, supplemented by the baseline schedule below. Planned dates are targets, **not evidence of completion**. Do not display tasks as completed unless their GitHub issues are closed and the acceptance criteria are verified.

## Output
- Main artifact: `roadmap.png` (recommended 1600 × 1000 px or larger, landscape, white background).
- Optional editable vector: `roadmap.svg` and/or `roadmap.pdf`.
- Save generated assets in `artifacts/` or a user-specified location. Do not commit generated assets unless requested.
- Include a small footer: "Planned milestones — not actual completion status" when rendering a plan.

## Required visual components

1. **Header:** large, dark navy "Standard Pioneer" / "Development Roadmap" on two lines. Subtitle "October 12 – November 30, 2026 · From foundation to a shared AI development environment". Optional upper-right motto: "Build. Learn. Share. What's next, together."
2. **Seven-column Gantt chart:** Weeks 1–7 with dates, seven workstream rows, left-hand label and one-line output, horizontal colored bars, subtle grid and alternating row fills.
3. **Cumulative agent development chart:** line chart with labeled point values 0, 2, 5, 8, 10, 10, 10, 10. X-axis dates: Oct 12, Oct 18, Oct 25, Nov 1, Nov 8, Nov 15, Nov 22, Nov 30. Y-axis 0–10 agents. Plot planned targets; if using live issues, use a second distinct series for actual verified completions rather than overwriting the planned series.
4. **Key milestones and outcomes:** four dated summaries, each with a colored icon or simple vector glyph:
   - **Nov 8 — Agent development complete:** Ten working introductory agents, configured AI Gateway, cloud-hosted Cloudflare OS.
   - **Nov 15 — Integrations operational:** Deployed MCP server, successful external tool calls, validated cloud connectivity.
   - **Nov 22 — Collaboration and security verified:** Agent sharing across environments, access controls, security checks.
   - **Nov 30 — Foundation ready:** Integrated demonstrations, documented outstanding issues, agreed next-stage priorities.
5. **Bottom goal banner:** "The overall goal" and: "By the end of November, Standard Pioneer should move from individual experimentation to a shared, functioning AI development environment with 10 demonstrable agents and a repeatable way for founders to collaborate." Right-hand signature: "Ideas to impact. / Standard Pioneer".

## Baseline data (editable)

Weeks and inclusive date ranges:
| Week | Date range |
|---|---|
| 1 | Oct 12–18 |
| 2 | Oct 19–25 |
| 3 | Oct 26–Nov 1 |
| 4 | Nov 2–8 |
| 5 | Nov 9–15 |
| 6 | Nov 16–22 |
| 7 | Nov 23–30 |

Gantt bars are **week indices, inclusive** (1-based):
| Workstream | Start | End | Subtitle | GitHub issues |
|---|---:|---:|---|---|
| AI Gateway | 1 | 1 | AI connectivity ready | #1 |
| Agents 1–10 | 1 | 4 | 10 working agents | #2–#11 |
| Cloud deployment | 3 | 4 | Hosted Cloudflare OS | #12 |
| MCP integration | 5 | 5 | MCP server + validation | #13–#14 |
| Agent sharing | 6 | 6 | Cross-founder execution | #15 |
| Security | 6 | 6 | Access controls verified | #16 |
| Final integration | 7 | 7 | Demo + review | #17–#18 |

Cumulative planned agent count:
| Date | Planned agents |
|---|---:|
| 2026-10-12 | 0 |
| 2026-10-18 | 2 |
| 2026-10-25 | 5 |
| 2026-11-01 | 8 |
| 2026-11-08 | 10 |
| 2026-11-15 | 10 |
| 2026-11-22 | 10 |
| 2026-11-30 | 10 |

## Layout and styling
- Overall aspect ratio approximately 16:10; minimum 1600 × 1000.
- Canvas: white `#FFFFFF`; headings navy `#102D59`; secondary text slate `#4C6586`; borders `#D6E2EF`; light row background `#F3F8FD`.
- Workstream palette: AI Gateway `#2F80E7`, agents `#399AE3`, cloud `#24AFA9`, MCP `#28B28C`, sharing/security `#9275D8`, final integration `#E3A128`.
- Use a modern sans-serif font (e.g. DejaVu Sans or an available system sans), clear type hierarchy, ample margins, rounded cards and bars, light gridlines.
- Top Gantt section ~45% of page height; lower half split into two cards: line chart left, milestone text right; footer banner ~9%.
- Use vector-drawn icons (gear, robot, cloud, link, people, shield, flag, target) or plain colored circles with simple symbols. Do not require proprietary icons or font files.
- Keep every label readable at 100% size; do not truncate text or overlap chart axes.
- Preserve visual distinctions between **planned** and **completed** work. Do not infer completion from due dates.

## Reproduction procedure
1. Read this file and, if current progress is requested, retrieve issues #1–#18 from `https://github.com/sayazian/sp-jira/issues` via GitHub access. Use issue status and acceptance evidence; do not invent actual completion.
2. Populate a structured data object containing weeks, workstreams, planned cumulative agent counts, milestones, and outcome banner. Use the tables above as the default data.
3. Render with Python 3 and Matplotlib (or SVG drawing code). Suggested install: `python3 -m pip install matplotlib`. Use `matplotlib.patches.FancyBboxPatch` for rounded Gantt bars and cards, `Axes.plot` and `fill_between` for the cumulative line chart, and text/patches for milestone panels. Use `GridSpec` or absolute figure coordinates for consistent alignment.
4. Set explicit figure size and DPI, for example `figsize=(16,10), dpi=150`; export with `savefig("artifacts/roadmap.png", dpi=150, facecolor="white")` and optionally `savefig("artifacts/roadmap.svg")`.
5. Inspect the rendered image for legibility, overlaps, dates, counts, and matching colors. Fix any layout issues before sharing.
6. Report the output path and the data's as-of date. If issue data could not be fetched, say that the graphic is the baseline plan only.

## Quality checklist
- [ ] All seven weekly columns and workstream bars match the baseline or approved updated plan.
- [ ] Agent target series is exactly 0 → 2 → 5 → 8 → 10, then remains at 10.
- [ ] All four dated milestones and descriptions are present.
- [ ] The overall-goal banner is included.
- [ ] Planned work is not misrepresented as completed.
- [ ] No cropped text, overlapping labels, illegible axes, or low-resolution output.
- [ ] PNG generated; SVG/PDF optional; output path documented.

## Update rules
- If founders revise scope or dates, update both the Gantt ranges and milestone summaries, and regenerate the line chart from the revised agent targets.
- Prefer GitHub issue descriptions for agreed deliverables; do not silently change the plan from issue status alone.
- The ten-agent target refers to **introductory agents**, not the separate 11 practical-agent exercises from the original curriculum.
- This skill is reusable by any collaborator with repository access and a Python environment; no access to the original generated infographic is required.
