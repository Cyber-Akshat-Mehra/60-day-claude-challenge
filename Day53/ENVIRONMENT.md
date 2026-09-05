# ENVIRONMENT.md — AI-Powered Personal Finance Analyzer
### Day 3 Deliverable | AB Talks 60-Day Claude AI Challenge Capstone

> Complete reference for every environment variable, tool, and external configuration this project depends on.

---

## 1. Environment Variables

All frontend environment variables must be prefixed with `VITE_` to be accessible in the browser (Vite's requirement). These live in `.env.local`, which is git-ignored and never committed.

| Variable | Used By | Description | Where to Find It |
|---|---|---|---|
| `VITE_SUPABASE_URL` | `src/services/supabaseClient.js` | Base URL of the Supabase project (e.g. `https://xxxx.supabase.co`) | Supabase Dashboard → Settings → API (or Integrations → Data API) |
| `VITE_SUPABASE_ANON_KEY` | `src/services/supabaseClient.js` | Public/anonymous key — safe for frontend use because Row-Level Security restricts what it can access | Supabase Dashboard → Settings → API Keys → Legacy anon, service_role API keys → `anon` `public` |

**Server-side only (to be added on Day 5, for the `/api/*` serverless functions — never in `.env.local`, set directly in Vercel dashboard when we deploy):**

| Variable | Used By | Description |
|---|---|---|
| `ANTHROPIC_API_KEY` | `api/categorize.js`, `api/insights.js`, `api/chat.js` | Anthropic Claude API key. Never exposed to the browser — read only inside serverless functions. |

---

## 2. Local Tools

| Tool | Version Used | Why It's Needed |
|---|---|---|
| Node.js | v22.18.0 | JavaScript runtime for the dev server, build process, and (later) serverless functions |
| npm | 10.9.3 | Installs and manages all project dependencies |
| Git | 2.50.1 | Version control, connects local project to GitHub |
| VS Code (or any editor) | — | Code editing; no required extensions for this stack, though ESLint/Prettier extensions are helpful |

---

## 3. External Services & Accounts

| Service | Purpose | Free Tier? |
|---|---|---|
| GitHub | Source control, connects to Vercel for deployment | Yes |
| Supabase | Postgres database + Authentication (signup/login/reset) | Yes |
| Anthropic (Claude API) | Powers categorization, insights, and chat features | Low-cost/free credits depending on plan |
| Vercel | Hosting for frontend + serverless API functions (set up Day 10) | Yes |

---

## 4. Supabase Project Configuration

| Setting | Value | Why |
|---|---|---|
| Region | South Asia (Mumbai) | Closest to builder's location for lowest latency |
| Email Auth Provider | Enabled | Required for signup/login (PRD FR-1) |
| Confirm Email | **Disabled** | PRD explicitly excludes email verification from v1.0 scope — signup grants immediate access |
| Row-Level Security | Enabled on `transactions` table | Enforces per-user data isolation at the database level |

---

## 5. Configuration Files (in repo)

| File | Purpose |
|---|---|
| `.env.local` | Local environment variables (git-ignored, never committed) |
| `.gitignore` | Excludes `node_modules/`, `.env*.local`, build output, etc. |
| `package.json` | Lists all dependencies and npm scripts (`dev`, `build`, `preview`) |
| `vite.config.js` | Vite's build/dev server configuration (default settings, no custom changes yet) |

---

## 6. Security Notes

- The `service_role secret` key from Supabase must **never** be used anywhere in this project's frontend code, and is not currently used anywhere (v1.0 relies entirely on RLS + the `anon public` key).
- The Anthropic API key will only ever be read server-side (inside `/api` serverless functions), starting Day 5.
- Any file containing secrets or passwords (e.g., database passwords) should be stored outside the project folder — never inside `finance-analyzer/`, even temporarily.
