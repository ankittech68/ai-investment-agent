# InvestIQ — AI Investment Research Agent

An AI-powered investment research platform that analyzes publicly traded companies in real time using Google Gemini 2.5 Flash and LangChain, enriched with financial data and market news from the Finnhub API.

## Overview

InvestIQ helps users make informed investment decisions by generating AI-powered stock analysis. The platform collects company information, financial metrics, stock quotes, and recent news, then uses an LLM-driven reasoning pipeline to produce:

* Investment Recommendation (Invest / Watchlist / Pass)
* Investment Score
* Confidence Score
* Risk Assessment
* SWOT Analysis
* Detailed AI Reasoning

## Tech Stack

### Frontend

* React 18
* Vite
* Tailwind CSS
* Recharts

### Backend

* Node.js
* Express.js

### AI Layer

* LangChain.js
* Google Gemini 2.5 Flash

### Data Source

* Finnhub API

### Deployment

* Frontend: Vercel
* Backend: Render

---

## Project Structure

```text
ai-investment-agent/
├── backend/
│   └── src/
│       ├── agents/
│       │   └── investmentAgent.js
│       ├── controllers/
│       │   └── researchController.js
│       ├── routes/
│       │   └── research.js
│       ├── services/
│       │   └── finnhubService.js
│       └── index.js
└── frontend/
    └── src/
        ├── components/
        ├── pages/
        ├── services/
        └── App.jsx
```

---

## Architecture

```text
React Frontend (Vercel)
          ↓
Express Backend (Render)
          ↓
Finnhub API
          ↓
LangChain Agent
          ↓
Gemini 2.5 Flash
          ↓
Investment Recommendation Output
```

---

## Setup Instructions

### 1. Obtain API Keys

* Finnhub API Key
* Gemini API Key

### 2. Backend Setup

```bash
cd backend
npm install
```

Create `.env`

```env
PORT=5000
GEMINI_API_KEY=your_key
FINNHUB_API_KEY=your_key
```

Run Backend:

```bash
npm start
```

Backend runs on:

```text
http://localhost:5000
```

### 3. Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend runs on:

```text
http://localhost:5173
```

---

## How It Works

### Step 1

User enters a company name or ticker symbol.

### Step 2

Backend resolves the ticker symbol using Finnhub search.

### Step 3

Company profile and stock information are fetched.

### Step 4

Financial metrics and stock quote data are collected.

### Step 5

Recent company news is retrieved.

### Step 6

All collected data is sent to Gemini 2.5 Flash through a LangChain workflow.

### Step 7

The AI generates:

* Recommendation
* Investment Score
* Confidence Score
* Risk Level
* SWOT Analysis
* Detailed Reasoning

---

## Features

### Home Page

* Company search
* Example company chips

### Loading Screen

* Animated analysis progress

### Results Page

* Company profile
* Stock price
* Recommendation card
* Investment score
* Confidence score
* Risk level
* Financial metrics
* SWOT analysis
* News articles
* AI-generated reasoning

---

## Key Decisions & Trade-offs

### Decisions

* Chose Gemini 2.5 Flash for fast inference and low latency.
* Used LangChain to organize the AI workflow.
* Selected Finnhub because it provides profile, quote, financial, and news data from a single API.
* Used React and Vite for rapid frontend development.

### Trade-offs

* Free-tier API limits may restrict heavy usage.
* Analysis quality depends on external API availability.
* Current version focuses on single-company analysis.
* Historical portfolio tracking is not implemented.

---

## Example Runs

### Netflix (NFLX)

Recommendation: INVEST

Investment Score: 84/100

Key Insights:

* Strong global subscriber base
* Expanding advertising business
* Competitive streaming market

### Apple (AAPL)

Recommendation: WATCHLIST

Investment Score: 78/100

Key Insights:

* Strong cash position
* Consistent profitability
* Mature smartphone market

### Microsoft (MSFT)

Recommendation: INVEST

Investment Score: 89/100

Key Insights:

* Strong cloud business growth
* AI integration across products
* Diversified revenue streams

---

## Deployment

### Frontend

Deploy `/frontend` on Vercel.

Environment Variable:

```env
VITE_API_URL=https://your-render-backend-url/api
```

### Backend

Deploy `/backend` on Render.

Environment Variables:

```env
GEMINI_API_KEY=your_key
FINNHUB_API_KEY=your_key
NODE_ENV=production
```

---

## Future Improvements

* Portfolio analysis
* Multi-company comparison
* Historical stock trends
* User authentication
* PDF report generation
* Multi-LLM support
* Advanced financial ratio analysis

---

## AI Development Process

This project was developed using AI-assisted software engineering practices.

AI tools were used for:

* Architecture planning
* LangChain workflow design
* API integration
* UI development
* Deployment troubleshooting
* Debugging and optimization

All implementation, testing, deployment, and integration decisions were performed manually.

---

## Repository

GitHub Repository:
https://github.com/ankittech68/ai-investment-agent
