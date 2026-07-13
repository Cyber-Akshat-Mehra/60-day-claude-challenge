# 30-Day MERN Roadmap: Build & Deploy 3 Productivity Web Apps

**Profile:** Student | Intermediate MERN | 1-2 hrs/day | Mixed learning style (videos + projects + docs)
**Goal:** Ship 3 real, deployed web apps that make someone's work/life easier, packaged into a portfolio.

**Guiding principle:** You already know MERN basics. This roadmap isn't "learn MERN again" — it's *build → deploy → repeat*, with each project adding one new real-world skill (auth → data viz → real-time). By Day 30 you'll have 3 live URLs you can put on a resume, not just repo links.

---

## Overview

| Week | Focus | Output |
|------|-------|--------|
| 1 | Project 1: **QuickTask** — Task manager with auth | Live app #1 |
| 2 | Project 2: **ExpenseIQ** — Expense tracker with dashboards | Live app #2 |
| 3 | Project 3: **CollabBoard** — Real-time Kanban board | Live app #3 |
| 4 | Testing, security, portfolio site, polish | Portfolio showcasing all 3 |

**Daily time budget (1-2 hrs):** ~20 min learning/reading/video, ~60-80 min building, ~10 min committing + notes.

---

## Week 1: QuickTask (Task Manager with Auth)

**Milestone by Day 7:** A deployed, authenticated task manager where a user can sign up, log in, and manage personal tasks (create, edit, complete, delete).

- **Day 1 — Plan & Setup**
  - Task: Sketch 4-5 core features (auth, add/edit/delete task, mark complete, due dates). Set up GitHub repo + folder structure (client/server). Init Express server + React app (Vite).
  - Resource: MongoDB Atlas free-tier setup docs; Express official docs (routing section).
  - Learning style tip: Watch one short video on JWT auth flow if rusty (search "JWT auth MERN" on YouTube — Traversy Media or freeCodeCamp are reliable channels).

- **Day 2 — Backend Models & Routes**
  - Task: Build Mongoose schemas for `User` and `Task`. Build REST routes: `POST /register`, `POST /login`, `GET/POST/PUT/DELETE /tasks`.
  - Resource: Mongoose docs (schemas & validation).

- **Day 3 — Authentication**
  - Task: Implement bcrypt password hashing + JWT issuing/verification middleware. Protect task routes so only logged-in users see their own tasks.
  - Resource: `jsonwebtoken` and `bcryptjs` npm docs.

- **Day 4 — Frontend Core UI**
  - Task: Build React pages: Login, Register, Dashboard. Wire up forms with basic validation. Store JWT in memory/context (not localStorage if you want to be strict about security — fine either way for a learning project).
  - Resource: React docs on Context API for auth state.

- **Day 5 — Connect Frontend to Backend**
  - Task: Hook up Axios/fetch calls to your API. Test full flow: register → login → see tasks → add/edit/delete task. Debug CORS issues now (common blocker).
  - Resource: Postman — test every endpoint independently before blaming the frontend.

- **Day 6 — UI Polish**
  - Task: Add Tailwind CSS (or your preferred styling), make it mobile-responsive, add loading/error states.
  - Resource: Tailwind docs "responsive design" section.

- **Day 7 — Deploy + Milestone**
  - Task: Deploy backend (Render or Railway), frontend (Vercel or Netlify), DB (MongoDB Atlas). Test the live link end-to-end.
  - Resource: Render/Vercel deployment docs for Node + React.
  - **Milestone: Live App #1 ✅**

---

## Week 2: ExpenseIQ (Expense Tracker with Dashboards)

**Milestone by Day 14:** A deployed expense tracker with categorized spending and a visual dashboard — genuinely useful for daily life.

- **Day 8 — Plan & Schema**
  - Task: Design `Expense` schema (amount, category, date, note, userId). Reuse Week 1's auth middleware — don't rebuild it.
  - Resource: Recharts docs (skim the bar/pie chart examples).

- **Day 9 — Backend: CRUD + Aggregation**
  - Task: Build expense CRUD routes. Add one aggregation endpoint (e.g., total spend per category using MongoDB aggregation pipeline).
  - Resource: MongoDB aggregation pipeline docs (`$group`, `$sum`).

- **Day 10 — Protect Routes & Test API**
  - Task: Apply auth middleware to all expense routes. Test with Postman using different users to confirm data isolation.

- **Day 11 — Frontend: Forms & Lists**
  - Task: Build add-expense form and a filterable expense list (by category/date range).

- **Day 12 — Data Visualization**
  - Task: Add a Recharts dashboard — pie chart (spend by category), line/bar chart (spend over time).

- **Day 13 — Filtering, Search, Pagination**
  - Task: Add search by note/category and paginate the expense list for performance.

- **Day 14 — Deploy + Milestone**
  - Task: Deploy this as a separate app (new Render/Vercel instance). Confirm both apps run independently and correctly.
  - **Milestone: Live App #2 ✅**

---

## Week 3: CollabBoard (Real-Time Kanban Board)

**Milestone by Day 21:** A deployed, multi-user real-time Kanban board — this is the "new skill" week (Socket.io + drag-and-drop).

- **Day 15 — Learn Real-Time Basics**
  - Task: Watch one focused tutorial on Socket.io with Express + React (20-30 min). Plan schema: `Board`, `List`, `Card`.
  - Resource: Socket.io official "get started" guide.

- **Day 16 — Backend Models & REST**
  - Task: Build REST endpoints for boards/lists/cards (create/read/update/delete/reorder).

- **Day 17 — Real-Time Sync**
  - Task: Wire up Socket.io so that when one user moves/edits a card, others see it update live. Start with a single event (`card:moved`) before adding more.

- **Day 18 — Drag-and-Drop UI**
  - Task: Implement drag-and-drop with `@dnd-kit/core` (actively maintained) or `react-beautiful-dnd`. Focus on getting one board with 3 columns working smoothly.
  - Resource: dnd-kit docs "Sortable" example.

- **Day 19 — Multi-User Testing**
  - Task: Open the app in two browser windows (or ask a friend to join). Confirm real-time sync actually works and fix race conditions.

- **Day 20 — Polish**
  - Task: Add loading states, optimistic UI updates, error handling for dropped socket connections.

- **Day 21 — Deploy + Milestone**
  - Task: Deploy (note: Socket.io needs a host that supports WebSockets — Render works well; some static hosts don't).
  - **Milestone: Live App #3 ✅**

---

## Week 4: Testing, Security, Portfolio & Polish

**Milestone by Day 30:** All 3 apps are secure, documented, and presented on a single portfolio site — ready to share.

- **Day 22 — Add Testing**
  - Task: Add Jest + React Testing Library to one project (pick your strongest one). Write 3-5 meaningful tests (e.g., auth flow, a core CRUD action).
  - Resource: React Testing Library docs.

- **Day 23 — Performance Pass**
  - Task: Add MongoDB indexes on frequently queried fields (userId, date). Add lazy loading/code-splitting to the heaviest frontend.

- **Day 24 — Security Hardening**
  - Task: Add `helmet`, rate limiting (`express-rate-limit`), proper CORS config, and confirm no secrets are committed (move to `.env` + hosting platform's env vars).
  - Resource: OWASP Node.js security cheat sheet (quick skim, not deep read).

- **Day 25 — Portfolio Site (Build)**
  - Task: Build a simple one-page portfolio site (can be a 4th mini-project or a static React/Next page) showcasing all 3 apps: screenshots, live links, GitHub links, one-line "problem it solves" for each.

- **Day 26 — Portfolio Site (Deploy)**
  - Task: Deploy portfolio, optionally connect a custom domain if you have one.

- **Day 27 — Documentation**
  - Task: Write a proper README for each of the 3 repos: what it does, tech stack, setup instructions, screenshots. This matters more than people expect for job/freelance credibility.

- **Day 28 — Get Real Feedback**
  - Task: Share links with 2-3 people (friends, classmates, or a dev community) and ask them to actually try to use one app. Note friction points.

- **Day 29 — Final Fixes**
  - Task: Fix the top 2-3 issues from feedback. Don't try to fix everything — prioritize what blocks usability.

- **Day 30 — Wrap-Up**
  - Task: Do a final walkthrough of all 3 live apps. Record a short screen-capture demo (2-3 min) for each — useful for job applications. Write a short reflection: what you'd build next (e.g., add AI features, mobile app, or a 4th tool).
  - **Final Milestone: 3 deployed, documented, tested productivity apps + a portfolio site ✅**

---

## Final Outcome

By Day 30 you will have:
- **3 live, deployed full-stack MERN apps** solving real productivity problems (task management, expense tracking, team collaboration)
- **1 portfolio site** linking them all with screenshots and demos
- **Documented GitHub repos** with README files
- Hands-on experience in: JWT auth, data aggregation & visualization, real-time communication (Socket.io), testing, and security hardening — skills that go beyond typical MERN tutorials

## Core Resources (reference throughout)
- **Docs:** Express, Mongoose, React, MongoDB Aggregation, Socket.io, Recharts, dnd-kit
- **Deployment:** Render/Railway (backend), Vercel/Netlify (frontend), MongoDB Atlas (database)
- **Videos:** Traversy Media, freeCodeCamp (YouTube) — for quick concept refreshers, not full courses
- **Testing:** Postman (API testing throughout), Jest + React Testing Library (Week 4)

## Notes on Pacing
- If a day's task overflows into the next, that's normal — the weekly milestone (not the daily task) is the real checkpoint.
- Reuse code aggressively: Week 2 and 3 should reuse Week 1's auth logic almost unchanged. This is intentional — it's what makes 3 apps in 30 days realistic at 1-2 hrs/day.
