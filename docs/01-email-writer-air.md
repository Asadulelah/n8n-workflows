# Email Writer Air — AI-Powered Cold Email Pipeline

## Stop Writing Cold Emails Manually

You spend hours researching prospects, crafting personalized emails, and still get terrible reply rates. Manual cold outreach doesn't scale. Generic templates get ignored. And hiring a VA to do it means training, managing, and hoping they get the tone right.

What if you could hand off the entire process to a system that researches every prospect individually, understands their business better than most humans would, and writes emails that actually get replies?

That's exactly what Email Writer Air does.

---

## What Is Email Writer Air?

Email Writer Air is a fully automated cold email pipeline built on n8n. It pulls prospects from your CRM, scrapes their LinkedIn, researches their company, analyzes their pain points, and writes hyper-personalized email sequences — complete with follow-ups — without you touching a single thing.

It's not a template engine. It's not a mail merge tool. It's a system that actually *understands* each prospect before writing to them.

---

## How It Works (Step by Step)

### Step 1: Pull Prospects From Your CRM
The workflow connects to your Airtable base and pulls prospect records that need emails written. You control the batch size — process 5 leads or 500 in one run.

### Step 2: LinkedIn Scraping
For each prospect, an Apify scraper pulls their full LinkedIn profile — job title, company name, bio, work experience, skills, and more. This is the raw data that makes personalization possible.

### Step 3: AI Web Research
A dedicated AI Research Agent takes each prospect and searches the web using Tavily. It finds recent company news, funding rounds, product launches, blog posts, press mentions — anything that gives context about what's happening in their world right now.

The LinkedIn data and web research are merged together and saved back to your CRM, so even if you never send an email, you've got enriched prospect data.

### Step 4: Prospect Analysis
A second AI agent — the Prospect Analyst — takes all the research and creates a detailed analysis: pain points, opportunities, competitive landscape, and the best angle for outreach. This is the strategic layer that makes the emails actually relevant.

### Step 5: Email Writing
This is where it gets interesting. Claude 3.7 Sonnet (via OpenRouter) takes the full prospect analysis and writes a complete email sequence:

- **Main email** — personalized opener, value proposition tied to their specific situation, clear CTA
- **Follow-up 1** — different angle, builds on the first email
- **Follow-up 2** — final touch, creates urgency without being pushy

Every email is unique to the prospect. Not "Hi {first_name}, I noticed your company {company_name}..." — actually unique.

### Step 6: Save & Review
The generated emails are parsed, structured, and saved back to Airtable alongside the prospect record. You can review, tweak if needed, and send.

---

## The AI Architecture

What makes this workflow different from a simple "GPT writes emails" setup is the multi-agent architecture:

| Agent | Model | Role |
|-------|-------|------|
| **Research Agent** | Google Gemini | Searches the web, gathers prospect context |
| **Prospect Analyst** | Google Gemini | Analyzes data, identifies angles and pain points |
| **Email Writer** | Claude 3.7 Sonnet | Writes personalized email sequences |

Each agent is specialized. The Research Agent doesn't try to write emails. The Email Writer doesn't do research. They pass structured data between each other, and the result is significantly better than any single-prompt approach.

---

## What You Need To Set Up

- **Airtable** — Your prospect database (needs LinkedIn URL, Name, Company columns at minimum)
- **Apify** — For LinkedIn profile scraping (they have a generous free tier)
- **Tavily** — For web research (API key required)
- **Google Gemini** — Powers the Research and Analysis agents
- **OpenRouter** — For Claude 3.7 Sonnet (the email writing model)

All credentials are configured inside n8n. The workflow includes detailed setup notes on every node, plus a full walkthrough via sticky notes.

---

## Who This Is For

**Agency owners** doing outbound for themselves or clients — this replaces hours of manual research and writing per prospect.

**Sales teams** that need personalized outreach at scale — your SDRs can focus on conversations instead of email drafting.

**Freelancers and consultants** who need to book more calls but don't have time to write 50 personalized emails a week.

**Anyone** who's tried generic cold email templates and wondered why nobody replies.

---

## What's Included

- Complete n8n workflow (ready to import)
- Every node annotated with a description of what it does
- Step-by-step sticky notes walking through the entire flow
- Installation guide with credential setup instructions

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| n8n | Workflow automation platform |
| Airtable | Prospect CRM and data storage |
| Apify | LinkedIn profile scraping |
| Tavily | AI-powered web research |
| Google Gemini | Research and analysis AI agents |
| Claude 3.7 Sonnet (OpenRouter) | Email writing AI |
