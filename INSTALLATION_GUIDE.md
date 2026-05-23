# Installation Guide — n8n Automation Suite

## Quick Setup (4 Steps)

### Step 1: Access Your n8n Instance

Log in to your self-hosted n8n instance. All 6 workflows are already deployed in **inactive** state:

| # | Workflow | Purpose |
|---|----------|---------|
| 1 | **Email Writer Air** | LinkedIn scraping + AI cold email sequences |
| 2 | **Viral Script Analyser** | Telegram bot that analyzes viral video psychology |
| 3 | **Content Machine** | YouTube research to X/Twitter publishing pipeline |
| 4 | **Lead Capturer & Decision Maker** | Meta Lead Ads → AI voice calls + WhatsApp routing |
| 5 | **WhatsApp Nurturing Multi Agent** | Automated WhatsApp lead nurturing with scoring |
| 6 | **FB Ads Lead Gen** | Facebook Ad Library scraping + lead verification |

---

### Step 2: Configure API Credentials

Go to **Settings → Credentials** in n8n and add the following:

#### Required for ALL workflows:
| Credential | Type | Used By |
|------------|------|---------|
| Google Gemini | API Key | All AI agents across all workflows |
| Airtable | API Key / OAuth | CRM storage (Email Writer, Lead Capturer, WhatsApp Nurturing, Viral Script Analyser) |

#### Per-workflow credentials:

**Email Writer Air:**
- Apify (LinkedIn scraping)
- Tavily (web research)
- OpenRouter (Claude 3.7 Sonnet for email writing)

**Viral Script Analyser:**
- Telegram Bot Token (create via @BotFather)
- Groq API Key (add manually in the `Groq-transcribe` node's Authorization header)
- Google Vertex AI

**Content Machine:**
- OpenAI (DALL-E image generation)
- Tavily (web research)
- Google Docs (review documents)
- Slack (human-in-the-loop approval)
- X/Twitter API (publishing)

**Lead Capturer & Decision Maker:**
- Meta/Facebook (Lead Ads webhook)
- VAPI (AI voice calls)
- WhatsApp Business API

**WhatsApp Nurturing Multi Agent:**
- WhatsApp Business API
- PostgreSQL (conversation memory)
- Supabase (session memory)
- Slack (optional — sales notifications)

**FB Ads Lead Gen:**
- Google Sheets OAuth
- Google PageSpeed API (via HTTP Request)

---

### Step 3: Configure Workflow-Specific Settings

Some nodes require manual configuration beyond credentials:

#### Lead Capturer & Decision Maker
1. Open the **Make Call** node → Replace `[YOUR ASSISTANT ID]` and `[YOUR PHONE NUMBER ID]` with your VAPI credentials
2. Open **Send template** and **Send template1** nodes → Set your WhatsApp Sender Phone Number ID, Recipient Phone Number expression, and Template name

#### Viral Script Analyser
1. Open the **Groq-transcribe** node → Replace `<API Tokens>` in the Authorization header with your actual Groq API key

#### FB Ads Lead Gen
1. Open the **Fb ads links** node → Set your target niche/keyword URLs for the Facebook Ad Library
2. Ensure the Google Sheets document ID matches your spreadsheet

---

### Step 4: Activate & Test

For each workflow:

1. **Open the workflow** in the n8n editor
2. **Review the overview sticky note** (top-left area) for workflow-specific setup details
3. **Test first** — Use the "Execute Workflow" button or send a test message to the trigger
4. **Verify the output** — Check that data flows correctly through each node
5. **Activate** — Toggle the workflow to active once testing passes

#### Recommended activation order:
1. **Viral Script Analyser** — Simplest to test (just send a Telegram message)
2. **FB Ads Lead Gen** — Manual trigger, easy to verify
3. **Email Writer Air** — Manual trigger, check Airtable output
4. **Content Machine** — Chat trigger, verify Slack approval flow
5. **WhatsApp Nurturing Multi Agent** — Needs WhatsApp webhook configured
6. **Lead Capturer & Decision Maker** — Needs Meta Lead Ads + VAPI + WhatsApp all configured

---

## Workflow Architecture

```
                    ┌─────────────────────┐
                    │   Meta Lead Ads     │
                    └─────────┬───────────┘
                              │
                    ┌─────────▼───────────┐
                    │  Lead Capturer &    │
                    │  Decision Maker     │
                    └──┬──────────────┬───┘
                       │              │
              ┌────────▼──┐    ┌──────▼──────────┐
              │ WhatsApp  │    │  AI Voice Call   │
              │ Template  │    │  (VAPI)          │
              └───────────┘    └──────┬───────────┘
                                      │
                    ┌─────────────────▼───────────┐
                    │  WhatsApp Nurturing         │
                    │  Multi Agent                │
                    └─────────────────────────────┘

    ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
    │ Email Writer │  │Content       │  │ Viral Script │
    │ Air          │  │Machine       │  │ Analyser     │
    └──────────────┘  └──────────────┘  └──────────────┘

    ┌──────────────────────────────────────────────────┐
    │              FB Ads Lead Gen                      │
    └──────────────────────────────────────────────────┘
```

---

## Troubleshooting

- **Workflow won't activate:** Check that all required credentials are configured
- **AI agent returns empty:** Verify the LLM credential (Google Gemini / OpenAI / OpenRouter) is valid
- **WhatsApp messages not sending:** Ensure the WhatsApp Business API webhook URL matches your n8n instance URL
- **Airtable errors:** Verify base ID, table name, and column names match your Airtable setup
- **Rate limits:** The Wait nodes are there for a reason — don't remove them

## Notes

- Each node has a descriptive note explaining its function — hover over the note icon on any node to read it
- Each workflow has detailed sticky notes walking through the entire flow step by step
- All workflows are deployed as **inactive** — activate them only after testing
