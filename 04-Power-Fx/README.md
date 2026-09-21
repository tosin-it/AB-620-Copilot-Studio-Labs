# Lab 04 — Power Fx

## Objective

Use Power Fx in Microsoft Copilot Studio to transform and standardize user-provided data before presenting the result in an agent response.

## Scenario

An employee provides the name of a software application. The agent uses Power Fx to clean the input and standardize its capitalization before presenting the normalized application name.

## Topic

**Software Request Normalization**

Topic description:

> Normalize and standardize software application names from employee requests using Power Fx before presenting the request for IT processing.

## Implementation

The topic:

1. Asks the user for a software application name.
2. Stores the response in the `SoftwareRequest` topic variable.
3. Uses a Power Fx expression to normalize the value.
4. Stores the result in `StandardizedSoftware`.
5. Displays the standardized value in a confirmation message.

## Power Fx Formula

```text
Proper(Trim(Topic.SoftwareRequest))