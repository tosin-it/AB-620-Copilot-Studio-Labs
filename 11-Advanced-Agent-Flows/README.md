# Lab 11 — Advanced Agent Flows: Automation / Orchestration

## Objective

Demonstrate how Microsoft Copilot Studio Agent Flows can orchestrate multiple actions to automate an employee onboarding process.

## Use Case

An employee onboarding request is submitted through the IT Support Conversation Agent.

The Agent Flow receives the employee information, generates an onboarding summary, sends an Outlook notification, and returns a confirmation to the agent.

## Architecture

```text
User
  ↓
Copilot Studio IT Support Conversation Agent
  ↓
Employee Onboarding Orchestration
  ↓
When an agent calls the flow
  ↓
Compose
  ↓
Send an email (V2)
  ↓
Compose 1
  ↓
Respond to the agent
  ↓
Agent returns confirmation to user
