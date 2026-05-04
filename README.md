# FinAI - Liminal AI Sales Finder Agent

<p align="center">
  <img src="https://www.becomeliminal.com/assets/logo-orange-7Sg2BzUP.webp" alt="Liminal Logo" width="200"/>
</p>

> 🏆 HackSouthWest - Most Innovative Hack | Superteam UK AI Agents in Blockchain Banking - Best Documentation & Outreach | Built in 24 hours

An AI-powered financial agent that analyses a user's transaction history, finds cheaper alternatives to their recent purchases, and delivers recommendations directly within Liminal's chat interface - helping users spend smarter without sacrificing quality.

## Demo
https://github.com/JakeFordy/FinAI/releases/download/v1.0/finAI.demo.mp4

<p align="center">
  <img src="https://github.com/JakeFordy/FinAI/releases/download/v1.0/finAI_demoPic1.png" alt="FinAI Screenshot 1" width="49%"/>
  <img src="https://github.com/JakeFordy/FinAI/releases/download/v1.0/finAI_demoPic2.png" alt="FinAI Screenshot 2" width="49%"/>
</p>

## What It Does

FinAI is a financial assistant that sits alongside a user's Liminal account and helps them spend smarter. It displays spending patterns through graphs and tables, runs continuous AI analysis in the background, and surfaces insights directly in the interface - without the user having to ask.

**Spending Overview** - Visualises transaction history in organised graphs and tables so users can understand their spending patterns at a glance.

**Budget Planner** - Users can set a monthly budget target and see in real time whether they're on track, saving, or overspending.

**AI Insights** - A background analysis loop continuously scans recent purchases and finds cheaper, good-quality alternatives. Findings are surfaced on a live notice board alongside alerts about suspicious transactions and price increases on frequent purchases.

**Subscription Tracker** - Surfaces all recurring payments in one place so users can easily spot and cancel services they no longer need.

**AI Chatbot** - Users can chat directly with Nim, the AI agent, to ask questions about their spending, get financial advice, or dig into specific transactions.

Built to align with Liminal's values of user consent, privacy, and transparency - the agent only analyses authorised transaction data and provides clear, explainable recommendations.

## Tech Stack

- **Backend** - Go, built on the `nim-go-sdk` WebSocket server
- **AI** - Claude (Anthropic) via `anthropic-sdk-go`
- **Frontend** - React + TypeScript (Vite), using the `nim-chat` widget
- **Banking Integration** - Liminal financial APIs (balance, transactions, payments)

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

## Key Features

- **Background analysis loop** - Automatically checks recent purchases every 5 seconds and posts savings opportunities to the notice board
- **Large transaction alerts** - Flags any outgoing transaction over $1,000 in real time
- **Recurring payment detection** - Uses AI to identify subscriptions and repeating charges, surfacing all recurring payments in one place
- **Savings calculator** - Shows at a glance whether a user is heading into the red based on their spending patterns
- **Fraud warning system** - Postmortem analysis of purchases to flag suspicious or unusual transactions
- **Conversational agent** - Users can ask Nim (the AI) directly about their purchases, spending patterns, or alternatives for specific products
- **Modular tool system** - Custom Claude tools for reading transactions, searching alternatives, and posting/reading alerts

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

## Challenges & Limitations

Built under time pressure, so a few rough edges remain:

- Competitor suggestions are based on AI inference rather than live pricing data
- Limited to mock transaction data - real Liminal transaction integration was partially blocked by API connectivity issues during the hackathon
- Product matching accuracy could be improved with richer datasets and broader retailer coverage

## What's Next

- Expanded blockchain integration with support for multiple cryptocurrencies
- Improved competitor search using live pricing data rather than AI inference
- Long-term spending pattern analysis for smarter recommendations
- Enhanced fraud detection with more granular transaction signals

## About
> finAI - the final AI for finance

FinAI was built as a team project during the Hackathons UK x HackSouthWest 2026 x Liminal Hackathon. This repo is a cleaned-up showcase fork of the original submission - the codebase has been restructured for readability but the core logic is unchanged from what was demoed on the day.

The project is a proof of concept exploring how AI-driven financial analysis can be integrated into blockchain-based banking systems to help users spend more efficiently.

### Special Thanks
A massive thank you to my amazing team for making this happen in 24 hours:
- Sholto Coulter
- Millie Clark
- Theo Swan
- Tamara Spalding

And to the organisers and sponsors who put on a brilliant event:
- [Superteam UK](https://www.linkedin.com/company/superteamuk/)
- [Hack South West](https://www.linkedin.com/company/hack-south-west/)
- [Hackathons UK](https://www.hackathons.org.uk/)
- [Exeter Computer Science Society (ExCS)](https://excs.uk/)
- [Liminal](https://www.becomeliminal.com/)

> Showcase fork - original submission: [src238/Untitled-AI](https://github.com/src238/Untitled-AI)
