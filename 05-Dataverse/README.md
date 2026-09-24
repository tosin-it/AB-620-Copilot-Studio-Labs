# Lab 05 Dataverse

## Objective

Use Microsoft Dataverse as a structured data source for a Copilot Studio agent and enable employees to look up software licensing information using natural-language requests.

## Scenario

The IT department maintains a software catalog containing application, licensing, business unit, approval, and availability information.

Employees can ask questions such as:

> Do we have Microsoft Visio license available?

The agent identifies the software from the user's request and retrieves the relevant information from Dataverse.

## Dataverse Table

**Table:** `IT Software Catalog`

Columns:

| Column | Type |
|---|---|
| Software Name | Single line of text |
| License Type | Single line of text |
| Business Unit | Single line of text |
| Approval Required | Yes/No |

## Sample Data

| Software | License Type | Business Unit | Approval Required |
|---|---|---|---|
| Microsoft Visio | New License | IT | Yes |
| Microsoft Project | New License | Project Management | Yes |
| Adobe Acrobat Pro | Additional License | Finance | No |

## Copilot Studio Implementation

The **Software Catalog Lookup** topic uses a topic input:

`SoftwareLookup`

The input is dynamically filled from the user's natural-language request.

Example:

> Do we have Microsoft Visio license available?

The agent identifies **Microsoft Visio** as the software lookup value and uses the Dataverse IT Software Catalog as the selected knowledge source.

This design avoids asking the user to repeat information that was already included in the original request.

## Testing

### Positive Test

User request:

> Do we have Microsoft Visio license available?

The agent successfully retrieved the Dataverse record and returned:

- License Type: New License
- Approval Required: Yes
- Business Unit: IT
- Status: Active

A Dataverse reference was also returned with the response.

### Negative Test

User request:

> Do we have Nitro Pro license available?

Nitro Pro was not present in the Dataverse catalog.

The agent completed the lookup without inventing licensing information and indicated that no catalog details were available for the requested software.

This validates behavior when a requested record does not exist in the structured data source.

## AB-620 Practice Focus

This lab reinforces the **Integrate and extend agents in Copilot Studio** skill area.

Key concepts practiced:

- Dataverse tables
- Structured business data
- Dataverse knowledge sources
- Topic input variables
- Dynamic input filling
- Generative orchestration
- Natural-language information retrieval
- Positive and negative testing
- Handling missing records without fabricating information

## Key Learning

A topic input can capture information directly from the user's original request, eliminating unnecessary follow-up questions.

Using Dataverse as a structured knowledge source allows the agent to retrieve business-specific information while maintaining a clear source reference.

Testing with a software application that does not exist in the catalog also demonstrated the importance of validating how the agent behaves when no matching record is available.

## Screenshots

- `Screenshots/01-IT-Software-Catalog-Data.png`
- `Screenshots/02-Software-Catalog-Lookup-Topic.png`
- `Screenshots/03-Successful-Dataverse-Lookup.png`
- `Screenshots/04-Dataverse-No-Matching-Record.png`