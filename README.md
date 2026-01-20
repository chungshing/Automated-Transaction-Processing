# Automated Transaction Processing Workflow Template for n8n

This n8n workflow automates the extraction, processing, and recording of transaction data from email notifications into dynamic Google Sheets tabs grouped by month.

---

## Features

- Dynamically determines sheet names by transaction date (e.g., "July 2025").
- Fetches transaction emails after the latest processed date.
- Extracts and sanitizes transaction details (amount, merchant, date, time).
- Groups transactions by month and writes them to the respective Google Sheet tabs.
- Automatically creates new sheets if they don’t exist.
- Opens the Google Sheet in the default browser upon completion.

---

## Setup Instructions

1. Import the `automated-transaction-processing.json` file into your n8n instance.
2. Configure the following credentials:
   - Google Sheets OAuth2 (set as **Google Sheets account**)
   - Gmail OAuth2 (set as **Gmail account**)
3. Replace placeholder Sheet IDs (`""` or `"SHEET_ID_HERE"`) with your actual Google Sheet ID in the workflow nodes.
4. Adjust the email sender filter in the Gmail node to match your transaction notification sender.
5. Run the workflow manually or schedule as needed.

---

## Node Overview

- **Manual Trigger**: Starts the workflow manually.
- **Code Nodes**: Handle date formatting, data extraction, grouping, and sanitization.
- **Google Sheets Nodes**: Read, create, and update sheets dynamically.
- **Gmail Node**: Retrieves transaction emails.
- **Execute Command**: Opens the Google Sheet URL after processing.

---

## Security Notice
- All credentials, sheet IDs, email senders, and example values in this repository are **placeholders**.
- No real accounts, personal data, or transaction information are included.

---

## Notes

- Currency is set to USD; modify the code node if needed.
- Timezone information is neutralized for portability.
- Ensure your Gmail and Google Sheets OAuth credentials have proper permissions.
