# Lab 11 — Testing & Evaluation

## Objective

Evaluate the quality of an AI agent using Microsoft Copilot Studio's built-in evaluation capabilities.

## Scenario

The IT Support Conversation Agent was evaluated using a targeted test set based on capabilities implemented in previous labs.

The evaluation focused on whether the agent's responses were semantically consistent with the expected responses.

## Evaluation Configuration

**Test Set:** Lab 12 - IT Support Quality Evaluation

**Data Type:** Single response

**Evaluation Method:**
- Answer quality
- Meaning match

## Test Cases

The evaluation included five scenarios:

1. Windows Wi-Fi troubleshooting
2. Second monitor request
3. Microsoft Visio license lookup
4. Lost or stolen company laptop
5. Second monitor request including business justification

## Evaluation Results

| Metric | Result |
|---|---:|
| Answer Quality | 100% |
| Meaning Match | 40% |
| Test Cases | 5 |
| Meaning Match Passed | 2 |
| Meaning Match Failed | 3 |

### Passing Results

The Microsoft Visio license lookup and lost/stolen laptop scenarios passed the Meaning Match evaluation.

### Evaluation Findings

The three failed Meaning Match cases demonstrated differences between the expected responses and the agent's actual conversational behavior.

For the Windows Wi-Fi scenario, the agent began its diagnostic conversation by asking whether the device could connect to Wi-Fi or had no internet access.

For the second-monitor scenarios, the agent routed the request into the equipment-request workflow and asked the user to provide equipment details rather than directly matching the expected response.

These results demonstrate that an agent can receive a passing Answer Quality result while still failing a more specific semantic evaluation criterion.

## AB-620 Practice Focus

This lab reinforces:

- Agent testing and evaluation
- Evaluation test sets
- Single-response testing
- Answer quality evaluation
- Meaning Match evaluation
- Interpreting evaluation failures
- Identifying differences between expected and actual agent behavior

## Key Learning

Evaluation results should be analyzed rather than treated as simple pass/fail measurements.

The evaluation identified specific conversational behaviors that differed from the expected responses. This provides actionable information for improving test cases, expected responses, or agent behavior.

## Evidence

Screenshot:

`Screenshots/01-Evaluation-Test-Cases.png`
`Screenshots/02-Meaning-Match-Evaluation-Results.png`

## Lab Outcome

Successfully created and executed a Copilot Studio evaluation test set and analyzed the resulting Answer Quality and Meaning Match scores.