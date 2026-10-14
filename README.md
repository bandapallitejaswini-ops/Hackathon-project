# EDUWALLET — The Smart Student Finance & Budget Planner
> *"Your money. Your goals. Your future."*

EDUWALLET is a college hackathon-ready personal finance and budgeting web platform engineered specifically for students managing limited pocket money, allowances, part-time earnings, and scholarships.

Built entirely with standard **HTML5**, **CSS3**, and **Vanilla JavaScript**, EDUWALLET runs 100% offline in any modern web browser with **zero external backend, zero API keys, zero paid services, and zero framework overhead**. All transaction ledgers, monthly category budgets, savings milestones, and planned purchase reflections persist reliably in browser `localStorage`.

---

## 🌟 Key Features & Architecture

### 1. Interactive Onboarding & Demo Presentation Mode
* **Instant Start:** First-time students configure their nickname, starting monthly allowance, primary income source, preferred currency (₹ INR, $ USD, € EUR, £ GBP, etc.), savings target, and living accommodation (Hostel, Home, PG, Rented).
* **One-Click Hackathon Demo Mode:** Evaluators can instantly populate realistic student records for **"Alex"** (hostel dues, canteen chai/samosa, coding mentorship stipends, textbook purchases, 3 savings goals, category budgets, and previous month comparison records).

### 2. High-Visibility Student Dashboard
* **6 Key Financial Metrics:** Real-time Available Balance, Monthly Income, Expenses This Month, Remaining Monthly Budget, Total Goal Savings, and the Daily Spend Guide allowance.
* **Pure SVG Interactive Donut Chart:** Responsive category expense breakdown with center totals and color pills.
* **Daily Spending Timeline:** Native SVG bar chart visualizing spending velocity across days 1–31 of the selected month.
* **Dynamic Budget Warnings:** Automatic banners warning students when categories reach `75%` (Approaching Limit), `90%` (Nearly Exhausted), or `>100%` (Over Budget).
* **Student Financial Tip of the Day:** Curated rotation of practical hostel hacks, student software discounts (GitHub Student Pack, Spotify 50% SheerID discount), and impulse control tactics with an on-demand shuffle button.

### 3. Transaction Manager
* **Full CRUD Lifecycle:** Add, view, edit, and delete transactions with inline validation (positive numbers, ISO dates, category selectors).
* **Smart Filtering & Search:** Real-time debounced text search across descriptions and notes, type filter (Income / Expense), category filter, and customizable date range bounds.
* **Sorting Engine:** Instant sorting by Newest First, Oldest First, Highest Amount, and Lowest Amount.
* **Dual Layout:** Responsive data table for desktops and compact touch-friendly cards for mobile displays.

### 4. Smart Monthly Budget Planner
* **Category Allocations:** Allocate spending limits to individual student categories (Food & Snacks, Hostel & Rent, Transportation, Books & Stationery, Recharges, Shopping, Entertainment, Health).
* **Visual Progress Bars:** Color-shifting progress bars indicating healthy spending (Green), caution (Amber), and over-budget states (Coral Red).
* **Unallocated Safety Buffer:** Automatically tracks the margin between total monthly budget and allocated category limits to preserve emergency cash.

### 5. Student Savings Goals
* **Milestone Planning:** Set targets for essentials like a Laptop Fund, College Trip, Tech Gadgets, or an Emergency Buffer.
* **Deposit Workflows:** One-click contribution modal with deposit notes and visual milestone progress rings.
* **Celebration Badge:** Unlocks when a goal achieves 100% completion.
* **Educational Clarification:** Clearly documented as a motivational tracking ledger, ensuring students know money has not moved to an external banking server.

### 6. Daily Spend Guide (Indicative Pacing)
* **Mathematical Formula:** $\text{Indicative Daily Allowance} = \frac{\text{Remaining Monthly Budget}}{\text{Remaining Days in Current Month}}$.
* **Dynamic Status:** Instantly flags whether today's recorded spending is safe or exceeding today's recommended pace.
* **Zero Denominator & Deficit Safety:** Gracefully handles month-end zero days and displays an alert if the budget is exhausted.
* **Interactive "What-If" Simulator:** Lets students input an impending purchase to see how it will lower their daily allowance for the rest of the month.

### 7. "Need or Want?" Purchase Analyzer
* **Impulse Shield:** Evaluates planned purchases before checkout.
* **4-Point Reflection Rubric:** Urgency check, sharing/borrowing feasibility, savings impact, and 24-hour cooling-off rule.
* **Rule-Based Decision Engine:** Evaluates price against remaining monthly budget and days left, outputting an **Impulse Quotient Score (0–100)**, verdict badge, and actionable guidance.
* **Planned Wishlist:** Allows saving items to a waitlist or directly converting them into active expenses.

### 8. Allowance & Income Planner
* **Expected vs. Received:** Schedule future pocket money, scholarships, or internship stipends.
* **Strict Double-Counting Protection:** Expected income is purely an informative schedule and does **not** artificially inflate available cash. Clicking *"Mark Received"* safely creates a single ledger transaction and updates balances.

### 9. Student Spending Insights
* **Data-Backed Observations:** Automated observations generated only from real saved data (e.g., largest single expense, most frequent category, average daily burn rate, savings rate percentage).
* **Month-over-Month Analytics:** Side-by-side comparative bars illustrating category spending shifts compared to the previous month.

### 10. Financial Learning Corner & Quiz
* **6 Bite-Sized Lessons:** Adapted 50-30-20 rule, ₹2,000 college emergency buffer, 24-hour rule, subscription creep, and balance vs. income clarification.
* **Interactive 5-Question Quiz:** Instant educational rationale feedback, score tracker, and local completion badges ("Smart Student Planner", "Financial Sensei").

### 11. Reports, RFC 4180 CSV Export & Print
* **Financial Statement:** Monthly summary of income, expenses, net cash flow, and category breakdowns.
* **Clean CSV Export:** RFC 4180-compliant comma/quote escaping generated via a client-side Blob download.
* **Print-Specific Stylesheet (`@media print`):** Formats cleanly for printer or "Save as PDF" by hiding navigation bars and modals.

### 12. Settings & Offline Data Management
* **Profile Customization:** Modify nickname, monthly budget, savings target, and living accommodation.
* **Currency Selector:** Support for INR (₹), USD ($), EUR (€), GBP (£), CAD (CA$), AUD (A$), and JPY (¥).
* **Theme Toggle:** Crisp Light Mode (Mint & Forest Green) and sleek Dark Mode (Deep Slate & Emerald).
* **JSON Backup & Restore:** Export complete state as a formatted JSON file and restore it on any device with schema validation.
* **2-Step Safe Data Wipe:** Full reset option with confirmation modal.

---

## 📁 File Structure

```
EDU WALLET/
├── index.html              # Main application shell with semantic views and modals
├── css/
│   └── styles.css          # Brand styles, CSS variables, dark mode, responsive & print styles
├── js/
│   ├── storage.js          # localStorage state manager, schema validation, demo dataset
│   ├── calculations.js     # Currency formatting, financial formulas, date math, threshold logic
│   ├── charts.js           # Pure SVG chart generators (Donut, Bar chart, Comparison, Progress rings)
│   ├── transactions.js     # Transaction CRUD, search, multi-faceted filtering, sorting
│   ├── budgets.js          # Monthly and category budget manager with threshold warnings
│   ├── goals.js            # Savings goals, contributions, and milestone celebrations
│   ├── daily-spend.js      # Indicative daily spending allowance and "What-If" simulator
│   ├── need-want.js        # Impulse control evaluator and planned purchase wishlist
│   ├── income-planner.js   # Expected vs Received schedule (zero double-counting)
│   ├── insights.js         # Spending habits, month-over-month comparisons, automated tips
│   ├── learn.js            # Bite-sized literacy modules and interactive quiz engine
│   ├── reports.js          # Statement generation, RFC 4180 CSV generator, print styles
│   ├── settings.js         # User preferences, theme switch, JSON backup/import/wipe
│   └── app.js              # SPA router, header state, onboarding, toast notifications
├── test_runner.html        # Automated unit and integration test suite (10/10 tests)
└── README.md               # Hackathon presentation and technical documentation
```

---

## 🚀 How to Run Locally

Because EDUWALLET uses standard web technologies with no compilation, no node modules, and no backend dependencies, running it is instantaneous:

### Option 1: Direct Browser Launch (Simplest)
1. Double-click `index.html` in Windows File Explorer, or
2. Right-click `index.html` → **Open with** → **Google Chrome** (or Edge / Firefox / Safari).

### Option 2: Local HTTP Server (Optional)
If you prefer running through a local web server:
* Using Python:
  ```bash
  python -m http.server 8000
  ```
  Open `http://localhost:8000` in your browser.

---

## 🏆 How to Demonstrate at a College Hackathon

1. **The Hook (First 30 seconds):**
   * Open `index.html`. Point out the welcoming Onboarding Modal designed specifically for students.
   * Click **"⚡ Load Demo Student Data (Alex)"** to instantly hydrate the application with a realistic dataset (₹8,000 allowance, hostel rent, mess food, Jio recharge, coding tutor stipend).

2. **The Dashboard & Pacing (1 Minute):**
   * Show the 6 summary metric cards computed dynamically from actual data.
   * Highlight the **Daily Spend Guide** metric ($₹197.89/\text{day}$). Explain how it prevents students from running out of money before the month ends.
   * Show the pure SVG **Daily Spending Timeline** and **Category Breakdown Donut Chart**.
   * Point to the dynamic **Budget Watch** banner warning that Hostel & Rent has reached 92% of its cap.

3. **Core Features Tour (2 Minutes):**
   * **Transactions:** Demonstrate searching for `"canteen"`, filtering by category or date, and adding a quick spend using the `+ Add Spend` button.
   * **Budgets:** Open `#budgets` to show the threshold color-coded badges (`<75%` Green, `75–90%` Amber, `90–100%` Warning, `>100%` Coral Red).
   * **Savings Goals:** Open `#goals` and click **"Contribute"** on the *M3 MacBook Air Fund*. Show how progress instantly updates.
   * **Need or Want?:** Open `#need-want`. Input an impulse item (e.g. ₹2,000 branded shoes). Fill out the 4-question checklist and click **"Analyze Decision"** to demonstrate the rule-based Impulse Quotient Score and advisory warning.
   * **Income Planner:** Open `#income-planner`. Point out how "Expected" scholarship money is kept separate until marked "Received", preventing accidental overspending.
   * **Learn & Quiz:** Open `#learn`. Show the bite-sized lessons and click through the interactive quiz with immediate rationale feedback.
   * **Reports:** Open `#reports`. Click **"Download CSV"** to demonstrate client-side RFC 4180 export.

4. **Finishing Touch (15 seconds):**
   * Click the Moon icon in the top header to toggle **Dark Mode**.
   * Open Settings to demonstrate the **Export JSON Backup** feature.

---

## 💾 How Local Data is Stored

EDUWALLET stores all data under specific, isolated keys inside the browser's `window.localStorage`:
* `eduwallet_profile`: User nickname, currency preference, monthly budget, savings targets, theme.
* `eduwallet_transactions`: Array of recorded income and expense ledger entries.
* `eduwallet_budgets`: Overall monthly ceiling and category limit allocations.
* `eduwallet_goals`: Savings targets, accumulated balances, deadlines, and deposit history.
* `eduwallet_planned_purchases`: Wishlist items assessed through the Need vs. Want engine.
* `eduwallet_income_schedule`: Expected vs. received allowance dates and transaction links.
* `eduwallet_learn_progress`: Completed reading modules and quiz high scores.

*Note on Privacy:* All financial entries remain strictly on the local machine. No tracking beacons, analytics scripts, or cookies are dispatched to any external server.

---

## 🧪 Automated Test Suite

An automated test suite is included in `test_runner.html`. To run the tests:
1. Open `test_runner.html` in your browser.
2. Review the verified test cases:
   - ✅ Demo Data Generation & Profile Persistence
   - ✅ Financial Balance & Month Summary Calculations
   - ✅ Currency Formatter `Intl.NumberFormat`
   - ✅ Budget Threshold Evaluator (`<75%`, `75-90%`, `90-100%`, `>100%`)
   - ✅ Daily Spend Guide Calculation & Zero-Denominator Safety
   - ✅ Savings Goals CRUD & Contribution Logic
   - ✅ Income Schedule "Mark Received" & Double-Counting Prevention
   - ✅ Need vs. Want Decision Engine Scoring
   - ✅ JSON Backup & Import Validation
   - ✅ Month-over-Month Comparison Engine

---

## ⚠️ Known Limitations & Educational Scope

1. **Browser Isolation:** Because storage relies on `localStorage`, clearing browser cache/history removes local records unless backed up via Settings → Export JSON.
2. **Device Scope:** Transactions recorded on one laptop/phone do not synchronize across devices automatically without importing a JSON backup.
3. **Non-Banking Software:** EDUWALLET is a personal budgeting and behavioral literacy tool. It does not interface with actual UPI bank accounts, credit bureaus, or payment gateways.
