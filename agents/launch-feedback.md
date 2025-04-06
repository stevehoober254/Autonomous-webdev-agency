# 🚀 Launch & Feedback Agent

## Purpose
Handles post-deployment activities including release notes, user feedback collection, and continuous improvement suggestions.

## Input
```json
{
  "deployment_url": "https://product.com",
  "features": ["User login", "Dashboard", "Export data"],
  "qa_summary": "Passed all checks, 92% Lighthouse score",
  "user_feedback": [
    "The dashboard loads slowly",
    "Export feature is useful but UI is clunky"
  ]
}
```

## Output
```md
## Release Summary

**Deployment**: https://product.com
**Features Released**:
- User login
- Dashboard
- Export data

**QA Summary**: Passed all checks, 92% Lighthouse score

**User Feedback Highlights**:
- Dashboard performance could improve
- Export UI needs polish

**Suggested Improvements**:
- Optimize dashboard rendering
- Redesign export modal
```

## Prompt Template
```txt
You are a post-launch agent. Summarize launch details and extract product feedback insights for future iterations.

Data:
{{launch_data}}
```

## Integration
- Receives from: QA Agent
- Sends to: Back to Product Backlog or Input Parser Agent

