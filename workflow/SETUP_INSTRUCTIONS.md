# Workflow Setup Instructions

## Importing the Workflows

1. In n8n, go to Workflows → Add workflow → Import from file
2. Import `chemical_monitor.workflow.TEMPLATE.json`
3. Import `error_handler.workflow.TEMPLATE.json`

## Credentials to Configure

Before running, set up these credentials in n8n Settings → Credentials:

### 1. Telegram API
- Type: Telegram API
- Value: Your bot token from @BotFather

### 2. Gemini API Key
- Type: Header Auth
- Header Name: x-goog-api-key
- Value: Your Gemini API key from aistudio.google.com

## Environment Variables

Add these to your .env file (copy from .env.example):

- TELEGRAM_CHAT_ID — get from @userinfobot in Telegram
- N8N_ENCRYPTION_KEY — generate a random 32-character string
- GEMINI_API_KEY — from aistudio.google.com (free tier)

## After Importing

1. Open the Chemical Process Monitor workflow
2. Update the Telegram node Chat ID field with your chat ID
3. Update the Format Error Message node, replace YOUR_TELEGRAM_CHAT_ID
4. Link the Error Handler in main workflow Settings → Error Workflow
5. Publish both workflows