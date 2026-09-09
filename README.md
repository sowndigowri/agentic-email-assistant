# Agentic Email Assistant

An intelligent email automation system that monitors important Gmail messages, analyzes them using Gemini, generates draft replies, sends WhatsApp notifications, and sends replies only after receiving user approval.

## Overview

The Agentic Email Assistant helps users manage important emails without continuously checking their inbox.

The system:

1. Monitors unread Gmail messages.
2. Identifies emails from important senders or domains.
3. Uses Gemini to summarize the email and prepare a draft reply.
4. Stores the email and draft in MySQL.
5. Sends a WhatsApp notification through Twilio.
6. Waits for the user's approval.
7. Sends the Gmail reply only after approval.

## Features

- Automatic Gmail monitoring
- Important sender and domain filtering
- AI-generated email summaries
- Email urgency classification
- AI-generated professional draft replies
- WhatsApp notifications using Twilio
- WhatsApp approval, rejection, and editing commands
- Gmail replies sent only after approval
- MySQL email and approval history
- Flask monitoring dashboard
- Scheduled inbox monitoring
- LangGraph-based workflow orchestration

## Approval Commands

The user can control replies through WhatsApp:

```text
APPROVE 12
REJECT 12
EDIT 12 Your updated reply message
```

## Technology Stack

- Python
- Flask
- LangGraph
- LangChain
- Google Gemini API
- Gmail API
- Google OAuth 2.0
- Twilio WhatsApp API
- MySQL
- APScheduler
- ngrok
- HTML, CSS and JavaScript

## Project Architecture

```text
Gmail Inbox
    |
    v
Important Email Filter
    |
    v
LangGraph Workflow
    |
    v
Gemini Analysis
    |
    v
MySQL Database
    |
    v
Twilio WhatsApp Notification
    |
    v
User Approval
    |
    v
Gmail Reply
```

## Project Structure

```text
agentic-email-assistant/
├── agents/
├── routes/
├── services/
├── workflows/
├── templates/
├── static/
│   ├── css/
│   └── js/
├── sql/
├── app.py
├── config.py
├── run_monitor.py
├── start_tunnel.py
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

## Environment Variables

Create a `.env` file using `.env.example` as a reference.

Required configuration includes:

- Gemini API key
- Gmail OAuth credentials
- Twilio credentials
- MySQL connection details
- Important senders and domains
- Email monitoring interval

> Never commit `.env`, OAuth tokens, API keys, passwords, or credentials to GitHub.

## Application Workflow

1. APScheduler checks Gmail periodically.
2. The importance agent filters messages.
3. Gemini summarizes important emails and creates draft replies.
4. The results are stored in MySQL.
5. Twilio sends a WhatsApp notification.
6. The user approves, rejects, or edits the draft.
7. Approved replies are sent through the Gmail API.
8. The dashboard displays email and approval statistics.

## Current Status

The project currently supports:

- Gmail authentication and email retrieval
- Important email filtering
- Gemini email analysis
- MySQL storage
- WhatsApp notifications
- WhatsApp approval processing
- Approved Gmail replies
- Automatic inbox monitoring
- Flask dashboard

## Security

Sensitive files are excluded using `.gitignore`, including:

```text
.env
secrets/
credentials.json
token.json
venv/
```

Twilio webhook signature validation is recommended before production deployment.

## Limitations

- Twilio trial accounts have restrictions on recipients and message templates.
- ngrok URLs may change when the tunnel is restarted.
- The Flask development server is intended only for local development.
- Google OAuth testing configuration may restrict application users.

## Future Enhancements

- Production deployment
- Improved dashboard controls
- Multiple Gmail account support
- Advanced email priority classification
- Custom WhatsApp template support
- Retry and failure-handling mechanisms
- Docker support
- Automated testing
- CI/CD workflow

## Author

**Sowndaryagowri N**

B.Tech Artificial Intelligence and Data Science

## License

This project is licensed under the MIT License.
