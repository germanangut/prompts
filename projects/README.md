# Projects

Project-scoped prompt bundles organized by domain. Each directory contains prompts tailored specifically for a particular type of project.

## Project Categories

| Directory | Use for | Example projects |
|---|---|---|
| [`web-development/`](./web-development/) | Web apps, APIs, dashboards | SaaS app, e-commerce site, REST API |
| [`data-science/`](./data-science/) | ML, analytics, data engineering | Recommendation engine, analytics dashboard, ETL pipeline |
| [`automation/`](./automation/) | Process automation, bots, integrations | CRM sync, report automation, RPA bot |
| [`content-creation/`](./content-creation/) | Blogs, newsletters, social media | Company blog, YouTube channel, email campaigns |
| [`mobile-app/`](./mobile-app/) | iOS, Android, cross-platform apps | Consumer app, internal tool, PWA |
| [`devops/`](./devops/) | CI/CD, infrastructure, cloud | Kubernetes cluster, CI pipeline, monitoring setup |

## How Project Prompts Differ from Generic Prompts

Prompts in `prompts/` are **generic** — they work across any domain.
Prompts in `projects/` are **domain-specific** — they include context, terminology, and considerations specific to that project type.

For example:
- `prompts/coding/code-review.md` — general code review for any codebase
- `projects/devops/security-review.md` — security review specifically for infrastructure code, with cloud-specific checks

## Combining Project and Generic Prompts

For best results, use project-specific prompts alongside generic ones:
1. Start with a project-specific prompt for domain context
2. Use generic prompts from `prompts/` for cross-cutting concerns (e.g., code review, report writing)
3. Use agent definitions from `agents/` if the task needs to be automated
