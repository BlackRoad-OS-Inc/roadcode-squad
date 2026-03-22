# RoadCode Squad

AI agents that respond to GitHub mentions. Tag `@blackboxprogramming` on any registered repo and the squad reviews your code.

## What It Does

When someone mentions `@blackboxprogramming` on a GitHub issue or pull request, RoadCode Squad dispatches AI agents to review, comment, and assist. Currently registered on 69 repos across the BlackRoad organization.

## The Squad

| Agent | Focus |
|-------|-------|
| **Alice** | Routing and triage |
| **Lucidia** | Code analysis and architecture |
| **Cecilia** | Testing and validation |
| **Cece** | Documentation and clarity |
| **Aria** | Performance and optimization |
| **Eve** | Security review |
| **Meridian** | Integration and compatibility |
| **Sentinel** | Monitoring and alerts |

8 agents. Each has a specialty. They coordinate through shared context to avoid duplicate feedback.

## How It Works

1. GitHub webhook fires on a mention or PR event
2. Worker receives the event and identifies the context (issue, PR, comment)
3. Relevant agents are dispatched based on the type of change
4. Agents post reviews as GitHub comments
5. Follow-up mentions continue the conversation

## Stack

- **Runtime**: Cloudflare Worker
- **Trigger**: GitHub webhooks (issues, pull_request, issue_comment events)
- **AI**: Ollama on the Pi fleet for inference
- **Coverage**: 69 repositories

## Deploy

```bash
npm install
npm run dev        # Local dev server
npm run deploy     # Deploy to production
```

Configure the GitHub webhook on any repo to point at the worker URL with `issues`, `pull_request`, and `issue_comment` events enabled.

## Adding Repos

Register the webhook on any repo where you want the squad active. The worker handles agent routing automatically based on file types and change patterns.

## License

Proprietary. Copyright (c) 2024-2026 BlackRoad OS, Inc. All rights reserved.

---

*Remember the Road. Pave Tomorrow.*
