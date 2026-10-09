# Visa Consultant Bot — n8n Workflow Automation

An automated Telegram-based visa consultancy assistant built using **n8n, Telegram Bot API, and Google Sheets**. The bot streamlines applicant onboarding, collects visa consultation details, manages user sessions, and notifies visa consultants when applications are submitted.

## Overview

The Visa Consultant Bot provides an interactive interface for users to begin their visa consultation through Telegram. It guides applicants through a structured conversation, collects relevant information, and stores application records in Google Sheets for further review by visa consultants.

The workflow uses conditional routing and session management to maintain conversation progress and handle user responses efficiently.

## Features

- **Telegram Integration:** Interact with applicants through a Telegram bot.
- **Session Management:** Create and retrieve sessions to maintain user progress.
- **Language Selection:** Allow applicants to select their preferred language.
- **Visa Category Selection:** Support student, work/professional, and tourist visa consultation categories.
- **Destination Selection:** Collect the country for which the applicant seeks visa assistance.
- **Interactive Question Flow:** Guide applicants through the required information-collection steps.
- **Application Review:** Provide a review stage before submission.
- **Google Sheets Integration:** Store session data and application records.
- **Submission Confirmation:** Send a success message to the applicant.
- **Consultant Notifications:** Notify the visa consultant when a submission is completed.

## Workflow Architecture

The automation follows this sequence:

1. **Telegram Trigger** — Receives incoming messages and button interactions.
2. **Normalize Telegram Update** — Standardizes incoming Telegram data.
3. **Get Session** — Retrieves the user's current session.
4. **Session Exists?** — Checks whether the user has an existing session.
5. **Create Session** — Initializes a new session when required.
6. **Process Step** — Processes the user's response and determines the next step.
7. **Button Click Validation** — Handles callback queries from interactive buttons.
8. **Prepare Session Row** — Formats session information for storage.
9. **Update Session** — Updates the session record in Google Sheets.
10. **Route Next Question** — Directs the conversation to the appropriate step.
11. **Prepare Application Row** — Structures the application data.
12. **Save Application** — Stores the application record in Google Sheets.
13. **Send Success Message** — Confirms successful submission.
14. **Notify Visa Consultant** — Sends a notification to the consultant.

## Technology Stack

- **n8n** — Workflow automation and orchestration
- **Telegram Bot API** — User interaction and messaging
- **Google Sheets** — Session and application data storage
- **JavaScript** — Data processing and workflow logic, where applicable

## Prerequisites

Before setting up the workflow, ensure you have:

- An accessible n8n instance
- A Telegram bot created through [BotFather](https://t.me/BotFather)
- A Google account with access to Google Sheets
- Telegram and Google Sheets credentials configured in n8n

## Setup Instructions

1. Clone or download this repository.
2. Open your n8n instance.
3. Import the exported workflow JSON file into n8n.
4. Configure your Telegram bot credentials.
5. Configure Google Sheets credentials and select the required spreadsheet.
6. Verify the spreadsheet structure and column mappings used by the workflow.
7. Test session creation, language selection, visa category selection, country selection, and application submission.
8. Activate the workflow after successful testing.

**Note:** Credentials and spreadsheet references may need to be configured after importing the workflow. Do not store API tokens, passwords, or other secrets in this repository.

## Repository Structure

```text
Visa-Consultant-Bot/
├── README.md
├── workflows/
│   └── visa-consultancy-workflow.json
└── .gitignore
```

The workflow JSON should be placed in the `workflows/` directory if you use the structure shown above.

## Security and Privacy

- Keep Telegram bot tokens and API credentials private.
- Use n8n's credential management for authentication.
- Avoid committing personal applicant information.
- Restrict access to Google Sheets containing application records.
- Use a private GitHub repository when appropriate.

## Project Scope

This project automates initial visa consultation and applicant data collection. It does not independently determine visa eligibility, submit applications to government immigration systems, or guarantee visa approval.

## Future Improvements

- Add additional languages.
- Implement stronger input validation and error handling.
- Add automated follow-up reminders.
- Generate application summaries for consultants.
- Introduce applicant status tracking and reporting.

## License

No license has been specified yet. If you intend to make this project publicly reusable, choose an appropriate open-source license. For a private repository, you can leave this section out until you decide.

---

**Developed as a workflow automation project using n8n, Telegram, and Google Sheets.**
