# Personal Finance App - Product Specification

## Assumptions

- Users manually enter transactions (no bank sync in MVP)
- Single currency per user account
- Web-only (no native mobile apps)
- English language only for MVP
- Users are motivated but need structure, not gamification

---

## Product Principles

1. **Budgets are guardrails, not handcuffs.** Budgets exist to guide decisions, not to punish overspending. Exceeding a budget is information, not failure.

2. **Visibility first, restriction never.** The app shows users where their money goes. It never blocks spending or creates friction in their financial life.

3. **Gentle coaching, not judgment.** Tone matters. Nudges are supportive and factual. No guilt, no shame, no "you failed" messaging.

4. **Simplicity protects motivation.** Every feature must earn its place. Complexity kills habit formation. When in doubt, leave it out.

5. **Emotional safety is a feature.** Money is stressful. The app should feel like a calm, private space—not another source of anxiety.

---

## 1. Problem Statement

**Who:** Young professionals (25-40) who earn enough to save but struggle to understand where their money goes. They've tried spreadsheets or other apps but found them either too complex or too shallow.

**Pain:** 
- No clear picture of spending patterns across categories
- Budgets feel punitive rather than helpful
- Existing tools require too much setup or ongoing maintenance
- No feedback loop between spending behavior and financial goals

**Solution:** A simple budgeting app that provides spending visibility, enforces lightweight budgets, and delivers timely nudges to encourage better financial habits.

---

## 2. Non-Goals

This app will NOT:

- Sync with bank accounts or financial institutions
- Provide investment tracking or advice
- Support multiple currencies within a single account
- Offer bill payment or money transfer features
- Include social features or spending comparisons with others
- Provide tax preparation or reporting
- Support shared/family accounts
- Include receipt scanning or OCR
- Offer financial education content or courses
- Track savings goals or financial targets (post-MVP; see Future Expansion)

---

## 3. Target User Personas

### Persona 1: "Aware Alex"
- **Age:** 28, Software Developer
- **Income:** $85k/year
- **Situation:** Earns well but has no idea why savings aren't growing. Uses credit cards for everything, pays them off monthly, but can't explain where $2k/month goes.
- **Behavior:** Checks bank balance occasionally, feels vague anxiety about money, avoids detailed tracking because it feels tedious.
- **Need:** Wants a simple way to see spending patterns without becoming an accountant.
- **Success:** "I finally know that I spend $400/month on food delivery."

### Persona 2: "Goal-Oriented Grace"
- **Age:** 34, Marketing Manager
- **Income:** $95k/year
- **Situation:** Has specific savings goals (house down payment, vacation fund) but keeps dipping into savings. Tried YNAB but found it overwhelming.
- **Behavior:** Sets budgets but abandons them when they feel restrictive. Wants guidance, not rigid rules.
- **Need:** Wants budgets that flex with reality and gentle reminders before overspending.
- **Success:** "I stayed within my dining budget this month because the app warned me at 80%."

---

## 4. Core User Journeys

### Journey 1: First-Time Setup
1. User signs up with email/password
2. User sets their primary currency
3. User creates 3-5 spending categories (app suggests defaults: Food, Transport, Entertainment, Shopping, Bills)
4. User optionally sets monthly budget amounts per category
5. User lands on empty dashboard, prompted to add first transaction

### Journey 2: Adding a Transaction
1. User taps "Add Transaction" button
2. User enters amount
3. User selects category from their list
4. User optionally adds a note
5. User confirms; transaction appears in list and updates dashboard totals

### Journey 3: Reviewing Spending
1. User opens app and sees current month's spending summary on dashboard
2. User sees progress bars showing budget usage per category
3. User taps a category to see transaction list for that category
4. User can filter by date range (this week, this month, custom)

### Journey 4: Receiving a Nudge
1. User's spending in a category reaches 80% of budget
2. App displays in-app notification: "Heads up: You've used 80% of your Dining budget with 10 days left in the month"
3. User acknowledges notification
4. If user exceeds budget, app shows a different message: "You've exceeded your Dining budget by $45"

### Journey 5: Adjusting a Budget
1. User navigates to Settings > Budgets
2. User sees list of categories with current budget amounts
3. User taps a category and adjusts the monthly limit
4. Change takes effect immediately for current month

### Journey 6: Monthly Reflection
1. At month's end, user opens the app and sees a simple prompt: "How did this month feel?"
2. User views a one-screen summary: total spent, top 3 categories, and any budgets exceeded
3. User is asked: "Any budgets you'd like to adjust for next month?"
4. User can tap to adjust budgets directly from this screen, or dismiss
5. Reflection is available but not forced—user can skip or return later

---

## 5. Functional Requirements (MVP)

### Authentication
- FR-1: Users can sign up with email and password
- FR-2: Users can log in and log out
- FR-3: Users can reset their password via email

### User Profile
- FR-4: Users can set their display name
- FR-5: Users can select their currency (set once during onboarding, changeable in settings)

### Categories
- FR-6: App provides default categories on signup (Food, Transport, Entertainment, Shopping, Bills, Other)
- FR-7: Users can create custom categories
- FR-8: Users can rename categories
- FR-9: Users can delete categories (transactions reassigned to "Other")
- FR-10: Users can set a monthly budget amount per category (optional)

### Transactions
- FR-11: Users can add a transaction with: amount, category, date, optional note
- FR-12: Users can edit a transaction
- FR-13: Users can delete a transaction
- FR-14: Transactions default to today's date
- FR-15: Users can view transactions filtered by category
- FR-16: Users can view transactions filtered by date range

### Dashboard
- FR-17: Dashboard shows total spending for current month
- FR-18: Dashboard shows spending per category for current month
- FR-19: Dashboard shows budget progress bars for categories with budgets set
- FR-20: Dashboard updates in real-time as transactions are added

### Nudges
- FR-21: App displays in-app notification when category spending reaches 80% of budget
- FR-22: App displays in-app notification when category budget is exceeded
- FR-23: Nudges appear once per threshold per category per month (not repeated)

### Monthly Reflection
- FR-24: App shows a monthly reflection prompt after the last day of each month
- FR-25: Reflection screen displays: total spent, top 3 spending categories, budgets exceeded
- FR-26: User can adjust budgets directly from the reflection screen
- FR-27: Reflection is optional—user can dismiss or access later from dashboard

### Data
- FR-28: All user data persists across sessions
- FR-29: Users can only see their own data

---

## 6. Future Expansion (Post-MVP)

These features are explicitly out of scope for MVP but represent logical next steps:

- **Recurring transactions:** Auto-create transactions for regular bills
- **Bank sync:** Connect to financial institutions via Plaid or similar
- **Reports:** Monthly/yearly spending reports with trends
- **Export:** Download transactions as CSV
- **Multiple budgets:** Different budget amounts for different months
- **Savings goals:** Track progress toward specific financial targets
- **Email nudges:** Send budget warnings via email, not just in-app
- **Mobile apps:** Native iOS and Android applications
- **Multi-currency:** Support users who spend in multiple currencies
- **Shared accounts:** Family or partner budgeting

---

## 7. Success Metrics

### Activation
- **Target:** 60% of signups complete onboarding (create at least 1 category and 1 transaction)
- **Measurement:** Funnel tracking from signup to first transaction

### Engagement
- **Target:** Active users add at least 5 transactions per week
- **Measurement:** Weekly transaction count per user

### Retention
- **Target:** 40% of users return in week 2 after signup
- **Measurement:** Cohort retention analysis

### Core Value Delivery
- **Target:** 50% of users with budgets set receive at least one nudge per month
- **Measurement:** Nudge trigger rate among budgeted users

### Budget Adherence
- **Target:** Users who receive 80% nudges exceed their budget 20% less often than users who don't see nudges
- **Measurement:** A/B comparison of budget outcomes with/without nudge visibility

---

## Appendix: Open Questions (Resolved via Assumptions)

| Question | Assumption Made |
|----------|-----------------|
| Should we support bank sync? | No - manual entry only for MVP |
| Multi-currency? | No - single currency per account |
| Mobile apps? | No - web only for MVP |
| Shared accounts? | No - single user only |
| How aggressive should nudges be? | Conservative - in-app only, once per threshold |
