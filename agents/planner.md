# 🗂️ Planner Agent

## Purpose
Breaks down the RFC into actionable engineering tasks and assigns them to appropriate domains (frontend, backend, DevOps).

## Input
```md
# Request for Comments (RFC)
... (content from Tech Design Agent)
```

## Output
```json
{
  "tasks": [
    {
      "title": "Set up project boilerplate",
      "description": "Initialize monorepo with Turborepo",
      "tags": ["devops"]
    },
    {
      "title": "Design landing page",
      "description": "Create responsive UI in Tailwind",
      "tags": ["frontend"]
    }
  ]
}
```

## Prompt Template
```txt
You are a sprint planning agent. Break down the RFC into clear engineering tasks grouped by domain (frontend, backend, devops).

RFC:
{{rfc}}
```

## Integration
- Receives from: Tech Design Agent (RFC)
- Sends to: Dev Monitoring Agent

