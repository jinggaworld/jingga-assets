DataScout is an autonomous AI agent that transforms how researchers, data scientists, and other AI agents discover and evaluate open datasets. Instead of manually browsing dozens of data portals, users simply describe what they need in natural language — and DataScout searches, scores, and delivers the best-matching datasets from 10+ sources in seconds.

Built on the CROO Agent Protocol, DataScout is a paid, callable agent that any AI system can hire to find data. It democratizes access to open data by combining parallel multi-source search, AI-powered query understanding, automated quality scoring, and license detection into a single, composable service.

## Project Details

### What is DataScout?

DataScout is a full-stack dataset discovery platform powered by AI. It accepts natural language queries (e.g., "find housing price datasets in Indonesia for the last 5 years"), parses them into structured search parameters using Gemini Flash on OpenRouter, then searches 10+ open data sources in parallel.

### Core Features

| Feature | Description |
|---|---|
| **Multi-Source Search** | Parallel search across HuggingFace, Kaggle, OpenML, Zenodo, data.gov, World Bank, FRED, NOAA, OpenAQ, arXiv |
| **AI Query Understanding** | Natural language → structured parameters via Gemini 2.5 Flash Lite (1M context, $0.10/1M tokens) |
| **Smart Deduplication** | Union-Find + fuzzy matching merges duplicates across sources |
| **Readiness Scoring** | 5-component weighted score (completeness, freshness, size, docs, license) — auto-graded A through F |
| **License Detection** | Regex-based classification for 13 license types (CC0, CC-BY, MIT, Apache, ODbL, etc.) |
| **Reproducible Reports** | Ranked datasets, comparison table, APA citations, download manifest, hash proof |
| **CROO Integration** | Live on CROO Agent Store — buyers hire DataScout, pay in USDC, receive results automatically |
| **Download Proxy** | Backend fetches source data, serves as proper CSV/JSON download with preview table |

### Tech Stack

- **Backend:** Python 3.11+, FastAPI, Pydantic v2, asyncio, httpx
- **AI Engine:** OpenRouter (Gemini 2.5 Flash Lite primary, Gemini 2.5 Flash fallback)
- **Frontend:** React 18, TypeScript, Vite, Tailwind CSS, Tanstack Query
- **Protocol:** CROO Agent Protocol (CAP) — negotiation, lock, deliver, clear
- **Data Sources:** 10+ open APIs (HuggingFace, Kaggle, OpenML, Zenodo, data.gov, World Bank, FRED, NOAA, OpenAQ, arXiv)
- **Testing:** 204+ automated tests, full TypeScript type checking

### How It Works

1. **User submits query** — Natural language or structured JSON
2. **AI parses query** — Gemini extracts topic, keywords, region, time range, filters
3. **Parallel search** — 10+ adapters search simultaneously
4. **Deduplicate & rank** — Union-Find merges duplicates, weighted scoring ranks results
5. **Score & detect license** — Readiness score (A–F) + license classification per dataset
6. **Generate report** — Markdown report with citations, comparison table, download manifest
7. **Deliver via CAP** — Results sent to buyer through CROO protocol with hash proof

### CROO Agent Store

DataScout is live on the CROO Agent Store as a callable agent:
- **Service:** Dataset Search & Discovery
- **Price:** 0.01 USDC per search
- **SLA:** 30 minutes
- **Deliverable:** Markdown report + JSON structured data

Buyers can hire DataScout from the CROO Agent Store, provide a search query, and receive ranked dataset results automatically — no manual browsing required.

### Impact

- **For researchers:** Find relevant datasets in seconds instead of hours
- **For AI agents:** Hire a data-finding sub-agent programmatically
- **For developers:** Legal dataset discovery with license verification
- **For the ecosystem:** Composable A2A service that other agents can chain

### Links

- **GitHub:** https://github.com/jinggaworld/datascout
- **Demo Video:** https://youtu.be/vFz-YvFlrpY
- **CROO Agent Store:** https://agentstore.croo.network
- **Live Frontend:** http://localhost:3000 (self-hosted)

### Team

Built by jinggaworld for the CROO Agent Hackathon.
