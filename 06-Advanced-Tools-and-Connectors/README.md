# Lab 06 Advanced Tools and Connectors

## Objective

Use a Microsoft 365 connector as an agent tool in Copilot Studio to retrieve information from Outlook.

## Scenario

An employee asks the IT support agent whether they have recent emails. The agent uses the Office 365 Outlook connector to retrieve recent messages and summarize the relevant information.

## Connector

**Connector:** Office 365 Outlook

**Action:** Get emails (V3)

**Connection:** Microsoft 365 Outlook

The connector was added as an agent tool and enabled for the IT Support Conversation Agent.

## Implementation

The agent uses the Outlook connector to:

1. Receive a natural-language request from the user.
2. Determine that recent email information is required.
3. Invoke the `Get emails (V3)` connector action.
4. Retrieve recent messages from the connected mailbox.
5. Summarize the relevant email information for the user.

## Testing

Test request:

> Do I have any recent emails?

The connector successfully retrieved recent Microsoft 365 emails and the agent summarized the results.

The test demonstrated that the agent can use an external Microsoft 365 service through a prebuilt connector action rather than relying only on static knowledge sources.

## AB-620 Practice Focus

This lab reinforces the **Integrate and extend agents in Copilot Studio** skill area.

Key concepts practiced:

- Agent tools
- Power Platform connectors
- Microsoft 365 integration
- Office 365 Outlook connector
- Connector actions
- External service integration
- Generative orchestration
- Testing connector-based agent actions

## Key Learning

Connectors allow Copilot Studio agents to interact with external services and retrieve live business information.

The Office 365 Outlook connector provided a practical example of extending an agent beyond knowledge retrieval by allowing it to access information from a connected Microsoft 365 service.

## Screenshots

- `Screenshots/01-Outlook-Get-Emails-Tool.png`
- `Screenshots/02-Successful-Outlook-Connector-Test.png`