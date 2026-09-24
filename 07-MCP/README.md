# Lab 07 — MCP

## Objective

Demonstrate how to integrate a Model Context Protocol (MCP) server with Microsoft Copilot Studio and use MCP tools to retrieve external information through an agent.

This lab uses the Microsoft Learn Docs MCP server to allow the IT Support Conversation Agent to search official Microsoft documentation and retrieve technical information dynamically.

---

## Scenario

An IT support agent needs access to current Microsoft technical documentation when answering technical questions.

Instead of relying only on the agent's existing knowledge sources, an MCP server is configured to provide access to Microsoft Learn documentation.

The test scenario uses an Intune Win32 application question to validate that the agent can invoke the Microsoft Learn MCP server and retrieve relevant Microsoft documentation.

---

## MCP Server

**Server Name:** Microsoft Learn Docs MCP

**Server Endpoint:**

`https://learn.microsoft.com/api/mcp`

**Authentication:** None

The Microsoft Learn MCP server provides tools that allow an agent to search and retrieve official Microsoft Learn documentation.

---

## MCP Tools Enabled

The following MCP tools were enabled:

### microsoft_docs_search

Searches official Microsoft/Azure documentation and returns relevant documentation content.

### microsoft_code_sample_search

Searches Microsoft Learn for relevant code samples and examples.

### microsoft_docs_fetch

Retrieves the full content of Microsoft Learn documentation identified through search.

---

## Copilot Studio Configuration

The MCP server was added to the:

**IT Support Conversation Agent**

The connection was successfully initialized and the MCP server became available as an agent tool.

The MCP configuration was validated by confirming that all three MCP tools were enabled.

---

## Implementation

The MCP server was configured in Copilot Studio using the following settings:

| Configuration | Value |
|---|---|
| MCP Server | Microsoft Learn Docs MCP |
| Endpoint | `https://learn.microsoft.com/api/mcp` |
| Authentication | None |
| Agent | IT Support Conversation Agent |
| Environment | Copilot-Studio-Lab |

The following MCP tools were enabled:

- `microsoft_docs_search`
- `microsoft_code_sample_search`
- `microsoft_docs_fetch`

---

## Testing

### Test Question

The following question was submitted to the agent:

> How do I create an Intune Win32 application?

### Expected Behavior

The agent should invoke the Microsoft Learn MCP server and retrieve relevant Microsoft documentation rather than relying only on the agent's existing knowledge.

### Observed Result

The test was successful.

The Copilot Studio test trace showed:

- Microsoft Learn Docs MCP initialized
- `microsoft_docs_search` executed
- MCP tool execution completed successfully
- Microsoft Learn/Intune documentation was returned
- The agent generated a response describing the process for creating an Intune Win32 application

The successful tool execution confirmed that the agent was able to use the MCP server during the conversation.

---

## AB-620 Practice Focus

This lab reinforces the following AB-620 concepts:

- Model Context Protocol (MCP)
- MCP server configuration
- MCP tools
- External tool integration
- Agent orchestration
- Microsoft Learn documentation retrieval
- Tool execution and validation
- Testing agent tool usage

The lab demonstrates how MCP can extend an agent beyond its built-in capabilities by providing access to external tools and information sources.

---

## Key Learning

MCP provides a standardized way for agents to interact with external tools and services.

In this implementation, Microsoft Learn Docs MCP provides the IT Support Conversation Agent with access to official Microsoft technical documentation.

The test also demonstrated the importance of validating actual tool execution rather than only verifying that the MCP server appears as connected.

The Copilot Studio trace confirmed that `microsoft_docs_search` was actually invoked and completed successfully during the test.

---

## Screenshots

### 1. MCP Tools Configured

`Screenshots/01-Microsoft-Learn-MCP-Tools-Configured.png`

Shows:

- Microsoft Learn Docs MCP server
- Connected MCP configuration
- `microsoft_docs_search` enabled
- `microsoft_code_sample_search` enabled
- `microsoft_docs_fetch` enabled

### 2. Successful MCP Test

`Screenshots/02-Successful-MCP-Intune-Search.png`

Shows:

- Test question about creating an Intune Win32 application
- Microsoft Learn Docs MCP initialized
- `microsoft_docs_search` tool execution
- Completed MCP tool call
- Microsoft Learn/Intune documentation returned to the agent

---

## Lab Outcome

The Microsoft Learn Docs MCP server was successfully integrated with the IT Support Conversation Agent.

The agent successfully invoked the MCP search tool and retrieved Microsoft Learn documentation in response to an Intune technical question.

This demonstrates practical MCP integration within Microsoft Copilot Studio and provides hands-on experience relevant to the AB-620 AI Agent Builder Associate certification.

---

## Technologies

- Microsoft Copilot Studio
- Model Context Protocol (MCP)
- Microsoft Learn Docs MCP
- Microsoft Intune
- Microsoft 365
- Generative AI orchestration
