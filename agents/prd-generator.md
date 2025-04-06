# 📄 PRD Generator Agent

## Purpose
Transforms parsed client input into a structured Product Requirements Document (PRD).

## Input
```json
{
  "project_name": "string",
  "goals": ["string"],
  "features": ["string"],
  "constraints": ["string"]
}
```

## Output
A markdown-based PRD document:
```md
# Product Requirements Document

## Project Name
{{project_name}}

## Goals
- Goal 1
- Goal 2

## Features
- Feature 1
- Feature 2

## Constraints
- Constraint 1
- Constraint 2
```

## Prompt Template
```txt
You are a PRD drafting agent. Based on the structured input below, generate a detailed product requirements document in markdown format.

Input:
{{parsed_input}}
```

## Integration
- Receives from: Input Parser Agent
- Sends to: Tech Design Agent (RFC)

