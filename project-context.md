# Smile & Cross – project context

Read this at the start of every chat in this project. It's the hand-over note between sessions.

## Who and what

- I'm a software developer who recently started a full-stack role. I studied renewable energy systems, not computer science, and want to fill the foundations.
- The learning project is **Smile & Cross**: a group Bingo web app for surviving family gatherings and company events. Users create boards ("Aunt comments on my weight"), play in a group, get a push notification when someone gets a Bingo, and chat. Mobile-first web app (PWA).
- Tagline: *Smile on the outside. Cross on the inside.*

## Where things live

| What | Where |
| --- | --- |
| Roadmap (milestones, checklists, progress) | https://claude.ai/artifact/8Xf8xEVvGcWkZZnDpdHqjn (a Claude Doc) |
| Code | GitHub repo `lu363/smile-and-cross` (public). Claude can clone it to review commits and code |
| Architecture decisions | `docs/adr/` in the repo |
| Learning knowledge base | Notion page "From Beginner to Full Stack": **one page per topic** (Git, Web security & networking, Python tooling, …), Learning Log, Knowledge Map |
| Updating the knowledge base | the `update-learning-kb` skill. New concepts go onto the fitting topic page, not into new pages |

## Decisions so far

- Stack = my team's stack: **Java + Spring Boot** (Gradle), PostgreSQL, InfluxDB Cloud, Python (AWS Lambda for push), TypeScript + React (Vite) PWA, AWS (ECS Fargate, RDS, ALB, SQS, Lambda), Terraform, GitHub Actions.
- Monorepo: `backend/`, `frontend/`, `functions/push-sender/`, `infra/`, `docs/`.
- Git over HTTPS with Git Credential Manager; SSH optional later. LF line endings via `.gitattributes`.
- Commit style: Conventional Commits; branches like `feat/…`, `fix/…`, `docs/…`; merge pull requests with "Squash and merge".
- Learning log lives in Notion, not in the repo.

## How we work

- **I write the code; Claude coaches.** Claude explains, reviews, asks questions and helps debug. If Claude writes a snippet, I explain it back before committing it.
- One milestone at a time. Done = it runs, it's committed, the roadmap is ticked, and the learnings are in Notion.
- After each milestone I explain the concepts that were **new to me** to Claude **in the chat** (no quizzing on basics I already know); Claude checks for gaps. Only then a concept's status becomes "Can explain". I don't write explanations in Notion: no "in my own words" boxes there.
- Claude points me to primary sources (official docs, release notes) so I learn to verify claims myself.
- I like overviews: few, well-structured pages rather than many small ones.
- Working with AI safely: no secrets in prompts, review every line, check that suggested packages exist, read commands before running them, beware of prompt injection, sandbox AI agents.

## Milestones

M0 Repo and tooling · M1 Data model and game logic · M2 REST API and Postgres · M3 Frontend · M4 Authentication · M5 Real time: chat and live Bingo · M6 Push notifications · M7 Containers and CI · M8 AWS with Terraform · M9 Security and supply chain · M10 Observability and analytics · M11 AI features, MCP and sandboxing.
Idea under consideration: a minimal CI workflow (run unit tests on push) already at the end of M1.

## Current status (update at the end of each session)

- **2026-11-22:** M0 checklist ticked. `main` has the starter files. Branch `feat/MO_repo_and_tooling` is pushed and three commits ahead of `main`: extended log, removed `docs/learning-log.md`, added `.gitattributes`. Not merged yet.
  Open for M0: merge that branch via a pull request with "Squash and merge". No exit check for M0 (git basics are already known).
  Next: M1 – data model and Bingo game rules in Java.
