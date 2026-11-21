# AI-Powered Student Query Response Automation
### n8n Workflow Automation with Google Forms, Google Sheets, Airtable, Ollama and Gmail

**Project status:** In progress — workflow design and local n8n setup started  
**Project type:** Workflow automation / AI-assisted student support  
**Author:** Mohammad Hummad Siddiqui

> **Project status note:** This repository documents the planned workflow while the project is being developed. Not all integrations or automation steps are implemented or tested yet. Sections marked as planned will be updated as each stage is completed.

## Project Overview

This project aims to automate the process of receiving student queries, preparing relevant information, generating a personalised draft response with a locally running large language model, and sending the response to the student's email address.

The workflow is being developed in **n8n** and is planned to connect Google Forms, Google Sheets, Airtable, Ollama (Llama 3.1 8B) and Gmail.

The goal is to reduce repetitive manual work in handling student questions while keeping a record of submitted queries and generated responses.

## Problem Statement

Student queries received through forms or other channels can require repetitive manual work:
- Collecting and organising submitted questions.
- Reviewing student information and query details.
- Preparing individual responses.
- Sending responses to the correct email address.
- Tracking which queries have been processed.

This project explores how workflow automation and a locally hosted AI model can assist with these tasks.

## Project Objectives

- Capture student queries submitted through Google Forms.
- Store form responses in Google Sheets.
- Transfer or maintain query records in Airtable for tracking.
- Format relevant student and query information as structured JSON.
- Use Ollama with Llama 3.1 8B to generate a response draft.
- Send the generated response to the student's submitted email address through Gmail.
- Maintain a record of query processing and response status.

## Planned Workflow

```text
Student submits Google Form
            |
            v
Google Forms response
            |
            v
Google Sheets
            |
            v
Airtable - query record and tracking
            |
            v
Format student details and query as JSON
            |
            v
Ollama - Llama 3.1 (8B)
Generate a response draft
            |
            v
Gmail
Send response to student's email
            |
            v
Update query status / response record
```

**Important:** This diagram represents the intended workflow, not a claim that every connection is already working. The final workflow may change during implementation.

## Tools and Technologies

| Tool | Planned purpose |
|---|---|
| n8n | Connect services and orchestrate the automation |
| Google Forms | Collect student queries |
| Google Sheets | Store form responses |
| Airtable | Organise and track query records |
| Ollama | Run the language model locally |
| Llama 3.1 (8B) | Generate response drafts |
| Gmail | Deliver responses by email |
| JSON | Structure information passed between workflow steps |
| Node.js | Local runtime used for the n8n setup |

## Current Development Status

| Component | Status |
|---|---|
| n8n local installation and launch | Set up |
| Google Forms integration | Planned / to be implemented |
| Google Sheets integration | Planned / to be implemented |
| Airtable integration | Planned / to be implemented |
| JSON formatting step | Planned / to be implemented |
| Ollama and Llama 3.1 (8B) integration | Planned / to be tested |
| Gmail response delivery | Planned / to be implemented |
| End-to-end workflow testing | Pending |

The local environment previously used for setup:
- Operating system: Windows
- Node.js: v24.20.0
- n8n: v2.36.7
- Local n8n address: `http://localhost:5678`

These are setup details from the development environment and may change as the project progresses.

## Planned Workflow Details

### 1. Query collection
A student submits a Google Form containing their contact details and question. The form response is stored in Google Sheets.

### 2. Query organisation
The workflow is intended to transfer or synchronise the relevant information with Airtable so queries and their processing status can be tracked.

### 3. JSON preparation
The student's relevant details and query text are to be formatted into a structured JSON object before being passed to the AI step.

### 4. AI response generation
Ollama is planned to run the Llama 3.1 (8B) model locally and generate a response draft based on the submitted query and supplied context.

### 5. Email delivery
Gmail is planned to send the generated response to the email address submitted by the student. The workflow will need checks to ensure the recipient and generated content are correct before sending.

### 6. Status tracking
The workflow is intended to record whether a query has been received, processed, and responded to.

## Safety, Privacy and Reliability

Because the workflow handles student information and sends email:
- Do not publish real student names, email addresses, phone numbers, or query content in this repository.
- Use dummy data when sharing screenshots or example workflow executions.
- Never upload API keys, OAuth credentials, access tokens, passwords, or exported credentials.
- Keep secrets in n8n credentials or environment variables, not directly in workflow code.
- Add a review or approval step before automatically emailing AI-generated responses, at least during testing.
- Validate the recipient email address and handle model/API failures before sending.
- Avoid sending sensitive personal information to an AI service unless there is a clear, approved reason and appropriate safeguards.

## Planned Repository Structure

The repository will be expanded as implementation progresses. A possible structure is:

```text
ai-student-query-automation/
├── README.md
├── workflow/
│   └── student-query-automation.json
├── docs/
│   ├── workflow-architecture.md
│   └── setup-notes.md
├── screenshots/
│   └── workflow-overview.png
├── sample-data/
│   └── sample-student-queries.csv
└── .gitignore
```

Only add workflow exports, screenshots and sample files after removing credentials and replacing real student information with dummy data.

## Roadmap

- [ ] Create the Google Form and connect its response sheet.
- [ ] Configure the Google Sheets trigger or retrieval step in n8n.
- [ ] Connect Airtable and define the query-tracking fields.
- [ ] Build and test the JSON formatting step.
- [ ] Install/configure Ollama and verify Llama 3.1 (8B) locally.
- [ ] Connect the AI response-generation step.
- [ ] Configure Gmail and test delivery using a test inbox.
- [ ] Add validation, error handling and an approval step.
- [ ] Test the complete workflow using dummy student records.
- [ ] Add screenshots and a sanitised n8n workflow export.
- [ ] Update this README to distinguish completed, tested and pending features.

## How to Run

The workflow is still under development, so there is not yet a complete, verified end-to-end run procedure.

For now, the local n8n editor was accessed at:

```text
http://localhost:5678
```

Once the workflow is complete, this section will include exact installation, configuration and execution instructions. Do not import an unreviewed workflow export or provide credentials through public files.

## Learning Outcomes

Through this project, I aim to gain practical experience with:
- Designing multi-step workflows in n8n.
- Connecting forms, spreadsheets, databases and email services.
- Passing structured JSON data between workflow nodes.
- Running and integrating a local large language model.
- Building AI-assisted response workflows.
- Handling errors, credentials, privacy and human review in automation systems.

## Author

**Mohammad Hummad Siddiqui**

- GitHub: [hummad01](https://github.com/hummad01)
- LinkedIn: [Mohammad Hummad Siddiqui](https://www.linkedin.com/in/mohammad-hummad-siddiqui-656b73306/)

---

*This README will be updated as the project moves from workflow design to implementation and end-to-end testing.*
