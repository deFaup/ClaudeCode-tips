# Claude code with Xiaomi mimo models

This explains how to setup Claude Code to use either your mimo API key or your mimo subscription (token plan)

## Pre-requisite
Choose your option

### How to get a subscription (token plan)
https://platform.xiaomimimo.com/token-plan
After successful subscription, go to [Subscription](https://platform.xiaomimimo.com/#/console/plan-manage) to obtain the exclusive Base URL and API Key

### How to get an API Key
- Go to `https://platform.xiaomimimo.com/docs/en-US/welcome`
- Click on Apply for API Key
- Make an account or log in if you have one
- once authenticated you should be on the [/console/api-keys](https://platform.xiaomimimo.com/console/api-keys) page where you can create up to 50 api keys
- after creating your first key you get a free 0.72$ credit

## Point ClaudeCode to MIMO api endpoints

Update/Create `~/.claude/settings.json` with the necessary environment variables:

### For the subscription
```json
{
  "env": {
    "ANTHROPIC_BASE_URL": "http://localhost:4141",
    "ANTHROPIC_AUTH_TOKEN": "tp-xxxxx",
  }
}
```

### For the API
replace the token with your api key
```json
{
  "env": {
    "ANTHROPIC_BASE_URL": "https://api.xiaomimimo.com/anthropic",
    "ANTHROPIC_AUTH_TOKEN": "sk-xxxxx",
  }
}
```

### Add remaining variables for models and cost optimization
    "ANTHROPIC_MODEL": "mimo-v2.5-pro",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "mimo-v2.5",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "mimo-v2.5-pro",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "mimo-v2.5-flash",
    "DISABLE_NON_ESSENTIAL_MODEL_CALLS": "1",
    "CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC": "1"

## Models and pricing
https://platform.xiaomimimo.com/docs/en-US/pricing
mimo-v2.5-pro
mimo-v2.5
mimo-v2.5-tts
mimo-v2.5-tts-voiceclone
mimo-v2.5-tts-voicedesign

## Useful links:
- official benchmark page for models 2.5: https://mimo.xiaomi.com/mimo-v2-5-pro/
- official setup instructions: https://platform.xiaomimimo.com/docs/en-US/integration/claudecode
- free ai studio: https://aistudio.xiaomimimo.com/#/
- https://venturebeat.com/ai/open-source-xiaomi-mimo-v2-5-and-v2-5-pro-are-among-the-most-efficient-and-affordable-at-agentic-claw-tasks