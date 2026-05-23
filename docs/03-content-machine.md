# Content Machine — From YouTube Research to Published X/Twitter Post

## One Topic In, Finished Social Posts Out

Creating content consistently is exhausting. You need to find topics, research them, write something compelling, create visuals, review the draft, and finally publish. For a single post. Now multiply that by 5 posts a week across multiple platforms.

Content Machine compresses that entire pipeline into one automated workflow. Give it a topic, and it handles the research, writing, image generation, approval, and publishing — with you staying in control of what goes live.

---

## What Is Content Machine?

A multi-agent AI pipeline that turns YouTube research into published X/Twitter posts. It searches YouTube for videos on your topic, curates the best ones, transcribes them, mines key insights, writes engaging posts, generates custom images, sends drafts for your approval via Slack, and publishes to X/Twitter.

Six AI agents. One workflow. You just approve and post.

---

## How It Works (Step by Step)

### Step 1: Input Your Topic
Type a topic into the chat interface. "AI automation trends," "cold email strategies," "ecommerce growth hacks" — whatever you want to create content about.

### Step 2: YouTube Search
The system searches YouTube for videos on your topic and pulls back a list of results with metadata.

### Step 3: AI Curation
Not every YouTube video is worth pulling insights from. The AI Curator agent evaluates each video for relevance, quality, and content value — scoring them and filtering out the noise. Only videos that pass the quality threshold move forward.

### Step 4: Transcription
Videos that made it through curation get transcribed. The audio is converted to text so the AI agents can work with the actual content, not just titles and descriptions.

### Step 5: Topic Mining
The Topic Miner agent reads through all the transcriptions and identifies the most interesting, shareable angles for X/Twitter posts. It's not summarizing — it's finding the specific insights, hot takes, and data points that would perform well as social content.

### Step 6: Research Enrichment
A Research Agent takes those angles and enriches them with real-time web data via Tavily search. If the topic references a statistic, it finds the source. If there's a trend, it gets the latest numbers. This makes your posts credible, not just engaging.

### Step 7: Post Composition
The Post Composer agent takes the mined topics + research and writes platform-optimized X/Twitter posts. These aren't generic — they're written with hooks, structure, and CTAs that work specifically on X.

### Step 8: Image Generation
For posts that benefit from visuals, the Image Prompt Generator creates a custom DALL-E prompt, and OpenAI generates an image tailored to the post content.

### Step 9: Human Approval (Slack)
The draft — post text + image + source document — is sent to your Slack channel for review. You read it, and approve or reject. **Nothing publishes without your say-so.**

A Google Doc is also created with the full content for your records.

### Step 10: Publish
Once approved, the post (with image if applicable) is published directly to X/Twitter.

---

## The 6-Agent Architecture

This isn't one AI doing everything. It's six specialized agents, each handling one part of the pipeline:

| Agent | Model | Role |
|-------|-------|------|
| **Curator** | Google Gemini | Evaluates YouTube videos for quality and relevance |
| **Topic Miner** | Google Gemini | Identifies shareable angles from transcriptions |
| **Research Agent** | Google Gemini | Enriches topics with real-time web data |
| **Post Composer** | Google Gemini | Writes platform-optimized X/Twitter posts |
| **Image Prompt Generator** | OpenAI | Creates DALL-E prompts for custom visuals |
| **Review Router** | Code-based | Routes posts through the approval and media pipeline |

Each agent passes structured output to the next. The result is dramatically better than asking one model to "write me a tweet about AI."

---

## Why Human-in-the-Loop Matters

Content Machine doesn't post behind your back. Every draft goes through Slack approval because:

- You maintain your voice and brand
- You catch anything that doesn't feel right
- You can add personal touches before publishing
- You stay aware of what's going on your profile

Automation without oversight is a liability. Automation with approval is a superpower.

---

## What You Need To Set Up

- **Google Gemini** — Powers 4 of the 6 AI agents
- **OpenAI** — For DALL-E image generation
- **Tavily** — For real-time web research
- **Google Docs** — For content review documents
- **Slack** — For human-in-the-loop approval
- **X/Twitter API** — For publishing posts

---

## Who This Is For

**Content creators** who want to post consistently without spending hours per post. Set up the pipeline once, and you can produce quality content every day.

**Social media managers** handling multiple accounts. Run the pipeline for different topics and approve a week's worth of content in one sitting.

**Thought leaders** who want to stay active on X/Twitter but don't have time to write. Your YouTube research becomes social content automatically.

**Marketing teams** that need a repeatable, scalable content process with built-in quality control.

---

## What's Included

- Complete n8n workflow (48 nodes, ready to import)
- Every node annotated with a description of what it does
- Step-by-step sticky notes walking through the entire flow
- Installation guide with credential setup instructions

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| n8n | Workflow automation platform |
| Google Gemini | AI agents (curation, mining, research, composition) |
| OpenAI | Image generation (DALL-E) and image prompt agent |
| Tavily | Real-time web research |
| Google Docs | Content review documents |
| Slack | Human-in-the-loop approval |
| X/Twitter API | Publishing |
