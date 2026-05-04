# FinAI - Liminal AI Sales Finder Agent

<p align="center">
  <img src="https://www.becomeliminal.com/assets/logo-orange-7Sg2BzUP.webp" alt="Liminal Logo" width="150"/>
  <br/>
  <em>Built for Liminal</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Go"/>
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React"/>
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript"/>
  <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite"/>
  <img src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=anthropic&logoColor=white" alt="Claude"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/🏆_Most_Innovative_Hack-HackSouthWest-orange?style=flat-square" alt="Most Innovative Hack"/>
  <img src="https://img.shields.io/badge/🏆_Best_Documentation_%26_Outreach-Superteam_UK_AI_Agents-blue?style=flat-square" alt="Best Documentation"/>
  <img src="https://img.shields.io/badge/Built_in-24_hours-red?style=flat-square" alt="Built in 24 hours"/>
</p>

<p align="center">
  An AI-powered financial agent that analyses a user's transaction history, finds cheaper alternatives to their recent purchases, and delivers recommendations directly within Liminal's chat interface - helping users spend smarter without sacrificing quality.
</p>

---

## Demo

<p align="center">
  <a href="https://github.com/JakeFordy/FinAI/releases/download/v1.0/finAI.demo.mp4">▶️ Watch Full Demo</a>
</p>

<p align="center">
  <img src="https://github.com/JakeFordy/FinAI/releases/download/v1.0/finAI_demoPic1.png" alt="FinAI Screenshot 1" width="49%"/>
  <img src="https://github.com/JakeFordy/FinAI/releases/download/v1.0/finAI_demoPic2.png" alt="FinAI Screenshot 2" width="49%"/>
</p>

---

## What It Does

FinAI is a financial assistant that sits alongside a user's Liminal account and helps them spend smarter. It displays spending patterns through graphs and tables, runs continuous AI analysis in the background, and surfaces insights directly in the interface - without the user having to ask.

**Spending Overview** - Visualises transaction history in organised graphs and tables so users can understand their spending patterns at a glance.

**Budget Planner** - Users can set a monthly budget target and see in real time whether they're on track, saving, or overspending.

> ![Budget Planner GIF](BUDGET_PLANNER_GIF_URL)

**AI Insights** - A background analysis loop continuously scans recent purchases and finds cheaper, good-quality alternatives. Findings are surfaced on a live notice board alongside alerts about suspicious transactions and price increases on frequent purchases.

<p align="center">
  <img src="AI_INSIGHTS_SCREENSHOT_1_URL" alt="AI Insights - Alternative Found" width="32%"/>
  <img src="AI_INSIGHTS_SCREENSHOT_2_URL" alt="AI Insights - Suspicious Activity" width="32%"/>
  <img src="AI_INSIGHTS_SCREENSHOT_3_URL" alt="AI Insights - Price Increase" width="32%"/>
</p>

**Subscription Tracker** - Surfaces all recurring payments in one place so users can easily spot and cancel services they no longer need.

> ![Recurring Payments GIF](RECURRING_PAYMENTS_GIF_URL)

**Graph Analysis** - Visual breakdown of spending patterns across categories, merchants, and time periods.

> ![Graph Analysis GIF](GRAPH_ANALYSIS_GIF_URL)

**AI Chatbot** - Users can chat directly with Nim, the AI agent, to ask questions about their spending, get financial advice, or dig into specific transactions.

> ![AI Chatbot GIF](AI_CHATBOT_GIF_URL)

Built to align with Liminal's values of user consent, privacy, and transparency - the agent only analyses authorised transaction data and provides clear, explainable recommendations.

---

## Tech Stack

- **Backend** - Go, built on the `nim-go-sdk` WebSocket server
- **AI** - Claude (Anthropic) via `anthropic-sdk-go`
- **Frontend** - React + TypeScript (Vite), using the `nim-chat` widget
- **Banking Integration** - Liminal financial APIs (balance, transactions, payments)

---

## Project Structure

```
FinAI/
├── main.go                   # Entry point, server setup, background loops
├── analysis.go               # AI background analysis loop + large transaction monitor
├── handlers.go               # HTTP endpoints (alerts, transactions, recurring payments)
├── prompts.go                # Claude system prompt and AI personality
├── recurringPayments.go      # AI-powered recurring payment detection
├── transactions.go           # Transaction parsing and filtering utilities
├── tools.go                  # Custom Claude tools (spending analyser, product search, alerts)
├── types.go                  # Shared type definitions
├── config.go                 # App config and constants
├── mock_transactions.txt     # Sample transaction data for demo
├── go.mod
├── go.sum
├── .env.example
├── frontend/
│   ├── index.html
│   ├── main.tsx              # App component + WebSocket client
│   ├── styles.css
│   ├── vite.config.ts
│   ├── package.json
│   ├── tsconfig.json
│   └── src/
│       ├── components/
│       │   ├── BudgetPlanner.tsx
│       │   ├── GraphAnalysis.tsx
│       │   ├── RecentTransactions.tsx
│       │   └── RecurringPayments.tsx
│       ├── hooks/
│       │   └── useWebSocket.ts
│       ├── utils/
│       │   └── formatters.tsx
│       ├── constants.ts
│       └── types.ts
└── sdk/                      # nim-go-sdk local dependency
    ├── core/                 # Tool, ToolExecutor interfaces
    ├── engine/               # Conversation engine, session, guardrails
    ├── executor/             # HTTP + gRPC executors for Liminal API
    ├── server/               # WebSocket server + protocol
    ├── store/                # Conversation storage
    ├── subagent/             # Sub-agent delegation
    └── tools/                # Tool builder DSL + Liminal tool definitions
```

---

## Key Features

- **Background analysis loop** - Automatically checks recent purchases every 5 seconds and posts savings opportunities to the notice board
- **Large transaction alerts** - Flags any outgoing transaction over $1,000 in real time
- **Recurring payment detection** - Uses AI to identify subscriptions and repeating charges, surfacing all recurring payments in one place
- **Savings calculator** - Shows at a glance whether a user is heading into the red based on their spending patterns
- **Fraud warning system** - Postmortem analysis of purchases to flag suspicious or unusual transactions
- **Conversational agent** - Users can ask Nim (the AI) directly about their purchases, spending patterns, or alternatives for specific products
- **Modular tool system** - Custom Claude tools for reading transactions, searching alternatives, and posting/reading alerts

---

## Getting Started

### Prerequisites

- Go 1.21+
- Node.js 18+
- An Anthropic API key

### Setup

```bash
cp .env.example .env
# Add your ANTHROPIC_API_KEY to .env
```

### Run the backend

```bash
go run .
```

### Run the frontend

```bash
cd frontend
npm install
npm run dev
```

The WebSocket server runs at `ws://localhost:8080/ws` and the alerts API at `http://localhost:8080/api/alerts`.

---

## Challenges & Limitations

Built under time pressure, so a few rough edges remain:

- Competitor suggestions are based on AI inference rather than live pricing data
- Limited to mock transaction data - real Liminal transaction integration was partially blocked by API connectivity issues during the hackathon
- Product matching accuracy could be improved with richer datasets and broader retailer coverage

---

## What's Next

- Expanded blockchain integration with support for multiple cryptocurrencies
- Improved competitor search using live pricing data rather than AI inference
- Long-term spending pattern analysis for smarter recommendations
- Enhanced fraud detection with more granular transaction signals

---

## About

> *fin[ance] AI - the final AI for finance*

FinAI was built as a team project during the Hackathons UK x HackSouthWest 2026 x Liminal Hackathon. This repo is a cleaned-up showcase fork of the original submission - the codebase has been restructured for readability but the core logic is unchanged from what was demoed on the day.

The project is a proof of concept exploring how AI-driven financial analysis can be integrated into blockchain-based banking systems to help users spend more efficiently.

### Special Thanks

A massive thank you to my amazing team for making this happen in 24 hours:
- Sholto Coulter
- Millie Clark
- Theo Swan
- Tamara Spalding

And to the organisers and sponsors who put on a brilliant event:

<p align="center">
  <a href="https://www.linkedin.com/company/superteamuk/"><img src="https://img.shields.io/badge/Superteam_UK-9945FF?style=for-the-badge" alt="Superteam UK"/></a>
  <a href="https://www.linkedin.com/company/hack-south-west/"><img src="https://img.shields.io/badge/Hack_South_West-E85D26?style=for-the-badge" alt="Hack South West"/></a>
  <a href="https://www.hackathons.org.uk/"><img src="https://img.shields.io/badge/Hackathons_UK-1A1A2E?style=for-the-badge" alt="Hackathons UK"/></a>
  <a href="https://excs.uk/"><img src="https://img.shields.io/badge/ExCS-003865?style=for-the-badge" alt="ExCS"/></a>
  <a href="https://www.becomeliminal.com/"><img src="https://img.shields.io/badge/Liminal-FF6B35?style=for-the-badge" alt="Liminal"/></a>
</p>

> Showcase fork - original submission: [src238/Untitled-AI](https://github.com/src238/Untitled-AI)
