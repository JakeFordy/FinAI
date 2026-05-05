# FinAI - Liminal AI Financial Assistant

<p align="center">
  <img src="https://github.com/user-attachments/assets/1b95e4a2-77d6-4dfb-bbfb-54501b18f43e" alt="Liminal Logo" height="80"/>
  &nbsp;&nbsp;&nbsp;&nbsp;
  <img src="https://github.com/user-attachments/assets/56fbab03-0f81-4af1-9425-0483e5e04bc6" alt="HackSouthWest Logo" height="80"/>
</p>
<p align="center"><em>Built for Liminal at HackSouthWest 2026</em></p>

<p align="center">
  <img src="https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white" alt="Go"/>
  <img src="https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB" alt="React"/>
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript"/>
  <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" alt="Vite"/>
  <img src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=anthropic&logoColor=white" alt="Claude"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/🏆_Most_Innovative_Hack-HackathonsUK-orange?style=flat-square" alt="Most Innovative Hack"/>
  <img src="https://img.shields.io/badge/🏆_Best_Documentation_%26_Outreach-Superteam_UK_AI_Agents-blue?style=flat-square" alt="Best Documentation"/>
  <img src="https://img.shields.io/badge/⏰_Built_in-24_hours-red?style=flat-square" alt="Built in 24 hours"/>
</p>

<p align="center">
  An AI-powered financial agent that analyses a user's transaction history, finds cheaper alternatives to their recent purchases, and delivers recommendations directly within Liminal's chat interface - helping users spend smarter and safer without sacrificing quality.
</p>

---

> 📌 This is a cleaned-up showcase fork of our original hackathon submission. Original repo: <a href="https://github.com/src238/Untitled-AI">src238/Untitled-AI</a>

## Demo

<p align="center">
  <video src="https://github.com/user-attachments/assets/1a7f7fae-516a-448f-99a5-e403e26da5ee" width="80%" controls></video>
</p>
<p align="center">
  <a href="https://github.com/JakeFordy/FinAI/releases/download/v1.0/finAI.demo.mp4">⬇️ Download Full Demo</a> &nbsp;|&nbsp;
  <a href="https://hack-south-west.devpost.com/">🏆 Devpost Submission</a>
</p>

## What It Does

FinAI is a financial assistant that sits alongside a user's Liminal account and helps them spend smarter. It displays spending patterns through graphs and tables, runs continuous AI analysis in the background, and surfaces insights directly in the interface - without the user having to ask.

<table>
<tr>
<td width="50%" align="center" valign="middle">

### 💳 Recent Transactions
A clean, scrollable table of all transactions with filters for all, sent, or received payments - making it easy to track exactly where money is going.

</td>
<td width="50%">
<img src="https://github.com/user-attachments/assets/2d0012e1-b98b-4361-8ce5-96267dfd9737" alt="Recent Transactions"/>
</td>
</tr>
  
<tr>

<td width="50%">
<img src="https://github.com/user-attachments/assets/a4aa2791-583a-4337-a82e-2c17c603905e" alt="AI Chatbot"/>
</td>
<td width="50%" align="center" valign="middle">

### 🤖 AI Chatbot
Users can chat directly with Nim, the AI agent, to ask questions about their spending, get financial advice, or dig into specific transactions.

</td>
</tr>
<tr>
<td width="50%" align="center" valign="middle">

### 📊 Graph Analysis
Visual breakdown of spending patterns across categories, merchants, and time periods.

</td>
<td width="50%">
<img src="https://github.com/user-attachments/assets/87cf4466-10b8-4a21-84a4-49176dfd0e3e" alt="Graph Analysis"/>
</td>
</tr>
<tr>

<td width="50%">
<img src="https://github.com/user-attachments/assets/aa50ebf1-89d3-4e4a-bef6-0a1079614c04" alt="Recurring Payments"/>
</td>
<td width="50%" align="center" valign="middle">

### 📅 Subscription Tracker
Surfaces all recurring payments in one place so users can easily spot and cancel services they no longer need.

</td>
</tr>
<tr>
<td width="50%" align="center" valign="middle">

### 💵 Budget Planner
Users can set a monthly budget target and see in real time whether they're on track, saving, or overspending.

</td>
<td width="50%">
<img src="https://github.com/user-attachments/assets/4b13abb3-d210-49be-bf5b-6642e37ef849" alt="Budget Planner"/>
</td>
</tr>

<tr>

<td width="50%">
  <p align="center">
    <img src="https://github.com/user-attachments/assets/0b666946-6395-49ee-b308-b245ae771a3f" alt="AI Insights - Large Transaction Alert" width="35%" style="vertical-align: middle;"/>      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    <img src="https://github.com/user-attachments/assets/83c029d2-a567-4304-8175-172046f4379f" alt="AI Insights - Alternative Found 1" width="35%" style="vertical-align: middle;"/>

  </p>
</td>
<td width="50%" align="center" valign="middle">
<br/>
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
  
### 📰 AI Insights
A background analysis loop continuously scans recent purchases and finds cheaper, good-quality alternatives, as well as flagging suspicious transactions and price increases on frequent purchases.
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
    
<br/>

</td>
</tr>
</table>






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

> *finAI - the final AI for finance*

FinAI was built as a team project during the Hackathons UK x HackSouthWest 2026 x Liminal Hackathon. This repo is a cleaned-up showcase fork of the original submission - the codebase has been restructured for readability but the core logic is unchanged from what was demoed on the day.

The project is a proof of concept exploring how AI-driven financial analysis can be integrated into blockchain-based banking systems to help users spend more efficiently.

More about the event: [HackSouthWest 2026](https://hack-south-west.excs.uk) | [Devpost](https://hack-south-west.devpost.com/)

### Special Thanks

A massive thank you to my amazing team for making this happen in 24 hours:
- Sholto Coulter
- Millie Clark
- Theo Swan
- Tamara Spalding

And to the organisers and sponsors who put on a brilliant event:

<p align="center">
  <a href="https://www.becomeliminal.com/"><img src="https://github.com/user-attachments/assets/1b95e4a2-77d6-4dfb-bbfb-54501b18f43e" alt="Liminal" height="80"/></a>
  &nbsp;&nbsp;
  <a href="https://www.nvidia.com/"><img src="https://github.com/user-attachments/assets/fd5f5261-e2f6-4191-90ae-afc35278d35e" alt="NVIDIA" height="80"/></a>
  &nbsp;&nbsp;
  <a href="https://www.linkedin.com/company/superteamuk/"><img src="https://github.com/user-attachments/assets/c87fd37b-0997-4e39-acbc-d3dda8dc405a" alt="Superteam Exeter" height="80"/></a>
  &nbsp;&nbsp;
  <a href="https://excs.uk/"><img src="https://github.com/user-attachments/assets/f36f4a24-3c45-4e86-a93d-56c992ba7dd8" alt="ExCS" height="80"/></a>
  &nbsp;&nbsp;
  <a href="https://www.hackathons.org.uk/"><img src="https://github.com/user-attachments/assets/ff62c9e2-8e39-4ddf-8a0d-4577e8466b11" alt="Hackathons UK" height="80"/></a>
</p>
<p align="center">
  <a href="https://www.solana.com/"><img src="https://github.com/user-attachments/assets/747cbefc-a18d-40fb-a0af-8e0fa025e882" alt="Solana" height="70"/></a>
  &nbsp;&nbsp;
  <a href="https://www.encodeclub.com/"><img src="https://github.com/user-attachments/assets/fb0f6f1a-621d-4a95-82f6-a24ef70583a1" alt="Encode Club" height="70"/></a>
  &nbsp;&nbsp;
  <a href="https://www.exeter.ac.uk/"><img src="https://github.com/user-attachments/assets/c6e856f5-72e8-4fd1-9dce-730f873cf312" alt="University of Exeter" height="70"/></a>
  &nbsp;&nbsp;
  <a href="https://www.tenzing.co/"><img src="https://github.com/user-attachments/assets/1315d39c-fdae-431e-a395-a67099a1ae34" alt="Tenzing" height="70"/></a>
</p>

> Showcase fork - original submission: [src238/Untitled-AI](https://github.com/src238/Untitled-AI)







