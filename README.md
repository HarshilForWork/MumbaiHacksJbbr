# 🚀 Project Aegis - Complete Misinformation Detection Pipeline

**An advanced end-to-end system for trend scanning, claim verification, and misinformation detection powered by Google Gemini AI and orchestrated agents.**

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://python.org)
[![Google AI](https://img.shields.io/badge/Google-Gemini%202.5%20Flash-brightgreen.svg)](https://ai.google.dev)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📋 Table of Contents

- [🎯 Overview](#-overview)
- [🏗️ System Architecture](#️-system-architecture)
- [✨ Key Features](#-key-features)
- [🚀 Quick Start](#-quick-start)
- [⚙️ Configuration](#️-configuration)
- [📖 Usage](#-usage)
- [🔧 Pipeline Components](#-pipeline-components)
- [📊 Output Format](#-output-format)
- [🤝 Contributing](#-contributing)
- [📄 License](#-license)

## 🎯 Overview

Project Aegis is a comprehensive misinformation detection pipeline that combines multi-platform trend scanning (**Reddit**, **Threads**, **Twitter (X)**, & **Telegram**), AI-powered content analysis, and automated fact-checking to provide real-time detection and verification of potentially harmful content.

### 🎪 Mumbai Hacks Project

- This project was developed for **Mumbai Hacks**, featuring a complete automated pipeline that:
- **Scans Social Media** (Reddit, Threads, Twitter (X), and Telegram) for trending posts.
- **Generates AI summaries** and extracts claims using Google Gemini 2.5.
- **Fact-checks Claims** against reliable sources with automated verification.
- **Verifies Media** (Images/Videos) for deepfakes and manipulation.
- **Provides structured output** ready for content moderation systems.

### 🔍 Problem Statement

With the rapid spread of misinformation on social media, there's a critical need for automated systems that can:
- **Detect trending content** before it goes viral using velocity tracking.
- **Extract and verify claims** automatically using AI.
- **Analyze Media** (Images/Videos) for deepfakes and manipulation using Computer Vision.
- **Provide comprehensive fact-checking** with reliable sources.
- **Scale efficiently** across multiple platforms with minimal human intervention.

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────────────────────────────┐
│                              PROJECT AEGIS ARCHITECTURE                              │
│                           ORCHESTRATOR-CENTRIC PIPELINE                              │
└─────────────────────────────────────────────────────────────────────────────────────┘

                            ┌─────────────────────────┐
                            │    ORCHESTRATOR AGENT   │
                            │   🎼 Central Command    │
                            │                         │
                            │ • Workflow Coordinator  │
                            │ • Agent Manager         │
                            │ • Result Aggregator     │
                            └─────────────────────────┘
                                        │
                                        │ coordinates
                                        ▼
                ┌───────────────────────────────────────────────────────────┐
                │                   AGENT WORKFLOW                          │
                └───────────────────────────────────────────────────────────┘
                                        │
            ┌───────────────────────────┼───────────────────────────┐
            │                           │                           │
            ▼                           ▼                           ▼
    
┌──────────────────┐            ┌──────────────────┐            ┌─────────────────────┐
│  TREND SCANNER   │            │ CLAIM VERIFIER   │            │  EXPLANATION AGENT  │
│      AGENT       │            │     AGENT        │            │                     │
│                  │            │                  │            │                     │
│ • Reddit Monitor │───────────>│ • Google Search  │───────────>│ • Debunk Generator  │
│ • Threads Scraper│   step 1   │ • Media Verifier │   step 2   │ • Content Creator   │
│ • Twitter Monitor│            │ • Source Analysis│            │ • Educational Posts │
│ • Telegram Scan  │            │ • Batch Verify   │            │ • Batch Processing  │
│ • Web Scraper    │            │                  │            │                     │
│ • AI Summarizer  │            │                  │            │                     │
└──────────────────┘            └──────────────────┘            └─────────────────────┘
         │                               │                               │
         │ data flow                     │ data flow                     │ data flow
         ▼                               ▼                               ▼
    
┌─────────────────────────────────────────────────────────────────────────────────────┐
│                              DATA FLOW SEQUENCE                                     │
│                                                                                     │
│  Step 1: Orchestrator → Trend Scanner (Reddit/Threads/Twitter/Telegram) → Trending posts             │
│  Step 2: Orchestrator → Claim Verifier (Text + Media) → Verified verdicts           │
│  Step 3: Orchestrator → Explanation Agent → Debunk posts → Final Output             │
└─────────────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────────────┐
│                                AI FOUNDATION LAYER                                  │
│                                                                                     │
│  🤖 Google Gemini 2.5 Flash  │ 🔍 Google Custom Search  │ 📸 Media Verification    │
│  • Content Summarization     │  • Fact-checking Sources  │  • Deepfake Detection    │
│  • Claim Extraction          │  • Credibility Assessment │  • Frame Analysis        │
│  • Risk Assessment           │  • Evidence Gathering     │  • Reverse Image Search  │
└─────────────────────────────────────────────────────────────────────────────────────┘
```

## ✨ Key Features

### 🤖 **AI-Powered Complete Pipeline**
- **Google Gemini 2.5 Flash** - Latest AI model for content analysis and summarization
- **Automated Claim Extraction** - AI identifies verifiable claims from posts
- **Comprehensive Fact-Checking** - Google Custom Search + AI analysis
- **Batch Processing** - Efficient processing with minimal API calls

### 📸 **Advanced Media Verification**
- **Deepfake Detection** - Identifies AI-generated images and videos using Gemini Vision
- **Frame-by-Frame Video Analysis** - Extracts and verifies individual video frames
- **Reverse Image Search** - Validates image origins and context via SerpAPI
- **YouTube Verification** - Metadata validation + visual analysis for YouTube links

-### 📊 **Real-Time Detection & Verification**
- **Multi-Platform Scanning** - Continuous monitoring of **Reddit**, **Threads**, **Twitter (X)**, and **Telegram**
- **Velocity Tracking** - Detection of rapidly trending posts
- **Risk Assessment** - Priority scoring for high-risk content

## 🛠️ Complete Technology Stack

### 🤖 **AI & Machine Learning**
- **Google Gemini 2.5 Flash** - multimodal AI for text and vision analysis
- **LiteLLM** - Multi-provider LLM integration

### 🌐 **Web Scraping & Content Extraction**
- **Playwright** - Headless browser automation for dynamic scraping (Threads and other dynamic sites)
- **Beautiful Soup 4** - HTML/XML parsing
- **Newspaper3K & Trafilatura** - Article extraction
- **PRAW** - Reddit API Wrapper
- **Parsel, Nested-Lookup, JMESPath** - JSON data extraction for dynamic sites

### 🎥 **Media Processing**
- **OpenCV (cv2)** - Video frame extraction and processing
- **Pillow (PIL)** - Image manipulation
- **Gemini Vision** - Visual analysis and deepfake detection

### 🔍 **Data Sources & APIs**
- **Google Custom Search API** - Fact-checking and source verification
- **SerpAPI** - Reverse image search
- **YouTube Data API** - Video metadata verification

## 🚀 Quick Start

### 📋 Prerequisites
- **Python 3.8+**
- **Google AI API Key**
- **Reddit API Credentials**
- **SerpAPI Key** (for media verification)

### ⚡ Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd MumbaiHacks
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   playwright install chromium
   ```

3. **Configure environment variables**
   ```bash
   cp .env.example .env
   # Edit .env with your API keys
   ```

### 🏃‍♂️ Quick Run

**Complete Pipeline**
```bash
python run_pipeline.py --mode full
```

**Individual Components**
```bash
python orchestrator_agent.py           # Full orchestrator
python trend_scanner_agent.py          # Trend scanning only
python video_verifier.py               # Standalone video verification
```

## 🔌 Internal Google Agents helpers


This repository provides an internal helper/orchestration layer implemented in the `trend_scanner.google_agents` module and used across the codebase.

Where the implementation lives:
- Module implementation: `trend_scanner/google_agents.py`
- Used by: `orchestrator_agent.py`, `trend_scanner/` tools, `claim_verifier/`, `explanation_agent/`, and other modules.
- Key classes exported/used across the repo: `GoogleAgentsManager`, `GoogleAIManager`, `GoogleOrchestrator`, and `GoogleAgentsOrchestrator`.

What it is:
- An internal, lightweight set of orchestration helpers that wrap `google.generativeai` calls, normalize requests/responses, and provide agent/workflow abstractions used by the orchestrator and tools.

How other code uses it (examples from the repo):
```python
from trend_scanner.google_agents import GoogleAgentsManager

gm = GoogleAgentsManager(api_key=os.getenv('GOOGLE_API_KEY'))
agent = gm.create_agent('trend_scanner', role='TrendScanner', goal='Identify trending posts')
result = agent.execute_task('Scan r/worldnews for trending posts')
```

Notes:
- This helper layer is internal and experimental; it is not an official Google SDK.
- If desired, we can extract these helpers into a top-level package (for example, `aegis_agents/`) and add dedicated docs/examples under `docs/SDK.md`.

## 🔗 Integration: Twitter

This repo includes full Twitter/X support: scanning tools, cookie management, and login helpers.

Key files:
- `login_twitter.py` — browser-based login helper to create cookie exports.
- `twitter_cookie_monitor.py` — cookie health checks and refresh monitoring.
- `convert_cookies.py` — conversion utilities between `cookies.txt` and the repo's JSON cookie format.
- `trend_scanner/tools/twitter_scan_tool.py` — the scanning tool used by the trend scanner.

Dependencies & auth options:
- Primary dependency: `twikit` (or scraping via Playwright). Ensure `twikit` is installed from `requirements.txt`.
- You can authenticate by:
  - Running `python login_twitter.py` to save cookies, or
  - Exporting browser cookies (`cookies.txt`) and converting them with `python convert_cookies.py`.

Environment variables (examples used across code):
- `TWITTER_USERNAME`, `TWITTER_PASSWORD` (for automated login flows)
- `TWITTER_COOKIES_FILE` (path to JSON cookies used by scanners)
- `TWITTER_ENABLED=true` to enable Twitter scanning in agents

Quick commands:
```bash
python login_twitter.py
python trend_scanner_agent.py        # run the trend scanner (ensure TWITTER_ENABLED=true)
```

Notes:
- The README previously referenced Playwright; Twitter scanning supports cookie-based scraping and Playwright-based flows depending on config. Add Playwright only if you need browser automation fallback.

## 🔗 Integration: Telegram

This repo includes Telegram channel scanning via Telethon.

Key files:
- `trend_scanner/tools/telegram_scan_tool.py` — Telegram scan tool used by the trend scanner.

Dependencies & auth:
- Dependency: `telethon` (listed in `requirements.txt`).
- Required env vars for initial setup:
  - `TELEGRAM_API_ID`
  - `TELEGRAM_API_HASH`
  - Optional: `TELEGRAM_PHONE`, `TELEGRAM_SESSION_NAME`

First-time auth:
- Telethon requires an interactive auth (phone + code) the first time. Run the scanner locally and follow the prompt to save the session file.

Quick command:
```bash
# set TELEGRAM_API_ID and TELEGRAM_API_HASH, then:
python trend_scanner_agent.py        # ensure TELEGRAM_ENABLED=true
```

## ⚙️ Other Important Setup Notes

- MongoDB: The repo has Mongo integration utilities. Set `MONGODB_URI` to enable database persistence (the code references a Mongo helper/`AegisMongoDB`).
- Google/Gemini keys: Components using Google generative APIs reference `GEMINI_API_KEY` or `GOOGLE_API_KEY`. Provide these keys as env vars for summarization/vision features.
- SerpAPI / Reverse Image Search: set `SERPAPI_KEY` if you want the reverse-image helpers to work.
- Scrapfly: If `scrapfly-sdk` is used (present in `requirements.txt`), set `SCRAPFLY_API_KEY` for certain scraping flows.
- Playwright: After `pip install -r requirements.txt`, run:
```bash
playwright install chromium
```
  Some dynamic scraping (Threads/Playwright flows) require this.
- Cookie conversion: Use `convert_cookies.py` to transform browser `cookies.txt` exports into the JSON format used by the scanners.

## 🧪 Tests

Run unit tests with:
```bash
pytest -q
```
Note: Some tests expect certain env vars or mocks; refer to test files for details.

---

If you'd like, I can:
- extract the small helpers into a `aegis_agents/` package for clearer imports,
- or add `docs/INTEGRATIONS.md` with step-by-step auth examples and screenshots.

## 🔧 Pipeline Components

### 1. **🎼 Orchestrator Agent** (`orchestrator_agent.py`)
Central coordination managing the entire lifecycle from scanning to explanation, using the Google Agents SDK pattern.

### 2. **🔍 Trend Scanner Agent** (`trend_scanner/`)
- **monitor_reddit.py**: Live post monitoring across subreddits.
- **threads_scraper.py**: Dynamic scraping of Threads.net using Playwright to extract trending discussions.
- **twitter_monitor.py**: Twitter/X monitoring and scraping utilities (cookie-based or API-backed flows).
- **telegram_scraper.py**: Telegram channel monitoring utilities (Telethon-based).
- **AI Analysis**: Gemini-powered summarization and risk scoring.

### 3. **✅ Claim Verifier Agent** (`claim_verifier/` & `video_verifier.py`)
- **Text Verification**: Cross-references claims with trusted sources via Google Search.
- **Media Verification**:
    - **Image Verifier**: Detects manipulation and finds original context.
    - **Video Verifier**: Hybrid analysis using YouTube API metadata and frame-by-frame visual inspection to detect deepfakes or out-of-context clips.

### 4. **📝 Explanation Agent** (`explanation_agent/`)
Generates clear, fact-based debunk posts and educational content tailored for social media.

## 📊 Output Format

The system produces a comprehensive JSON report:

```json
{
  "timestamp": "2024-01-15T10:30:00",
  "posts": [
    {
      "claim": "Deepfake video of public figure",
      "platform": "threads",
      "verification": {
        "verified": false,
        "verdict": "false",
        "media_analysis": {
            "type": "video",
            "findings": "Visual artifacts consistent with AI generation detected in 4/10 frames."
        },
        "details": {
          "confidence": "high",
          "sources_found": 3
        }
      }
    }
  ]
}
```

## 📈 Risk Levels

| Level | Description | Action Required |
|-------|-------------|-----------------|
| **HIGH** | Likely misinformation, viral deepfakes, conspiracy theories | Immediate Investigation |
| **MEDIUM** | Unverified claims, lacks sources | Monitor Closely |
| **LOW** | Factual content, satire, opinion | Routine Logging |

## 🤝 Contributing

Contributions are welcome! Please run tests before submitting PRs:
```bash
python -m pytest tests/
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

**🚀 Project Aegis - Defending Truth in the Digital Age**
*Built with ❤️ for Mumbai Hacks | Powered by Google Gemini 2.5 Flash*
