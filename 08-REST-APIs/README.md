# Lab 08 — REST APIs

## Objective

Demonstrate how to integrate a REST API with Microsoft Copilot Studio using an OpenAPI specification and expose the API operation as an agent tool.

This lab uses a public REST API to retrieve task information and demonstrate how Copilot Studio can call an external API and use the returned data in a natural-language response.

---

## Scenario

An IT support agent needs to retrieve the status of a task from an external REST API.

The agent should be able to accept a task ID from the user, call the REST API, retrieve the task record, and summarize the result.

Example request:

> What is the status of task 20?

The agent uses the REST API tool to retrieve the corresponding task record.

---

## REST API

The lab uses the public JSONPlaceholder REST API.

**API host:**

`https://jsonplaceholder.typicode.com`

**Endpoint:**

`GET /todos/{id}`

The endpoint returns task information including:

- User ID
- Task ID
- Task title
- Completion status

No authentication is required.

---

## OpenAPI Specification

The REST API was defined using an OpenAPI 2.0 specification.

The specification file is:

`IT-Task-Status-API.json`

The OpenAPI specification defines:

- API metadata
- HTTPS connection
- REST endpoint
- `id` path parameter
- Response schema
- Task output properties

The specification tells Copilot Studio how to construct and interpret calls to the REST API. The actual task data is retrieved from the external JSONPlaceholder API at runtime.

---

## Copilot Studio Configuration

The REST API was added to the:

**IT Support Conversation Agent**

### API Plugin

**Tool name:**

`IT Task Status API`

**Authentication:**

`None`

### REST Operation

**Operation:**

`Get task status`

**Description:**

`Retrieves a sample task and its completion status.`

### Input

| Input | Type | Description |
|---|---|---|
| `id` | Number | Task ID. |

### Outputs

| Output | Type | Description |
|---|---|---|
| `userId` | Number | ID of the user associated with the task. |
| `id` | Number | ID of the task. |
| `title` | String | Title of the task. |
| `completed` | Boolean | Indicates whether the task has been completed. |

---

## Implementation

The REST API was integrated through the Copilot Studio **Add a tool → REST API** workflow.

The implementation included:

1. Creating an OpenAPI 2.0 specification.
2. Uploading the specification to Copilot Studio.
3. Configuring the API plugin details.
4. Selecting no authentication because the API is public.
5. Selecting the `Get task status` operation.
6. Configuring the `id` input parameter.
7. Configuring the API output descriptions.
8. Reviewing and publishing the REST API tool.
9. Testing the tool through the agent.

---

## Testing

### Test 1 — Task 1

The following request was submitted:

> What is the status of task 1?

The REST API returned:

- Task ID: `1`
- Title: `delectus aut autem`
- User ID: `1`
- Completed: `false`

The agent correctly reported that task 1 was not completed.

---

### Test 2 — Task 20

The following request was submitted:

> What is the status of task 20?

The REST API returned:

- Task ID: `20`
- Title: `ullam nobis libero sapiente ad optio sint`
- User ID: `1`
- Completed: `true`

The agent correctly reported that task 20 was completed.

---

### Test 3 — Revalidation

The agent was asked:

> Are you sure task 20 has been completed?

The agent checked task 20 again and returned the API record showing:

- Task ID: `20`
- Completed: `true`

This demonstrated that the agent could invoke the REST API again rather than relying only on the previous conversational response.

---

## API Data Flow

The implementation follows this flow:

```text
User
  |
  v
IT Support Conversation Agent
  |
  v
Get task status REST Tool
  |
  v
GET /todos/{id}
  |
  v
JSONPlaceholder REST API
  |
  v
JSON Response
  |
  v
Copilot Studio
  |
  v
Natural-Language Response