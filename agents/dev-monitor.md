# 📈 Dev Monitoring Agent

## Purpose
Monitors developer activity on GitHub, PR reviews, CI/CD status, and flags bottlenecks.

## Input
```json
{
  "tasks": [
    {
      "title": "Implement login",
      "status": "in_progress",
      "assignee": "@dev1",
      "pr_link": "https://github.com/...",
      "ci_status": "failing"
    }
  ]
}
```

## Output
Alerts and summaries:
```txt
🚨 PR #42 (Implement login) is failing CI.
👀 PR #37 (Navbar UI) has been idle for 2 days without review.
✅ All backend tasks for Sprint 1 are complete.
```

## Prompt Template
```txt
You are a dev monitoring agent. Analyze PRs, CI/CD statuses, and developer activity. Identify issues and generate a daily summary.

Input:
{{task_data}}
```

## Integration
- Receives from: Planner Agent
- Sends to: QA Agent

