---
name: sp-roadmap-progress
description: Redraw the Standard Pioneer roadmap with the latest GitHub issue evidence and planned versus actual progress in a consistent comparison format. Use for SP roadmap refreshes, progress graphs, and milestone comparisons in the sp-jira repository.
---

# Standard Pioneer roadmap and progress

Generate one comparison infographic from the current agreed plan and freshly retrieved issue evidence. This is an on-demand workflow; it does not schedule monitoring or update issues.

## Sources and retrieval

Read [the visual specification](../roadmap.md), `docs/project-context.md`, and `docs/milestones.md` from the repository root. The visual specification supplies the baseline dates, workstream mapping, palette, wording, and layout. Apply the comparison conventions below whenever progress is requested. Keep the agreed plan unchanged unless a revision has explicit founder approval; flag conflicting dates instead of silently resolving them.

Retrieve issues from `sayazian/sp-jira`, including closed issues, full descriptions, all comments with timestamps, labels, assignees, state, and closure dates. Use GitHub tools or `gh`; paginate lists and comments so recent evidence is not omitted. Inspect issues #1–#18 and any explicitly linked replacements or dependencies. New unrelated issues do not automatically expand the roadmap. Follow relevant evidence links when accessible, and record limitations when they are not.

Record the retrieval timestamp and timezone. If retrieval fails or is partial, label the affected data unavailable or stale; never present cached information as current. Do not replace an existing successful current snapshot with a failed fetch. A baseline-only rendering must say that live progress was unavailable.

## Evidence rules

Build a structured evidence record per mapped issue: issue URL, planned target, issue state, reported status, verified acceptance criteria, evidence URLs and timestamps, blockers, completion date when supported, and uncertainty. Keep claims from comments distinct from independently inspectable evidence.

Use these fixed display states:

| State | Required support |
|---|---|
| Verified complete | Issue closed and all applicable acceptance criteria supported by accessible evidence |
| Reported complete — unverified | Completion claimed or issue closed, but acceptance evidence is incomplete or inaccessible |
| In progress | Explicit progress report or partial acceptance evidence |
| Blocked | Explicit unresolved blocker in the latest relevant update |
| Not started | Explicit statement that work has not begun |
| No verified update | Insufficient information; an open issue alone does not prove zero work |

Read updates chronologically and account for corrections, reopened issues, and resolved blockers. A failed experiment can be a valid documented outcome when the issue calls for investigation; it does not establish a working feature. Do not infer percentages from elapsed time, comments, commits, or checked boxes. A workstream with several issues shows a compact status breakdown, not an invented overall percent. Completion counts describe deliverables, never founder performance.

## Fixed comparison format

Keep the same seven workstream rows, order, header, two lower cards, goal banner, fonts, and base colors as `skills/roadmap.md`. Use a 1600 × 1060 SVG viewBox and export a 2400 × 1590 PNG. Retain the same geometry on subsequent refreshes; fit concise labels and put detailed evidence in the companion data file.

1. **Header:** Preserve the title and planning window. Add `Progress as of YYYY-MM-DD HH:mm TZ`.
2. **Gantt:** Keep all seven planned weekly columns. Draw planned bars in the original workstream colors at 25% opacity. Below each planned bar, reserve a thin actual-events lane. Draw dated evidence markers there: green circles for verified completion, blue circles for progress reports, amber diamonds for blockers. These are events, not inferred execution durations. Add a right-hand status column with compact labels or state counts for grouped issues. Use gray for unknown/unverified status. Include a vertical as-of line if within the window; otherwise state that the as-of date is outside the plan. Do not squeeze out-of-window events into the final week: list their dates in the status column/evidence file.
3. **Legend:** Always show `Planned`, `Verified complete`, `Reported progress`, `Blocked`, and `Unverified / no update`, using both words and visual encodings.
4. **Agent chart:** Keep the planned cumulative target series as a dashed blue line. Add a solid green step series for verified completed introductory agents (#2–#11), using supported completion dates. End actual data at the as-of date; never extend it into the future. Do not use `updatedAt` as a completion date or reconstruct unsupported history from current issue state. If historical completion dates cannot be established, show only the current verified-count point and label the historical series unavailable. Label a zero current count `0 verified; remaining progress unverified` when appropriate, rather than implying no work occurred. Report unknown-date completions separately rather than inventing dates. Reopened or invalidated completions must not remain counted as currently verified.
5. **Milestone card:** Preserve the four target dates and outcomes, prefixing each with `Target`. Add one short actual-status line under each. Say `Verified complete` only when every required outcome is evidenced; otherwise report verified outcomes, explicit blockers, or missing evidence. Distinguish an elapsed unverified target from a demonstrated missed delivery.
6. **Footer:** Preserve the goal banner. Use `Agreed plan vs evidence-backed progress · Source: GitHub issues · As of ...`. Include any material retrieval or evidence limitation. Do not use the baseline-only footer on a comparison chart.

The existing `artifacts/draw-roadmap.cjs`, if available, is a baseline-only rendering reference, not a progress-capable renderer. Adapt or build a deterministic SVG/plotting renderer driven by the structured evidence data; do not merely relabel its hardcoded planned graph as actual progress. Use locally available dependencies without embedding machine-specific runtime paths in reusable scripts.

## Output and verification

Write `artifacts/roadmap-progress.png`, `artifacts/roadmap-progress.svg`, and `artifacts/roadmap-progress-data.json` (or the user's chosen destination). The JSON contains the as-of timestamp, plan source, per-issue evidence records, plotted events, counts, and limitations so another reader can audit the graph. Include only public, task-relevant evidence; no credentials or confidential content.

Before delivery, reconcile plotted counts against the mapped issues, confirm no future actual points or unsupported dates, and inspect the rendered PNG for clipped labels, overlaps, readable legends, and distinct plan/actual encodings. Preserve baseline-only artifacts. Do not commit generated assets or publish changes unless requested.

Show the PNG inline and link the SVG and evidence data. State the as-of date and any material uncertainty concisely. Normal invocation: “Use skills/sp-roadmap-progress/SKILL.md to refresh the roadmap with current issue progress.”
