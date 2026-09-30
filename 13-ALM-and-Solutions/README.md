# Lab 13 — ALM & Solutions

## Objective

Demonstrate application lifecycle management (ALM) for a Microsoft Copilot Studio agent by packaging the agent and its dependencies into a solution and exporting the solution as a managed deployment package.

## Scenario

The IT Support Conversation Agent has been developed through multiple Copilot Studio labs.

This lab demonstrates how the agent can be packaged into a Power Platform solution so that its components and dependencies can be managed and moved through an application lifecycle.

## Solution

**Solution:** AB-620 ALM Lab

**Version:** 1.0.0.1

**Export Type:** Managed

## Solution Components

The solution contains the IT Support Conversation Agent and its associated components.

During the export process, Copilot Studio identified additional unmanaged dependencies and allowed them to be added to the solution:

- IT Equipment Request workflow
- Employee Onboarding workflow
- Connection references
- IT Software Catalog Dataverse search component

The solution ultimately contained the required agent components and dependencies for deployment.

## ALM Workflow

The following lifecycle was demonstrated:

1. Created a dedicated solution.
2. Added the existing IT Support Conversation Agent.
3. Included associated agent components and dependencies.
4. Published all customizations.
5. Reviewed required unmanaged dependencies.
6. Added the required dependencies to the solution.
7. Selected managed export.
8. Enabled Solution Checker during export.
9. Exported the solution successfully.
10. Downloaded the resulting managed solution package.

## Deployment Package

The exported managed solution was downloaded as a `.zip` package.

The package represents the deployable solution artifact produced by the ALM process.

## AB-620 Practice Focus

This lab reinforces:

- Power Platform solutions
- Copilot Studio solution management
- Solution components
- Dependencies
- Connection references
- Managed solutions
- Solution export
- Solution Checker
- Deployment artifacts
- Application lifecycle management

## Key Learning

A Copilot Studio agent is not always a standalone component. Enterprise deployment can require packaging the agent together with its related topics, workflows, knowledge components, Dataverse dependencies, and connection references.

Reviewing dependencies before export is an important part of preparing a solution for deployment.

Managed solution export provides a deployable package that can be used as part of a controlled application lifecycle.

## Evidence

Screenshots:

- `Screenshots/01-ALM-Solution-Agent-and-Components.png`

## Lab Outcome

Successfully packaged the IT Support Conversation Agent and its required dependencies into a dedicated Power Platform solution and exported the solution as a managed deployment package with Solution Checker enabled.