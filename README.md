# Slack AI Assistant – LangChain + OpenAI

A Slack bot that answers messages and @mentions with an OpenAI model through LangChain. It runs over **Slack Socket Mode**, so no public server or webhook URL is needed.

## Features

- Replies to direct messages and `@bot` mentions in channels
- LangChain prompt template plus OpenAI chat model for responses
- Socket Mode connection (`slack_bolt`), so it runs on a laptop or a private server
- Secrets loaded from `.env`, never hard-coded

## Setup

1. Create a Slack app at [api.slack.com/apps](https://api.slack.com/apps):
   - Turn on **Socket Mode** and create an **App-Level Token** (`xapp-…`)
   - Add bot scopes: `app_mentions:read`, `chat:write`, `im:history`
   - Subscribe to the `message.im` and `app_mention` events, then install the app to get the **Bot Token** (`xoxb-…`)
2. Run:

```bash
git clone https://github.com/Fahad-Ali-Data-Scientist/slack-ai-assistant-langchain.git
cd slack-ai-assistant-langchain
pip install -r requirements.txt
cp .env.example .env     # add SLACK_BOT_TOKEN, SLACK_APP_TOKEN, OPENAI_API_KEY
python complete.py
```

## Tech stack

Python · Slack Bolt (Socket Mode) · LangChain · OpenAI API · python-dotenv
