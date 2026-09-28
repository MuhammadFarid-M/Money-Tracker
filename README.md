# Budgetly: AI Money Diary with Envelopes

A mobile-first web prototype for tracking money with envelope budgeting.

**Live site (GitHub Pages):** https://muhammadfarid-m.github.io/Money-Tracker/

## The idea
UPI made spending effortless and invisible. Budgetly gives every rupee of your salary an envelope, makes logging effortless, and shows what a purchase costs your goals *before* you buy it.

Full problem statement and solution: [`docs/Budgetly-Problem-and-Solution.md`](docs/Budgetly-Problem-and-Solution.md)

## What's in the prototype (`index.html`)
- **Home page** with the problem, features and a comparison with other apps
- **Setup:** salary, fixed costs, spending envelopes per category, goals (target, monthly amount, already saved) and savings
- **Envelopes tab:** what's left in each envelope, per-day amounts, goals with progress, locked savings, and moving money between envelopes
- **"Can I afford this?":** checks the matching envelope and shows the trade-offs (unallocated money, other envelopes, how long a goal gets delayed). You can also record a skipped purchase.
- **Overspending:** when an expense takes an envelope below zero, you pick another envelope to cover it
- **Month end:** leftovers in each envelope move to Savings or carry over, per envelope
- **Add expenses** by typing, quick add ("chai 20, auto 60") or bill photo (the sample bill works offline)
- **Today:** safe to spend today, pace chart with a month-end projection, and alerts
- **History:** month-by-month charts, how each envelope ended, category drill-down and bill items
- **Assistant** with suggested questions

Data is stored only in the browser (localStorage). Tap **Explore the demo** to load four months of sample data.

## About the AI features
AI bill reading, free-form chat and AI tips use Claude and only work when the page is opened as a Claude artifact. On GitHub Pages the app runs in **offline mode**: the sample bill, quick add, the suggested questions and every calculation still work. In the full hackathon build these call an LLM API from the backend.

## Other folders
- [`qr-test/`](qr-test/): the earlier Lifafa UPI QR test page. It showed that browsers can open GPay with payee and amount filled in, but GPay rejected the payment for the merchant we tested, so QR payments were dropped from the idea.
- [`docs/`](docs/): the problem statement and solution.

## Planned stack for the hackathon build
React + Vite (mobile-first PWA) · FastAPI · PostgreSQL · Groq/OpenRouter LLM · Vercel + Render
