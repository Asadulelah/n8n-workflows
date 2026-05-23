# Viral Script Analyser — Decode Why Content Goes Viral

## You Watch Viral Videos. This Bot Tells You Why They Work.

Every creator has done it. You see a Reel blow up with 10 million views and you think — *what did they do differently?* You watch it a few times, maybe take some notes, try to reverse-engineer the hook. But you're guessing.

What if you could send any viral video to a bot and get back a full psychological breakdown — the hook technique, the retention strategy, the emotional triggers, the CTA structure — in under a minute?

That's what the Viral Script Analyser does.

---

## What Is It?

A Telegram bot powered by AI that takes any video URL (Instagram Reel, TikTok, YouTube Short), downloads it, transcribes the audio, and delivers a detailed breakdown of the viral psychology behind the content.

Send a link. Get back a masterclass on why it works.

Every analysis is also saved to Airtable, so over time you build a personal library of viral content patterns you can reference whenever you're creating.

---

## How It Works (Step by Step)

### Step 1: Send a Video Link
Open your Telegram bot and paste a video URL. Instagram Reel, TikTok, YouTube Short — it handles all of them.

### Step 2: Video Download
The system downloads the video through an external API. It handles the different URL formats across platforms automatically.

### Step 3: Audio Transcription
The video's audio is sent to Groq's Whisper large-v3 model for transcription. Groq runs Whisper on custom hardware, so transcription is fast — usually a few seconds even for longer videos.

### Step 4: AI Analysis
Here's where the magic happens. The full transcript is sent to an AI analysis agent that breaks it down across multiple dimensions:

- **Opening Hook** — What technique did they use in the first 1-3 seconds? Pattern interrupt? Bold claim? Question? Story loop?
- **Retention Mechanics** — How do they keep people watching? Open loops? Pacing changes? Visual transitions?
- **Emotional Triggers** — What psychological buttons are being pressed? Fear of missing out? Curiosity gaps? Social proof?
- **Call-to-Action** — How do they drive action? Is it explicit or implied? Where is it placed?
- **Content Structure** — What's the overall framework? Hook-story-offer? Problem-agitate-solve? List format?

The analysis isn't surface-level. It connects specific moments in the script to psychological principles that explain *why* they work.

### Step 5: Save & Reply
The full analysis is saved to Airtable (video URL, username, analysis text), then formatted into a clean, readable message and sent back to you in Telegram.

---

## What You Actually Get Back

Here's the kind of insight you get for every video:

**Hook Analysis:** "Opens with a pattern interrupt — a shocking statistic delivered in a whisper tone, creating contrast that stops the scroll. The first 2 seconds use a visual zoom that triggers the orienting response."

**Retention Breakdown:** "Uses a classic open loop at 0:08 ('but here's what nobody tells you...') that creates a curiosity gap. The pacing shifts every 3-4 seconds with alternating close-up and wide shots, preventing habituation."

**Emotional Mapping:** "Primary emotion: aspiration with underlying FOMO. The creator positions themselves as 'someone who figured it out' while implying the viewer is behind. The social proof ('I've helped 500+ people do this') activates herd behavior."

This isn't ChatGPT summarizing a video. This is a structured psychological analysis you can actually learn from.

---

## Building Your Viral Content Library

Every analysis gets stored in Airtable automatically. After analyzing 50 or 100 videos, you'll have a searchable database of viral patterns organized by:

- Video URL and platform
- Creator username
- Full analysis text
- Date analyzed

Search it when you're creating content. Look for patterns across your top-performing analyses. Build your own playbook based on real data, not guesses.

---

## What You Need To Set Up

- **Telegram Bot** — Create one via @BotFather (takes 2 minutes)
- **Groq API Key** — For Whisper audio transcription
- **Google Vertex AI** — For the analysis agent
- **Airtable** — Base with a table for storing analyses

Setup is straightforward. Every node in the workflow has a description explaining what it does, and the sticky notes walk you through the entire flow.

---

## Who This Is For

**Content creators** who want to study what works instead of guessing. Analyze your competitors' best-performing content and understand exactly why it resonated.

**Social media managers** who need to brief clients or teams on content strategy. Send a few viral videos through the bot and you've got a data-backed content strategy document.

**Video editors** who want to improve retention. The analysis focuses heavily on pacing, transitions, and structural elements that keep viewers watching.

**Anyone** who consumes viral content and wants to understand the psychology behind it — whether you're creating content yourself or just want to be more media-literate.

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
| Telegram Bot | User interface for sending videos and receiving analyses |
| Groq Whisper | Fast, accurate audio transcription |
| Google Vertex AI | AI agent for viral psychology analysis |
| Airtable | Storage for building your viral content library |
