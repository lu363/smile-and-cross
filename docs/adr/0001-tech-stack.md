# 0001 – Use the team's stack for Smile & Cross

- **Status:** Accepted
- **Date:** 2026-11-21

## Context

The project's main goal is learning, so that what I learn transfers directly to my job as a full-stack developer. My team uses AWS, Java, Kotlin, Python, PostgreSQL and InfluxDB Cloud.

## Options considered

1. **Team stack.** Pros: everything I learn is useful at work; colleagues can answer questions. Cons: the JVM and Spring Boot have a steeper start than lighter frameworks.
2. **A beginner-friendly stack (e.g. Node.js + SQLite).** Pros: faster first results. Cons: little transfers to work.

## Decision

Use the team stack:

- **Backend:** Java + Spring Boot, built with Gradle. Java because the team uses it and it makes OOP concepts (classes, interfaces, types) very explicit, which suits learning. Kotlin can be added later, since both run on the JVM.
- **Main database:** PostgreSQL, for everything that must be correct and consistent.
- **Time-series data:** InfluxDB Cloud, for game events over time (marks, time to Bingo, active players).
- **Push notifications:** a Python function on AWS Lambda, triggered by an SQS queue.
- **Frontend:** TypeScript + React (Vite) as an installable web app (PWA), needed for Web Push on phones.
- **Infrastructure:** AWS (ECS Fargate, RDS, ALB, SQS, Lambda), described in Terraform.

## Consequences

- One monorepo with `backend/`, `frontend/`, `functions/` and `infra/`.
- Four languages to learn (Java, TypeScript, Python, HCL), but each has one clear job.
- The local setup needs Docker for Postgres and InfluxDB.
