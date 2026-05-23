# 1. Email Writer Air

## The Problem
You spend hours researching prospects, crafting personalized emails, and still get terrible reply rates. Manual cold outreach doesn't scale, and generic templates get ignored.

## The Solution
Email Writer Air is a fully automated cold email pipeline that researches your prospects, understands their business, and writes hyper-personalized email sequences — all without you lifting a finger.

## How It Works
1. **Pull prospects** from your Airtable CRM
2. **Scrape their LinkedIn** profile automatically via Apify — job title, company, experience, skills
3. **AI Research Agent** searches the web for recent company news, funding rounds, product launches, and relevant context
4. **Prospect Analyst** identifies pain points, opportunities, and the best angle for outreach
5. **Email Writer (Claude 3.7 Sonnet)** crafts a complete email sequence — main email + follow-ups — uniquely tailored to each prospect
6. **Everything saved** back to Airtable, ready to send

## What Makes This Different
- Uses **3 separate AI agents**, each specialized for a different task (research, analysis, writing)
- Emails are based on **real data** — LinkedIn profiles and live web research — not generic templates
- Claude 3.7 Sonnet writes emails that actually sound human
- Fully automated loop — process 10 prospects or 1,000 with the same workflow

## Who This Is For
- Agency owners doing outbound lead generation
- Sales teams that need personalized outreach at scale
- Freelancers and consultants looking to book more calls
- Anyone tired of writing cold emails manually

## Tech Stack
n8n, Airtable, Apify, Tavily, Google Gemini, Claude 3.7 Sonnet (OpenRouter)

---

# 2. Viral Script Analyser

## The Problem
You watch viral Reels, TikToks, and Shorts and wonder — *why did this blow up?* You try to reverse-engineer what works, but you're guessing. You don't have a systematic way to break down viral content psychology.

## The Solution
A Telegram bot that takes any video URL, transcribes it, and delivers a full AI-powered breakdown of the viral psychology behind it — hooks, retention patterns, emotional triggers, CTAs, and content structure.

## How It Works
1. **Send a video link** to your Telegram bot (Instagram Reel, TikTok, YouTube Short)
2. The system **downloads the video** and **transcribes the audio** using Groq's Whisper model
3. An **AI analysis agent** breaks down the transcript for viral patterns
4. You get a **detailed report** sent right back to you in Telegram
5. Every analysis is **saved to Airtable** so you build a library of viral patterns over time

## What You Get In Every Analysis
- Opening hook breakdown — what grabs attention in the first 3 seconds
- Retention techniques — how they keep viewers watching
- Emotional triggers — what psychological buttons they're pressing
- Call-to-action effectiveness — how they drive action
- Content structure patterns — the framework behind the virality

## Who This Is For
- Content creators who want to study what works
- Social media managers analyzing competitor content
- Video editors looking to improve retention
- Anyone who wants to decode viral content systematically

## Tech Stack
n8n, Telegram Bot, Groq Whisper, Google Vertex AI, Airtable

---

# 3. Content Machine

## The Problem
Creating consistent, high-quality social media content takes forever. You need to research topics, write posts, create images, get approval, and publish — and that's just for ONE post.

## The Solution
Content Machine automates the entire pipeline from YouTube research to published X/Twitter post. Give it a topic, and it searches YouTube, transcribes relevant videos, mines key insights, writes engaging posts, generates images, gets your approval via Slack, and publishes.

## How It Works
1. **Input a topic** via chat
2. The system **searches YouTube** for relevant videos on that topic
3. An **AI Curator** evaluates each video for quality and relevance
4. Relevant videos are **transcribed** and the content is extracted
5. A **Topic Miner** identifies the best angles for X/Twitter posts
6. A **Research Agent** enriches those angles with real-time web data
7. The **Post Composer** writes engaging, platform-optimized posts
8. An **Image Generator** creates custom visuals using DALL-E
9. The draft goes to **Slack for your approval** — you stay in control
10. Once approved, it **publishes directly to X/Twitter**

## What Makes This Different
- **6 specialized AI agents** working together in a pipeline
- **Human-in-the-loop** — nothing posts without your approval
- Goes from raw YouTube content to finished social post automatically
- AI-generated images tailored to each post
- Builds a Google Doc review trail for every piece of content

## Who This Is For
- Content creators who want to post consistently without burnout
- Social media managers handling multiple accounts
- Thought leaders who want to repurpose video content into posts
- Marketing teams that need a scalable content pipeline

## Tech Stack
n8n, Google Gemini, OpenAI (DALL-E), Tavily, Google Docs, Slack, X/Twitter API

---

# 4. Lead Capturer & Decision Maker

## The Problem
Leads come in from Facebook ads, and then... nothing happens fast enough. By the time someone follows up, the lead has gone cold. You need instant, intelligent response — but you can't be available 24/7.

## The Solution
An automated lead capture and routing system that instantly processes Meta/Facebook Lead Ads, stores them in your CRM, and routes each lead through an intelligent decision tree — AI voice calls for hot leads, WhatsApp messages for everyone else.

## How It Works
1. **Lead comes in** from a Meta/Facebook Lead Ad
2. Data is **normalized and stored** in Airtable CRM instantly
3. The system checks **call consent** from the lead form
4. **If they opted in for a call:** An AI voice agent (VAPI) calls them immediately, monitors the call status, and routes based on outcome
5. **If they didn't opt in:** A WhatsApp template message is sent automatically
6. **Missed calls** get a WhatsApp follow-up
7. **Accepted calls** trigger the nurturing workflow for continued engagement

## What Makes This Different
- **Sub-second response time** — leads are contacted the moment they submit the form
- **Intelligent routing** — not every lead gets the same treatment
- **AI voice calling** — VAPI handles the first conversation so you don't have to
- **Automatic fallback** — missed calls don't fall through the cracks
- Connects directly to the WhatsApp Nurturing workflow for ongoing engagement

## Who This Is For
- Businesses running Meta/Facebook Lead Ads
- Sales teams that need instant lead follow-up
- Agencies managing lead gen campaigns for clients
- Anyone who loses leads because follow-up takes too long

## Tech Stack
n8n, Meta Lead Ads, Airtable, VAPI (AI Voice), WhatsApp Business API

---

# 5. WhatsApp Nurturing Multi Agent

## The Problem
You capture leads, but nurturing them through WhatsApp is a full-time job. You can't personally message every lead, track every conversation, score engagement, and route hot leads to sales — all at the same time.

## The Solution
A fully automated WhatsApp nurturing system powered by 5 AI agents. It handles incoming messages, generates contextual replies, detects when conversations end, scores leads based on engagement, and routes them to the right follow-up path.

## How It Works
1. **Lead sends a WhatsApp message** — the webhook captures it instantly
2. The system **looks up their CRM record** in Airtable for context
3. The **WhatsApp LLM Handler** generates a contextual, personalized reply using conversation history
4. The reply is **sent back via WhatsApp** with natural pacing
5. A **Conversation End Detector** monitors for natural conversation endings
6. When the conversation ends, the **Nurturing Agent** analyzes the full conversation
7. The lead gets a **score based on engagement quality**:
   - **Hot (80+)** — CRM flagged as priority, sales team notified
   - **Warm (50-79)** — Follow-up plan generated, record updated
   - **Cold (below 50)** — Marked for later re-engagement

## What Makes This Different
- **5 specialized AI agents** — each handles a specific part of the nurturing process
- **Full conversation memory** — powered by PostgreSQL, so the AI remembers every interaction
- **Automatic lead scoring** — no manual qualification needed
- **Smart routing** — hot leads get instant attention, warm leads get nurtured, cold leads get saved for later
- Works 24/7 without human intervention

## Who This Is For
- Businesses that use WhatsApp for lead communication
- Sales teams that need automated lead qualification
- Agencies managing high-volume lead nurturing
- Anyone who wants AI-powered conversations that actually convert

## Tech Stack
n8n, WhatsApp Business API, Airtable, Google Gemini, PostgreSQL, Supabase, Slack

---

# 6. FB Ads Lead Gen

## The Problem
Finding businesses that are actively spending money on ads — and are therefore likely to need your services — is time-consuming. You manually browse the Facebook Ad Library, check their profiles, visit their websites, and try to write something compelling. It takes hours per lead.

## The Solution
An automated pipeline that scrapes the Facebook Ad Library for businesses running ads in your target niche, verifies their Instagram presence and website quality, analyzes their site performance, and writes personalized outreach copy — all saved to a Google Sheet ready for outreach.

## How It Works
**Part 1 — Lead Discovery:**
1. **Searches the Facebook Ad Library** for ads in your target niche (last 30 days)
2. **Deduplicates** advertisers so you don't process the same business twice
3. **Saves everything** to Google Sheets — ad ID, page name, Instagram profile, website

**Part 2 — Lead Verification & Enrichment:**
1. **Reads unverified leads** from the sheet
2. **Checks Instagram** — minimum follower count and profile verification
3. **Validates website** — filters out Instagram-only links, empty URLs, and invalid pages
4. **Runs Google PageSpeed analysis** — gets real performance data on their website
5. **AI Copy Writer** analyzes the website data and writes personalized outreach messages (1 main message + 2 follow-ups)
6. **Saves everything** back to Google Sheets — verified, enriched, and ready for outreach

## What Makes This Different
- **Finds businesses that are already spending money** — these aren't cold leads, they're active advertisers
- **Automated verification** — only qualified leads make it through
- **Website performance data** gives you a concrete talking point for outreach
- **AI-written outreach copy** personalized to each lead's actual website
- Two-part workflow — run discovery and verification independently

## Who This Is For
- Agency owners looking for clients who already invest in ads
- Freelancers offering web design, SEO, or marketing services
- Sales teams targeting e-commerce businesses
- Anyone who wants a pipeline of pre-qualified, ad-spending leads

## Tech Stack
n8n, Facebook Ad Library API, Google Sheets, Google PageSpeed Insights, Google Gemini
