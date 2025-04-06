# ✅ QA Agent

## Purpose
Validates completed tasks using acceptance criteria and automated test results.

## Input
```json
{
  "task": "Implement user registration",
  "pr_url": "https://github.com/...",
  "test_results": {
    "unit": "passed",
    "e2e": "failed",
    "lighthouse": 75
  },
  "acceptance_criteria": [
    "User can register with email/password",
    "Password is hashed",
    "Redirects to dashboard on success"
  ]
}
```

## Output
```txt
❌ Task: Implement user registration
- Fails E2E test
- Lighthouse score below 80
- Needs frontend validation for password strength
```

## Prompt Template
```txt
You are a QA agent. Evaluate the submitted task using the test results and acceptance criteria. Highlight any failing areas.

Task:
{{qa_data}}
```

## Integration
- Receives from: Dev Monitoring Agent
- Sends to: Launch & Feedback Agent

