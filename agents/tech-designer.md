# 🧱 Tech Design Agent (RFC)

## Purpose
Translates the PRD into a technical design document, highlighting architectural decisions, tools, and trade-offs.

## Input
```md
# Product Requirements Document
... (content from PRD Agent)
```

## Output
A markdown-based RFC (Request for Comments):
```md
# Request for Comments (RFC)

## Overview
Brief summary of what the system will do.

## Tech Stack
- Frontend: React + Tailwind
- Backend: Node.js + Express
- Database: PostgreSQL

## Architecture Diagram
(Insert ASCII or mermaid)

## APIs / Modules
- Auth Service
- Data Service

## Trade-offs
- Chose X for speed, Y for scalability

## Risks
- Integration delays, scaling costs
```

## Prompt Template
```txt
You are a technical design agent. Based on this PRD, create an RFC that outlines the architecture, tools, APIs, and trade-offs.

PRD:
{{prd}}
```

## Integration
- Receives from: PRD Generator Agent
- Sends to: Planner Agent

