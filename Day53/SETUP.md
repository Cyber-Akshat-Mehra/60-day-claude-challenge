# SETUP.md — AI-Powered Personal Finance Analyzer
### Day 3 Deliverable | AB Talks 60-Day Claude AI Challenge Capstone

> Step-by-step guide to get this project running from a fresh clone. Follow this if setting up on a new machine, or onboarding someone else to the project.

---

## Prerequisites

| Tool | Minimum Version | Verified Version (this project) | Purpose |
|---|---|---|---|
| Node.js | 18+ | v22.18.0 | Runs the dev server and build tooling |
| npm | 9+ | 10.9.3 | Installs and manages packages |
| Git | any recent | 2.50.1 | Version control |

Check your versions with:
```
node -v
npm -v
git --version
```

---

## 1. Clone the Repository

```
git clone https://github.com/Cyber-Akshat-Mehra/finance-analyzer.git
cd finance-analyzer
```

---

## 2. Install Dependencies

```
npm install
```

This installs everything listed in `package.json`, including:
- `react`, `react-dom` — core framework (from Vite scaffold)
- `@supabase/supabase-js` — Supabase client (auth + database)
- `react-router-dom` — page navigation/routing
- `recharts` — dashboard charts
- `papaparse` — CSV file parsing

---

## 3. Set Up Environment Variables

Create a file named `.env.local` in the project root (this file is git-ignored and must never be committed):

```
VITE_SUPABASE_URL=<your Supabase project URL>
VITE_SUPABASE_ANON_KEY=<your Supabase anon public key>
```

**Where to find these values:**
1. Log into [supabase.com](https://supabase.com), open the `finance-analyzer` project.
2. Go to **Settings → API** (or **Integrations → Data API**) for the Project URL.
3. Go to **Settings → API Keys → Legacy anon, service_role API keys** for the `anon public` key.

⚠️ Never use the `service_role secret` key in frontend code — only the `anon public` key belongs in `.env.local`.

See `ENVIRONMENT.md` for the full list of variables and what each one does.

---

## 4. Set Up the Database (first-time only)

If the `transactions` table doesn't already exist in your Supabase project:

1. Open the Supabase dashboard → **SQL Editor** → **New query**.
2. Paste and run the SQL from `docs/SCHEMA.md` (creates the table + Row-Level Security policy).
3. Verify in **Table Editor** that `transactions` appears with the correct columns.

---

## 5. Configure Supabase Auth Settings

1. In the Supabase dashboard, go to **Authentication → Sign In / Providers**.
2. Confirm **Email** provider is **Enabled**.
3. Confirm **"Confirm email"** (under User Signups) is turned **OFF** — this project intentionally skips email verification per the PRD, so users can sign up and use the app immediately.

---

## 6. Run the Project Locally

```
npm run dev
```

Open the URL shown in the terminal (typically `http://localhost:5173/`). You should see the app with a navigation bar and all 7 placeholder pages reachable.

---

## 7. Verify Everything Works

- [ ] `npm run dev` starts with no errors
- [ ] Navigation bar shows: Dashboard, Login, Signup, Transactions, CSV Upload, Chat
- [ ] Clicking each link loads its page with no console errors
- [ ] `.env.local` exists locally but does **not** appear in `git status`
- [ ] Supabase Table Editor shows the `transactions` table

If any step fails, see the **Common Issues** section in `docs/IMPLEMENTATION-BLUEPRINT.md` (Day 2/3 sections) for troubleshooting tips.
