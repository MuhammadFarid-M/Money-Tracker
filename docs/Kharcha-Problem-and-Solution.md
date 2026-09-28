# Kharcha: Your AI Money Diary

*Working name: "kharcha" is Hindi for expense.*

---

## Problem Statement

**Digital payments made spending effortless, and made it invisible.**

With UPI and cards, a ₹40 chai and a ₹4,000 pair of shoes both take the same single tap. There is no wallet getting thinner, so people lose track of how much they spend.

1. **People don't know where their money goes.** Money leaves in dozens of small payments a week across UPI, cards and cash. By the 25th of the month, most people can't say how much went to food, travel or shopping.
2. **They find out too late.** Bank statements and most apps show spending after the month is over. By then the salary is gone and the savings goal is missed again.
3. **Tracking apps get abandoned.** Logging every expense by hand is tedious, so most people stop within a couple of weeks.
4. **Monthly budgets don't translate into daily decisions.** "₹50,000 a month" doesn't help at the café counter. People need to know what they can spend *today*.
5. **A monthly budget isn't a spending plan.** "₹50,000 a month" says nothing about how much is for food, how much for a bike goal, and what to give up when you overspend.
6. **Simple "daily limit" tools give wrong warnings.** Dividing the budget by 30 flags day 1 as overspending, even though rent and bills are paid then. False alarms train people to ignore alerts.

**In one line:** people earn regularly but can't see, control or understand their spending until it's too late to change it.

---

## Our Solution

**Kharcha is an AI money diary built on envelope budgeting. Every rupee of your salary gets an envelope, logging is effortless, and before you buy something Kharcha shows what it really costs your goals.**

### 1. Give every rupee an envelope
The user enters their **monthly salary** and **fixed monthly costs** (rent, Wi-Fi, subscriptions; logged automatically every month), then splits the rest into envelopes:
- **Spending envelopes** for each category: Food, Groceries, Travel, Shopping, and so on.
- **Goal envelopes** with a target: *Bike ₹2,00,000 at ₹12,000 a month*, with progress and months to go.
- **Savings**, locked so it doesn't get spent by accident.

Kharcha shows how much of the salary is still **unallocated**.

### 2. Log spending in seconds
- **📸 Snap a bill:** AI reads the photo and **splits it item by item into categories**. A single supermarket bill becomes groceries + snacks + household.
- **⚡ Quick add:** type *"chai 20, auto 60, lunch 180"* and it becomes three categorized expenses.
- **✍️ Type it:** amount, category, note and date.
- **💬 Tell the assistant:** *"spent 250 on dinner"* gets logged from the chat.

### 3. Check before you buy
- **"Can I afford this?":** type a price, e.g. *Shoes ₹5,000*. Kharcha checks the matching envelope.
  - If it fits: *"Yes. Shopping goes from ₹7,000 to ₹2,000, about ₹680 a day."*
  - If it doesn't: *"Shopping has ₹2,000. You're ₹3,000 short."* Then it shows the trade-offs: take it from unallocated money, from another envelope (*"leaves Travel ₹500"*), or from a goal (*"delays your Bike by about 1 week"*). Savings stay locked unless you unlock them.
  - **Skip it** and Kharcha records how much you kept in your plan.
- **Overspending gets covered:** if an expense takes an envelope below zero, Kharcha asks which envelope should cover it, so the plan always adds up.
- **Month end:** leftovers in each envelope either **move to Savings** or **carry over** to next month (the user chooses per envelope).

### 4. Know what's safe to spend today
- Fixed costs are **planned, not overspending**. Only variable spending is paced.
- **Safe to spend today** = what's left of the variable budget ÷ days left. Spend less today and tomorrow's allowance grows.
- **Early warnings based on the trend:** *"You're ₹3,200 ahead of pace. At this rate you'll spend ₹54,100 this month, ₹4,100 over your target."*
- Category alerts compare with the same point last month, and small payments under ₹200 are totalled up.

### 5. See where the money goes
- **Charts:** spending vs the ideal pace line (with a month-end projection), category breakdown, daily spending, a share-of-spending donut and a month-by-month comparison.
- **Monthly history:** every month is kept separately with its total vs target, savings, how each envelope ended (moved to Savings, carried over, or overspent), top category, daily chart and a comparison with the previous month. Drill down from month → category → expense → bill items.

### 6. Ask anything about your money
An AI assistant answers from the user's real data, with suggested questions above the prompt bar:
- *"Can I afford ₹3,000 shoes?"*
- *"How much is left in my envelopes?"*
- *"How much can I spend today?"*
- *"Where did most of my money go this month?"*
- *"Am I on track to save ₹20,000?"*
- *"Compare with last month"*

The app's code calculates every number; the AI only explains it, so answers stay accurate.

---

## How Kharcha Is Different

| | Typical expense trackers | Bank / UPI app history | **Kharcha** |
|---|---|---|---|
| Budgeting | One monthly limit, or none | None | **Envelopes per category and goal; leftovers roll into Savings** |
| Before buying | Nothing | Nothing | **"Can I afford this?" shows the trade-off first** |
| Logging | Manual forms | Automatic but unlabelled | **Photo, quick text, chat or form** |
| Bill understanding | Total amount only | Merchant name only | **Item-level split by category** |
| Daily guidance | Fixed daily limit, or none | None | **"Safe to spend today", adjusting daily** |
| Fixed costs | Counted as overspending | — | **Planned separately, never false alarms** |
| Warnings | After the limit is crossed | None | **Early, from the spending trend and projection** |
| Questions | Filters and reports | None | **AI assistant grounded in your own data** |

*Check competitors' current features before presenting; apps change often.*

**Why not just ask ChatGPT?** It doesn't keep your envelopes and expenses up to date, can't tell you what a purchase does to your goals using your real balances, and won't tell you each morning how much you can safely spend.

---

## Who It's For
- Young professionals and students managing their first salaries or stipends.
- Anyone who pays mostly by UPI and feels their money "disappears".
- Households trying to hit a monthly savings target.

---

## Hackathon Scope

**Built:**
- Home page, and setup of salary, fixed costs, spending envelopes, goals and savings
- Add expenses by bill photo (AI item split), quick text, typed form or chat
- Envelopes tab: balances, per-day amounts, goals, locked savings, moving money between envelopes
- "Can I afford this?" with trade-offs (unallocated, other envelopes, goal delay), and covering overspent envelopes
- Month-end leftovers: move to Savings or carry over, per envelope
- Today dashboard: safe to spend today, pace chart with projection, alerts, category bars
- Monthly history with charts, month detail, previous-month comparison, category and expense drill-down
- AI assistant with suggested questions
- Mobile-first web app

**Production roadmap:**
- Automatic bank transaction sync via India's Account Aggregator framework
- Reading UPI payment SMS on Android
- Shared household budgets
- Voice input in Hindi and other Indian languages
