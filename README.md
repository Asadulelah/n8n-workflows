# n8n Workflows

> A curated, open-source library of production-grade n8n automation workflows. Built and battle-tested in real client work. Drop the JSON files into your own n8n instance, wire up the credentials, and ship.

---

## What's inside

| # | Workflow | What it does | Stack |
|---|---|---|---|
| 1 | **Email Writer Air** | LinkedIn scraping + AI cold email pipeline. Pulls prospects from a CRM, scrapes LinkedIn, runs web research, writes hyper-personalized email sequences. | Airtable · Apify · Tavily · OpenRouter (Claude 3.7 Sonnet) |
| 2 | **Viral Script Analyser** | A Telegram bot that analyzes viral video psychology. Send it a video link or audio; it transcribes, breaks down the hooks/structure/emotional beats, and saves the analysis. | Telegram · Groq · Google Vertex AI · Airtable |
| 3 | **Content Machine** | YouTube research → X/Twitter publishing pipeline. Watches a niche, researches trending takes, drafts content, runs through human-in-the-loop approval, publishes. | YouTube · OpenAI (DALL-E) · Tavily · Google Docs · Slack · X API |

Each workflow has a full walkthrough in [`docs/`](./docs).

## Quick start

1. **Clone this repo.**
2. **Open your n8n instance** (self-hosted or cloud).
3. **Import a workflow** — Settings → Import from File → pick a JSON from [`workflows/`](./workflows).
4. **Configure credentials** in n8n's Credentials panel. See [INSTALLATION_GUIDE.md](./INSTALLATION_GUIDE.md) for the full credential matrix per workflow.
5. **Open the workflow** and read the sticky notes — each node has setup details inline.
6. **Test before activating.** Use n8n's "Execute Workflow" button with sample data; verify outputs; only then toggle to active.

## What's NOT in this drop (yet)

A few workflows are sitting in [`_pending-review/`](./_pending-review) while I finish a careful PII / secret-scrubbing pass on them:

- **Lead Capturer & Decision Maker** — Meta Lead Ads → AI voice (VAPI) + WhatsApp template routing.
- **WhatsApp Nurturing Multi Agent** — Automated WhatsApp lead nurturing with lead-scoring.
- **FB Ads Lead Gen** — Facebook Ad Library scraping + lead verification.

These will land in a follow-up release once the JSON exports are stripped of any real-world bearer tokens, sample lead data, and account-specific IDs. If you're impatient, the architecture docs for each are linked in the [resource hub](./RESOURCE_HUB_DESCRIPTIONS.md).

## Conventions

- **Every node has an inline note.** Hover the icon to read it. Setup details live with the node, not in a separate doc.
- **Every workflow has a top-left sticky note** walking through the entire flow step by step. Start there.
- **All workflows are exported as inactive.** Activate them only after testing with realistic data — there are Wait nodes specifically there for rate-limit reasons; don't remove them.
- **Never edit production workflows directly.** Always import as a copy.

## Architecture map

```
                    ┌──────────────────────┐
                    │   Meta Lead Ads      │
                    └──────────┬───────────┘
                               │
                ┌──────────────▼───────────┐
                │ Lead Capturer & Decision │  (pending)
                └──────┬───────────────────┘
                       │
              ┌────────▼───┐  ┌──────────────────┐
              │ WhatsApp   │  │ AI Voice Call    │
              │ Template   │  │ (VAPI)           │
              └────────────┘  └──────────────────┘

  ┌──────────────────┐  ┌─────────────────┐  ┌───────────────────┐
  │  Email Writer Air│  │ Content Machine │  │ Viral Script      │
  │  (this drop)     │  │ (this drop)     │  │ Analyser          │
  └──────────────────┘  └─────────────────┘  │ (this drop)       │
                                              └───────────────────┘
```

## License

[MIT](LICENSE). Use them, fork them, build on them. Attribution welcome, not required.

## Built by

[**Asadulelah**](https://github.com/Asadulelah) — frameworks for AI-native operations. More repos + the full portfolio at [asad-portfolio-lake.vercel.app](https://asad-portfolio-lake.vercel.app).
