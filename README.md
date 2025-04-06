# 🚀 Web Development Automation with AI Agents

This repository contains a modular web development pipeline powered by AI agents and orchestrated using **n8n**. The goal is to automate the entire web development process, from parsing client inputs to collecting post-launch feedback, with minimal human intervention.

![System Diagram](./A_README_file_displays_"Web_Development_Automation.png)

### 🚀 Overview

This system leverages a series of AI agents, each responsible for specific tasks in the web development lifecycle. The agents are orchestrated through **n8n**, an open-source automation tool that enables the integration of various processes and services into a cohesive workflow.

### 🛠️ Key Features

1. **Input Parser Agent**: Parses incoming client input and structures it for use in the pipeline.
2. **PRD Generator Agent**: Generates a Product Requirement Document (PRD) from the parsed client input.
3. **Tech Design Agent (RFC)**: Converts the PRD into a Technical Design Document (RFC).
4. **Planner Agent**: Breaks down the RFC into tasks and assigns them to the development team.
5. **Dev Monitoring Agent**: Monitors the progress of development tasks and provides status updates.
6. **QA Agent**: Runs tests and generates QA reports.
7. **Launch & Feedback Agent**: Collects user feedback post-launch and suggests improvements.

### 🌍 Architecture

The entire pipeline is modularized into separate workflows, each representing a different phase of the development cycle. These workflows are triggered and coordinated using **n8n Agent Nodes**. The agent nodes handle the orchestration, data passing, and error handling between the sub-workflows.

### 🧩 Workflow Breakdown

1. **Main Workflow**: Coordinates the execution of all agent workflows.
   - **Sub-Workflows**: 
     - `input-parser-workflow`: Handles input parsing.
     - `prd-generator-workflow`: Generates the PRD.
     - `tech-designer-workflow`: Creates the RFC.
     - `planner-workflow`: Breaks down the RFC into tasks.
     - `dev-monitoring-workflow`: Monitors development progress.
     - `qa-workflow`: Handles quality assurance.
     - `launch-feedback-workflow`: Collects feedback after launch.

2. **Agent Nodes**: Each sub-workflow is triggered via an **n8n Agent Node**, making the system modular and scalable.

### 🔧 Setup Instructions

1. **Install n8n**:
   - Follow the [n8n installation guide](https://n8n.io/docs/).
   - Alternatively, you can deploy n8n using Docker for ease.

2. **Create Workflows**:
   - Create a workflow for each agent (Input Parser, PRD Generator, etc.) in **n8n**.
   - Each workflow will contain the specific nodes and logic to perform its designated task.

3. **Integrate Workflows**:
   - In the **Main Workflow**, use **Agent Nodes** to trigger each sub-workflow in sequence.
   - Ensure the correct flow of data between workflows using **n8n Variables** and **Expressions**.

4. **Triggering the Workflow**:
   - The Main Workflow can be triggered either manually or automatically via a **Webhook**.
   - Each agent workflow will execute sequentially or conditionally based on input data.

5. **Monitor & Optimize**:
   - Use the **n8n Dashboard** to monitor workflow execution and make adjustments as necessary.
   - Implement error handling to ensure smooth workflow execution.

### 🔗 Integrations

- **Slack**: Notify team members about progress and task assignments.
- **GitHub/GitLab**: Monitor pull requests and commit statuses for development progress.
- **Trello/Asana**: Automatically create tasks for each step in the development cycle.
- **Google Sheets**: Track and store the progress of the project.
- **Jenkins**: Trigger and monitor automated tests for quality assurance.

### ⚙️ Example Workflow

The following is an example of a **Main Workflow** orchestrated using **Agent Nodes** in **n8n**:

```json
{
  "nodes": [
    {
      "parameters": {
        "workflowId": "input-parser-workflow-id"
      },
      "name": "Input Parser Agent",
      "type": "n8n-nodes-base.agent",
      "typeVersion": 1,
      "position": [200, 300]
    },
    {
      "parameters": {
        "workflowId": "prd-generator-workflow-id"
      },
      "name": "PRD Generator Agent",
      "type": "n8n-nodes-base.agent",
      "typeVersion": 1,
      "position": [400, 300]
    },
    {
      "parameters": {
        "workflowId": "tech-designer-workflow-id"
      },
      "name": "Tech Design Agent",
      "type": "n8n-nodes-base.agent",
      "typeVersion": 1,
      "position": [600, 300]
    }
  ]
}
```

**This JSON represents the orchestration of the sub-workflows using Agent Nodes.**

### 📑 Documentation for Agents
Each agent has its own markdown documentation file explaining its purpose, input/output, and configuration. These are stored in the agents/ directory.

### 🔒 Security
Ensure that all workflows and data are properly secured, especially when integrating with external services like Slack, GitHub, or Google Sheets. Use appropriate authentication methods (OAuth, API keys) for each integration.

### 🚀 License
This project is licensed under the MIT License - see the LICENSE file for details.
