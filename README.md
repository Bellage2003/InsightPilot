# InsightPilot — AI Analytics Agent SaaS Dashboard

InsightPilot is a multi-tenant SaaS analytics dashboard with an AI agent that answers questions over your project metrics and generates weekly insight reports.

> Built on top of an open-source SaaS starter (credits below). I extended it with project-based analytics data modeling, an agent tool layer for metric queries, and a dashboard + chat workflow optimized for real SaaS use.

## Features
- **Multi-tenant Projects**: users can create projects and manage data sources
- **Analytics Dashboard**: KPI cards + charts (trend, breakdown, cohort-ready)
- **AI Agent for Metrics**:
  - Ask questions like “Why did conversion drop last week?”
  - Generate weekly summaries with cited date ranges
  - Tool-based querying to reduce hallucinations
- **Auth & Session**: NextAuth
- **Database**: PostgreSQL + Prisma
- **UI**: TailwindCSS + shadcn/ui

## Tech Stack
Next.js (App Router) / React / TypeScript / PostgreSQL / Prisma / NextAuth / Recharts

## Architecture (High-level)
- App Router + Server Actions for server-side mutations
- Prisma models: User, Project, DataSource, MetricEvent, ChatSession, ChatMessage
- Agent layer:
  - system prompt + tool definitions
  - `queryMetrics(projectId, range)` -> SQL aggregation
  - `summarizeMetrics(data)` -> insight report

## Getting Started
### 1) Setup
- Node.js >= 18
- PostgreSQL

```bash
pnpm install
cp .env.example .env
pnpm prisma migrate dev
pnpm dev


## 📜 Docs 
<br />
https://www.saasstarterkit.com/docs

##  💻 Demo
https://www.saasstarterkit.com/dashboard/test243/main
