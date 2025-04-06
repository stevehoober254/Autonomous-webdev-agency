# 🧠 Input Parser Agent

## Purpose
Extracts structured goals, scope, and features from raw client inputs such as emails, forms, or call transcripts.

## Input
- Raw client text

## Output
```json
{
  "project_name": "string",
  "goals": ["string"],
  "features": ["string"],
  "constraints": ["string"]
}
```

## Prompt Template
```txt
You are an input parsing agent. Extract project name, goals, features, and constraints from this client input.

Client Input:
{{client_input}}
```

## Integration
- Triggers: New client request via form/email/transcript
- Sends to: PRD Generator Agent
