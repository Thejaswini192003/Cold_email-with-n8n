# Cold_email-with-n8n
This n8n workflow automates sending personalized job application emails directly from form submissions.

# Tools used:
1) self host n8n
2) Gemini Api
3) Email and
4) Google sheet

# Cold Emailing Automation Workflow - n8n

This repository contains an **n8n workflow** that automates sending personalized job application emails directly from form submissions. It also stores submitted data in Google Sheets and integrates with Google Gemini (PaLM) for generating professional email content.

## Workflow Overview

- **Trigger:** Form submission capturing `email` and `company name`.
- **AI Model:** Google Gemini Chat Model to craft professional, humanized emails.
- **Email Formatting:** Uses a JSON-to-table structure for `To`, `Subject`, and `Body`.
- **Email Sending:** Automatically sends personalized emails via Gmail.
- **Data Storage:** Submissions are saved in a Google Sheet for record-keeping.
- **Enhancements:** Minor JSON transformations and code nodes to structure email fields.

## Nodes in the Workflow

1. **Form Trigger** – Captures email and company name from the user.
2. **Agent AI** – Generates the email content using Google Gemini (PaLM).
3. **JSON to Table** – Structures AI output into `To`, `Subject`, `Body`.
4. **Extract Email Fields** – Converts the table into Gmail-ready fields.
5. **Google Sheets Node** – Stores the email details.
6. **Gmail Node** – Sends the email automatically.
7. **Sticky Note** – Workflow description inside n8n for clarity.

## How to Use

1. Import `cold_emailing_workflow.json` into your n8n instance.
2. Connect your credentials for:
   - Google Gemini (PaLM) API
   - Gmail
   - Google Sheets
3. Activate the workflow.
4. Fill the form → AI generates email → Stores in Sheet → Sends email automatically.

## Notes

- Ensure proper API credentials are set up in n8n before activating.
- Email personalization is dynamic using `{{ $json['email'] }}` and `{{ $json['company name'] }}` placeholders.
- Resume link and signature are pre-filled in the email body.

## License

MIT License
