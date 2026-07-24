# AI Lead Enrichment and Qualification System

An AI-powered n8n workflow that reviews lead records, generates factual business descriptions, scores lead quality, and classifies each lead as HOT, WARM, or COLD.

## Project Overview

This automation helps businesses review lead lists more efficiently and identify which prospects are worth contacting.

The workflow reads lead information from Google Sheets, processes each eligible record with OpenAI, and writes the qualification results back to the same spreadsheet.

## Business Problem

Businesses often collect lead information without having a clear way to evaluate its completeness or quality.

Manually reviewing every lead can be repetitive and time-consuming, especially when the list contains incomplete or inconsistent information.

## Solution

This system automatically:

- Reads lead records from Google Sheets
- Skips leads that have already been processed successfully
- Marks each active lead as processing
- Generates a factual business description using the available information
- Assigns a qualification score from 1 to 10
- Classifies the lead as HOT, WARM, or COLD
- Updates the original Google Sheet with the results
- Marks completed records as successful

## Key Features

- Automated lead-list review
- AI-generated business descriptions
- Lead scoring from 1–10
- HOT, WARM, and COLD classification
- Google Sheets record updates
- Duplicate-processing prevention
- Processing-status tracking
- Controlled delay between workflow cycles
- Structured OpenAI JSON output

## Tools and Technologies

| Tool | Purpose |
|---|---|
| n8n | Workflow orchestration and automation |
| OpenAI | Lead analysis, description generation, scoring, and classification |
| Google Sheets | Lead storage, input, and result tracking |
| JSON | Workflow export and structured AI response format |

## System Architecture

```text
Manual Trigger
      ↓
Read Leads from Google Sheets
      ↓
Check Processing Status
      ↓
Loop Through Eligible Leads
      ↓
Mark Lead as Processing
      ↓
OpenAI Analysis
      ↓
Generate Description, Score, and Status
      ↓
Update Google Sheets
      ↓
Mark Lead as Successful
      ↓
Wait and Continue

```

## Workflow Screenshot

![AI Lead Enrichment and Qualification System](screenshots/system-overview.png)


## Sample Data

This repository includes fictional sample data for testing and demonstration:

- [View sample input](sample-data/sample-input.json)
- [View sample output](sample-data/sample-output.json)

The sample names, businesses, email addresses, and other details are fictional. No real lead or customer information is included.

## Included Workflow File

```text
workflows/
└── ai-lead-enrichment-qualification-workflow.json
```

The JSON file is a sanitized public portfolio version of the working n8n workflow.

## Installation and Import

1. Download `workflows/ai-lead-enrichment-qualification-workflow.json`.
2. Open your n8n workspace.
3. Create a blank workflow.
4. Open the workflow menu.
5. Select the option to import a workflow from a file.
6. Upload the downloaded JSON file.
7. Connect your own Google Sheets credentials.
8. Connect your own OpenAI credentials.
9. Replace `YOUR_GOOGLE_SHEET_ID` with your spreadsheet ID.
10. Test the workflow with fictional data first.

## Expected Google Sheets Columns

```text
Name
Business
Niche
Email
Website
Location
Lead Source
Description
Score
Status
Stage

## Required Integrations

- n8n
- OpenAI API access
- Google Sheets
- A Google Sheet containing the expected columns

## Environment Setup

The repository includes a `.env.example` file containing placeholders only:

```env
OPENAI_API_KEY=YOUR_OPENAI_API_KEY
GOOGLE_SHEET_ID=YOUR_GOOGLE_SHEET_ID
```

Do not upload real API keys, passwords, OAuth tokens, credential files, or private spreadsheet IDs.

Configure the actual OpenAI and Google Sheets credentials securely inside n8n.

## Testing Information

The workflow has been completed and is working.

It has been tested to:

- Read lead records from Google Sheets
- Identify records that have not been completed successfully
- Process leads individually
- Mark active records as `Processing...`
- Return structured OpenAI output
- Write descriptions, scores, and statuses back to Google Sheets
- Mark completed records as `Successful`

## Current Project Status

**Completed and working**

This repository is a sanitized demonstration of a personal portfolio project built by Joshua Asegunloluwa Akanni.

## Security and Privacy

Before publication, the workflow was reviewed and sanitized.

The following information was removed or replaced:

- Google Sheet IDs
- Direct spreadsheet URLs
- Google Sheets credential identifiers
- OpenAI credential identifiers
- Webhook identifiers
- n8n instance identifiers
- Workflow version identifiers
- Error-workflow identifiers
- Private execution information

This repository does not include real API keys, passwords, OAuth tokens, customer records, client records, or private lead information.

## Known Limitations

- The workflow evaluates only the information already available in the spreadsheet.
- It does not independently verify whether lead information is accurate.
- It does not currently collect new data from external enrichment services.
- Missing information can reduce a lead’s score.
- Qualification rules may need adjustment for different industries.
- OpenAI usage may create API costs.
- The workflow currently starts manually.

## Possible Future Improvements

- Add automatic scheduling
- Connect external lead-enrichment APIs
- Add email-verification services
- Add CRM integration
- Add configurable qualification rules
- Add industry-specific scoring
- Add error notifications
- Add human-review routing
- Add reporting dashboards
- Add automated outreach for qualified leads

## Author

**Joshua Asegunloluwa Akanni**

AI Automation Specialist | n8n Workflow Developer | AI Agent Builder

Portfolio: [blanyx.com](https://blanyx.com)

GitHub: [@joshuaakanni](https://github.com/joshuaakanni)

## License

No open-source license has been added. All rights are currently reserved by the author.
