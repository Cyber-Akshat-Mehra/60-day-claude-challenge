# Project Structure — AI-Powered Personal Finance Analyzer
### Day 2 Deliverable | AB Talks 60-Day Claude AI Challenge Capstone

> Complete folder layout for the repository. Matches the locked tech stack: React (Vite) frontend, Vercel serverless functions, Supabase for data/auth. This structure is the target for all future implementation days — create folders as needed, matching this layout.

---

## Full Folder Tree

```
finance-analyzer/
├── api/                          # Vercel serverless functions (backend)
│   ├── categorize.js             # POST /api/categorize
│   ├── insights.js               # POST /api/insights
│   └── chat.js                   # POST /api/chat
│
├── src/                          # React frontend source
│   ├── components/               # Reusable UI building blocks
│   │   ├── Navbar.jsx
│   │   ├── AddTransactionForm.jsx
│   │   ├── TransactionList.jsx
│   │   ├── CategoryPieChart.jsx
│   │   ├── SpendingTrendChart.jsx
│   │   ├── SummaryCards.jsx
│   │   ├── InsightsPanel.jsx
│   │   ├── ChatBubble.jsx
│   │   ├── SuggestedQuestions.jsx
│   │   └── ProtectedRoute.jsx
│   │
│   ├── pages/                    # Full screens (one per route)
│   │   ├── LoginPage.jsx
│   │   ├── SignupPage.jsx
│   │   ├── ForgotPasswordPage.jsx
│   │   ├── DashboardPage.jsx
│   │   ├── TransactionsPage.jsx
│   │   ├── CsvUploadPage.jsx
│   │   └── ChatPage.jsx
│   │
│   ├── services/                 # All external calls live here — nowhere else
│   │   ├── supabaseClient.js      # ✅ Created Day 3 — single shared Supabase connection
│   │   ├── auth.js                # Supabase Auth wrapper (signUp, signIn, signOut, resetPassword)
│   │   ├── transactions.js        # Supabase DB wrapper (CRUD)
│   │   ├── csvParser.js           # PapaParse wrapper + validation
│   │   ├── aiCategorize.js        # calls /api/categorize
│   │   ├── aiInsights.js          # calls /api/insights
│   │   └── aiChat.js              # calls /api/chat
│   │
│   ├── context/
│   │   └── AuthContext.jsx        # Tracks logged-in user/session app-wide
│   │
│   ├── constants/
│   │   └── categories.js          # Fixed category list — single source of truth, reused everywhere
│   │
│   ├── utils/
│   │   └── aggregations.js        # groupByCategory(), groupByPeriod() — pure functions for charts/insights
│   │
│   ├── App.jsx                    # Route definitions
│   └── main.jsx                   # App entry point
│
├── public/
│   └── template.csv               # Downloadable CSV template for users
│
├── docs/                          # All planning deliverables live here for reference
│   ├── PRD.md
│   ├── ARCHITECTURE.md
│   ├── SCHEMA.md
│   ├── API.md
│   ├── UI-WIREFRAMES.md
│   └── IMPLEMENTATION-BLUEPRINT.md
│
├── .env.local                     # API keys/secrets — NEVER committed (in .gitignore)
├── .gitignore
├── package.json
├── vercel.json                    # Vercel routing/config (if needed)
└── README.md
```

---

## Folder Responsibilities & Rationale

| Folder | Responsibility | Why separated this way |
|---|---|---|
| `api/` | Only place that talks to the Claude API | Vercel auto-detects this folder as serverless functions; keeping all AI calls here guarantees the API key is never bundled into frontend code |
| `src/components/` | Small, reusable UI pieces | Keeps pages readable; a chart or form isn't duplicated across screens |
| `src/pages/` | One file per route/screen | Matches the screen inventory in `UI-WIREFRAMES.md` 1:1 — easy to find "the file for X screen" |
| `src/services/` | Every external call (Supabase, AI endpoints) | Single boundary layer — if an API changes, only one file needs updating; components never call Supabase or `fetch()` directly |
| `src/context/` | App-wide state (just auth for v1.0) | Avoids prop-drilling the current user through every component |
| `src/constants/categories.js` | The fixed category list | Referenced by the manual form dropdown, CSV categorization, AI prompts, and the DB CHECK constraint — must never drift out of sync, so it lives in exactly one place |
| `src/utils/aggregations.js` | Pure data-transformation functions | Reused identically by both the dashboard charts (Day 6) and the insights prompt (Day 7) — no duplicated aggregation logic |
| `docs/` | All planning deliverables | Keeps the repo self-documenting; future-day AI sessions (or anyone else) can find the source of truth without leaving the repo |
| `public/template.csv` | Sample file for users | Matches the CSV Upload screen's "Download Template" button |

---

## Where Future Code Will Live (by Blueprint Day)

| Day | Primary folders touched |
|---|---|
| Day 3 (Auth) | `src/services/auth.js`, `src/context/AuthContext.jsx`, `src/components/ProtectedRoute.jsx`, `src/pages/LoginPage.jsx`, `SignupPage.jsx`, `ForgotPasswordPage.jsx` |
| Day 4 (Transactions CRUD) | `src/services/transactions.js`, `src/constants/categories.js`, `src/components/AddTransactionForm.jsx`, `TransactionList.jsx` |
| Day 5 (CSV + Categorization) | `src/pages/CsvUploadPage.jsx`, `src/services/csvParser.js`, `aiCategorize.js`, `api/categorize.js`, `public/template.csv` |
| Day 6 (Dashboard & Charts) | `src/utils/aggregations.js`, `src/components/CategoryPieChart.jsx`, `SpendingTrendChart.jsx`, `SummaryCards.jsx` |
| Day 7 (Insights) | `api/insights.js`, `src/services/aiInsights.js`, `src/components/InsightsPanel.jsx` |
| Day 8 (Chat) | `api/chat.js`, `src/services/aiChat.js`, `src/pages/ChatPage.jsx`, `src/components/ChatBubble.jsx`, `SuggestedQuestions.jsx` |
| Day 9 (Testing & Polish) | Any file, as bugs are found; possibly `src/styles/` for a consistency pass |
| Day 10 (Deployment) | `README.md`, `vercel.json`, environment variable configuration on Vercel dashboard |

This structure directly mirrors the Implementation Blueprint's Day 4–8 "Files and folders" sections — nothing here conflicts with what's already planned; it simply makes the full picture explicit before implementation begins.

---

## Day 3 Status Update

As of Day 3, the full folder tree above has been created in the actual repository, with placeholder content in all `src/pages/*.jsx` files and a working `src/services/supabaseClient.js`. Routing is live in `App.jsx`. All other `src/components/`, `src/context/`, `src/constants/`, and `src/utils/` files exist as empty placeholders, ready to be filled in starting Day 4 per the Implementation Blueprint.
