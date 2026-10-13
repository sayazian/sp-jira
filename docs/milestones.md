# Standard Pioneer — October–November 2026 milestones

**Planning window:** October 12 – November 30, 2026  
**Status:** Proposed targets recorded in GitHub issues; not a statement that work is complete.  
**Issues:** https://github.com/sayazian/sp-jira/issues

| Week | Dates | Expected deliverable | Issues |
|---|---|---|---|
| 1 | Oct 12–18 | Configure AI Gateway; agents 1–2 | #1–#3 |
| 2 | Oct 19–25 | Develop and validate agents 3–5 | #4–#6 |
| 3 | Oct 26–Nov 1 | Develop and validate agents 6–8; begin cloud work | #7–#9, #12 |
| 4 | Nov 2–8 | Agents 9–10; deploy Cloudflare OS | #10–#12 |
| 5 | Nov 9–15 | Deploy MCP server; validate cloud integrations | #13–#14 |
| 6 | Nov 16–22 | Agent sharing/interoperability and security checks | #15–#16 |
| 7 | Nov 23–29 | Integration testing, issue resolution, final demonstrations | #17 |
| Final | Nov 30 | Review deliverables, record lessons and agree on next priorities | #18 |

## Milestone acceptance checkpoints

### November 8 — Agent and cloud foundation
- 10 introductory agents are demonstrable against their issue-specific acceptance criteria.
- AI Gateway is configured and responds to a test request.
- Cloudflare OS is deployed and accessible to an authorized user.

### November 15 — Integrations
- MCP server exposes a working tool backed by an external API.
- An agent successfully invokes that tool.
- Cloud, gateway, MCP and core storage smoke tests are documented; critical failures addressed.

### November 22 — Collaboration and security
- Another founder can run a shared agent in their environment.
- Access control, secret handling and isolation checks are demonstrated; gaps recorded.

### November 30 — Final review
- Integrated demonstration of agents, hosted environment, MCP and sharing.
- Open issues and limitations documented.
- Next-stage priorities and owners agreed by founders.

## Issue map
- #1 AI Gateway
- #2–#11 Ten introductory agents (agents 6–10 are intentionally founder-defined)
- #12 Cloudflare OS deployment
- #13 MCP server
- #14 Cloud validation
- #15 Agent sharing
- #16 Security
- #17 Integration review and demos
- #18 November milestone closure

## Planned cumulative agent targets
| Date | Agents |
|---|---:|
| Oct 12 | 0 |
| Oct 18 | 2 |
| Oct 25 | 5 |
| Nov 1 | 8 |
| Nov 8 | 10 |
| Nov 15 | 10 |
| Nov 22 | 10 |
| Nov 30 | 10 |

## Keeping the plan current
- Owners update issue progress and provide evidence.
- The coordinator records decisions, blockers and next actions after each founders' session.
- A revised milestone requires agreement and a corresponding update to issues, this file and `skills/roadmap.md`.
- To generate a roadmap graphic, follow `skills/roadmap.md`. Distinguish planned progress from verified actual completions.
