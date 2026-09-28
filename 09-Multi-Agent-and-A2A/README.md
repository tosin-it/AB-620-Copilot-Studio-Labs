# Lab 09 — Multi-Agent and A2A

## Objective

Demonstrate a multi-agent architecture in Microsoft Copilot Studio by creating a specialized child agent and delegating an appropriate support request from the parent agent.

This lab also explores the Agent2Agent (A2A) integration option available in Copilot Studio and documents the distinction between local child-agent delegation and external A2A agent connections.

---

## Scenario

The organization uses an internal IT support agent as the primary employee-facing assistant.

Some support activities are handled by a third-party Managed Services Provider (MSP). The internal IT agent can delegate appropriate requests to a specialized MSP agent.

### Parent Agent

**IT Support Conversation Agent**

Responsible for:

- General internal IT support
- Employee-facing assistance
- Internal IT knowledge
- Internal IT workflows and tools

### Child Agent

**Managed Services Provider Agent**

Responsible for:

- Outsourced IT support
- Managed endpoint services
- MSP troubleshooting coordination
- Incident escalation to the external provider

This separation prevents the MSP agent from making internal IT policy or authorization decisions.

---

## Child Agent Configuration

### Name

`Managed Services Provider Agent`

### Description

> Represent a third-party managed service provider that handles outsourced IT support, managed endpoint services, and incident escalation requests.

### Usage

The agent is configured to be selected by the parent agent based on its description.

### Instructions

The child agent was instructed to:

- Act as a third-party MSP supporting the internal IT team.
- Handle outsourced IT service requests.
- Coordinate managed endpoint support.
- Handle incident escalation.
- Avoid acting as the organization's internal IT department.
- Avoid making internal IT policy decisions.
- Avoid approving hardware, software, access, or security requests.
- Refer internal authorization decisions back to the internal IT team.

---

## Child Agent Input

The child agent accepts a required string input:

**Support Request**

Description:

> The IT support issue or incident that requires assistance from the managed service provider.

This allows the parent agent to pass the employee's support request to the specialized MSP agent.

---

## Child Agent Output

The child agent returns a string output:

**MSP Response**

Description:

> The response from the managed service provider regarding the submitted support request.

The parent agent can use this output when constructing its final response to the user.

---

## Delegation Test

### User Request

The following request was submitted to the parent agent:

> My company laptop keeps disconnecting from the VPN every 10 minutes. This needs to be handled by our external MSP.

### Expected Behavior

The parent agent should recognize that the request is appropriate for the external MSP and delegate the request to the:

`Managed Services Provider Agent`

### Observed Result

The delegation was successful.

The Copilot Studio trace showed:

- `Managed Services Provider Agent` — Completed
- `SupportRequest` passed to the child agent
- `MSPResponse` returned by the child agent
- Parent agent incorporated the child-agent response into the final answer

The child agent identified the recurring VPN issue as an MSP-supported incident and recommended escalation to the MSP support team.

It also maintained the responsibility boundary by noting that internal approvals, policy decisions, and access decisions remain the responsibility of the internal IT team.

---

## Multi-Agent Flow

```text
Employee
   |
   v
IT Support Conversation Agent
   |
   | Determine specialized responsibility
   v
Managed Services Provider Agent
   |
   | MSP Response
   v
IT Support Conversation Agent
   |
   v
Employee Response