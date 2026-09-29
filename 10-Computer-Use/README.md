# Lab 10 — Computer Use

## Objective

Demonstrate how Microsoft Copilot Studio Computer Use can interact with web-based applications, perform multi-step tasks, enter structured information, process documents, and extract information from a user interface.

## Scenario

Computer Use was tested against multiple simulated business applications to validate UI navigation, data entry, document processing, and information extraction.

## Tests Performed

### Test 1 — Inventory Data Entry

The agent interacted with the Adventure Works Cycles inventory application.

The agent:

1. Opened the inventory application.
2. Entered product information.
3. Submitted five inventory records.
4. Verified the submitted records in the Inventory Items section.

**Records processed:**

| Product | Product ID | Quantity | Price | Supplier |
|---|---|---:|---:|---|
| Rear Derailleur | RD-4821 | 50 | $42.75 | Shimano |
| Pedal Set | PD-1738 | 80 | $19.99 | Northwind Traders |
| Brake Lever | BL-2975 | 35 | $14.50 | Trey Research |
| Chainring Bolt Set | CB-6640 | 100 | $5.25 | VanArsdel, Ltd. |
| Bottom Bracket | BB-9320 | 60 | $24.90 | Tailwind Traders |

**Result:** Successfully submitted and verified all five inventory records.

---

### Test 2 — Invoice Processing

The agent interacted with a simulated invoice management portal.

The agent:

1. Opened the invoice management application.
2. Processed invoice information from a PDF.
3. Extracted vendor and invoice details.
4. Entered invoice line-item information.
5. Submitted the invoice.
6. Verified the successful submission and reference number.

**Data extracted:**

- Vendor Name: Tech Supplies USA LLC
- Invoice Number: INV-2025-0089
- Invoice Date: 04/03/2025
- Due Date: 18/03/2025
- Total Amount: $4,235
- Line items and quantities
- Unit prices
- Line-item amounts

**Result:** Invoice was successfully submitted and confirmed in the application.

---

### Test 3 — Financial Portfolio Data Extraction

The agent interacted with a simulated financial portfolio dashboard.

The agent:

1. Opened the financial portfolio dashboard.
2. Navigated through the portfolio table.
3. Located the requested portfolio record.
4. Extracted the portfolio manager and current portfolio value.

**Extracted data:**

| Field | Value |
|---|---|
| Portfolio Manager | Yhlas Geldjyev |
| Current Portfolio Value | $190,000,000 |

**Result:** Successfully located and extracted the requested information from the web application.

---

## Validation Results

| Test | Computer Use Task | Result |
|---|---|---|
| 1 | Inventory data entry | Successful |
| 2 | Invoice processing | Successful |
| 3 | Financial portfolio extraction | Successful |

All three Computer Use scenarios completed successfully.

## Screenshots

The `Screenshots` folder contains evidence of the Computer Use tests:

- `01-Computer-Use-Data Entry-Tools-Details.png`
- `02-Computer-Use-Inv Processing-Test-Completed.png`
- `03-Computer-Use-Inv Processing-Tools-Details.png`
- `04-Computer-Use-Data Entry-Test-Completed.png`
- `05-Computer-Use-Data Extraction-Test-Completed.png`
- `06-Computer-Use-Data Extraction-Tools-Details.png`

## Skills Demonstrated

- Microsoft Copilot Studio
- Computer Use
- Browser automation
- Multi-step UI interaction
- Web application navigation
- Structured data entry
- Document/invoice data extraction
- Information retrieval from web interfaces
- Data validation
- Task completion verification

## Key Takeaway

Computer Use was demonstrated across different business scenarios where the agent needed to interact with applications through the user interface rather than relying solely on a direct API or connector.