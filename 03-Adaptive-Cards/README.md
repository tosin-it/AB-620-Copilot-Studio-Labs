# Lab 03 — Adaptive Cards

## Objective

Build an interactive software license request form using an Adaptive Card in Microsoft Copilot Studio.

## Scenario

An employee needs to request software that requires an IT-managed license. The agent presents an interactive form that collects the request details and returns a confirmation containing the submitted information.

## Topic

**Software License Request**

Topic description:

> Create an interactive software license request form using an Adaptive Card that captures the requested application, license type, business justification, and urgency for IT review.

## Adaptive Card

The Adaptive Card collects four pieces of structured input:

- **Application Name**
- **License Type**
  - New License
  - Additional License
  - License Renewal
- **Business Justification**
- **Urgency**
  - Low
  - Normal
  - High

The card uses the `Ask with adaptive card` node so the agent can wait for the user's submission and capture the submitted values.

## Output Variables

The Adaptive Card automatically generated the following output properties:

- `applicationName`
- `licenseType`
- `businessJustification`
- `urgency`

These variables are used in the confirmation message after the card is submitted.

## Implementation Flow

```text
User
  |
  v
Software License Request Topic
  |
  v
Ask with Adaptive Card
  |
  +--> applicationName
  +--> licenseType
  +--> businessJustification
  +--> urgency
  |
  v
Confirmation Message