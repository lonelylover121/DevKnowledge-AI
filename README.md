# DevKnowledge AI

DevKnowledge AI keeps engineering documentation current. It reads GitHub repositories, generates Markdown docs for each module, tracks who worked on what, and writes weekly summaries and project knowledge reports for handover.

## Status

Planning is complete. The product spec and architecture are approved. The first build slice (repository scaffold) is blocked until the team's GitLab repository is connected to Cursor.

## Documents

- Product specification: goals, scope, agents, data model, and phases.
- Architecture: stack, components, GitHub integration, security, and the Phase 1 plan.

## What it does

1. **Documentation Intelligence Agent** generates and updates a Markdown doc for each module. Docs follow the repository's folder structure. Changes go through human review before they are published.
2. **Contribution Intelligence Agent** records verified commits and pull requests against modules and GitHub identities. It never treats commit counts as productivity.
3. **Work Summary and KT Agent** builds weekly employee summaries and project knowledge reports from the persisted docs and contribution records. Every statement links to its evidence.

## Planned stack

- **Web:** Next.js (App Router) with Microsoft Entra ID sign-in
- **API and worker:** NestJS, one codebase, two deployables
- **Database:** PostgreSQL with Prisma
- **Queue:** Redis with BullMQ, fed from a PostgreSQL outbox
- **GitHub:** a read-only GitHub App with webhooks
- **AI:** Azure OpenAI behind an adapter
- **Editor:** a VS Code extension, later phase

## Phases

1. Core documentation engine: GitHub integration, module discovery, Agent 1, review, and push-event processing.
2. Employee knowledge portal: sign-in, project explorer, Markdown viewer, history.
3. Contribution intelligence: Agent 2, identity mapping, contribution dashboards.
4. Manager dashboard and reports: Agent 3, weekly reports, project KT, PDF export.
5. Advanced intelligence: architecture graphs, Q&A with RAG, VS Code extension enhancements.

## Running locally

Not available yet. The scaffold will add the commands here once the repository is connected.

## Principles

- Generated content is labeled as generated, and every claim has source evidence.
- Source code is read in memory only and is never stored in full.
- Nothing is pushed to a default branch without explicit approval.
- Commit counts are never used as a productivity measure.
