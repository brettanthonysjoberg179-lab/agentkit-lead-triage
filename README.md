# AgentKit Lead Triage

Production-ready autonomous AI agent for inbound lead triage and automated Gmail draft replies powered by Python and Composio.

## Features
- **Gmail Inbox Polling:** Fetches unread inbound messages via Composio Gmail tools (`GMAIL_FETCH_EMAILS`).
- **Intent Classification:** Classifies incoming emails into categories (Hot Sales / Pricing, Technical Support, Affiliate / Partnership, General Inquiry).
- **Automated Draft Replies:** Generates tailored responses linking to checkout/documentation and creates a draft in Gmail (`GMAIL_CREATE_EMAIL_DRAFT`).
- **Dry-Run & Live Modes:** Safely test logic without sending/modifying live mail, or switch to live mode for production execution.

## Setup & Configuration

1. Copy `.env.example` to `.env` and configure your settings:
   ```bash
   cp .env.example .env
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Authenticate Composio:
   ```bash
   composio login
   ```

## Usage

Run in dry-run mode (default, uses simulated or fetched unread leads):
```bash
python agentkit_lead_triage.py --dry-run
```

Run in live mode (processes actual unread emails and creates drafts):
```bash
python agentkit_lead_triage.py --live --max 5
```
