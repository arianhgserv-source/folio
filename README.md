![Banner Social Image](https://i.imgur.com/D1PRVtF.png)

<h1 align="center">Folio — hLedger Reader</h1>
<p align="center"><b>Folio</b> is a zero-install, single-file financial dashboard for <a href="https://hledger.org/">hLedger</a> plain-text accounting files. Drop in your <code>.ledger</code> file and instantly explore your finances through interactive charts, tables, and a daily calendar — all running entirely inside your browser. Nothing is ever uploaded to a server.</p>

<h3 align="center"><a href="https://arianhgserv-source.github.io/folio/">Use Folio</a> • <a href="https://github.com/arianhgserv-source/folio#features">Features</a> • <a href="https://github.com/arianhgserv-source/folio#getting-started"> Getting Started</a> • <a href=https://github.com/arianhgserv-source/folio#privacy">Privacy</a> </h3> 

---
## Description
Folio turns a plain `.ledger` journal into a rich, navigable financial dashboard in one click. It parses your file locally using JavaScript, so your data never leaves your machine. There's no backend, no accounts, no installation — just open `index.html` (or visit the GitHub Pages URL) and drag in your file.

It's designed for people who already use hLedger or Ledger CLI to track their money but want a visual layer on top without setting up a full reporting stack.

---
## Features
### 📊 Income Statement
View total income, total expenses, net income, and savings rate for any period. A donut chart shows the income/expense split at a glance, and a bar chart ranks your top expense categories. A scrollable **period matrix** breaks every account down by sub-period (daily, weekly, or monthly depending on your selected range) so you can spot trends across time.

![Income Statement](https://i.imgur.com/CsveqTU.png)

 ### 💧 Cash Flow

Track money in vs. money out over time with a combined bar + line chart. Use the **account drill-down** to focus on any single account — the chart switches to show that account's net change per sub-period alongside a running balance line, with open/close balance stats in the cards above.

![Cash Flow](https://i.imgur.com/VeGStV2.png)
### 💰 Net Worth Over Time

A full-history line chart of assets, liabilities, and net worth — always showing the complete picture regardless of the period filter. Stat cards surface current net worth, total assets, total liabilities, and period-over-period change.

![Net Worth Tracker](https://i.imgur.com/FWWDpct.png)

### 🌊 Money Flow (Sankey)

An interactive SVG Sankey diagram tracing money from income sources through a central "Budget" node out to individual expense accounts. Hover any ribbon or node to see a tooltip with the full account path, dollar amount, and percentage of total income. Non-hovered ribbons dim so you can follow a single flow. Expense accounts are color-coded by category (Housing, Food, Health, etc.) for quick visual grouping.

![Money Flow](https://i.imgur.com/GgclCJI.png)  

### 📅 Calendar View

A month-grid or week-grid view of daily financial activity. Each day cell shows a net-worth change chip (green/red) plus asset and liability deltas. Click any day to expand a drawer with detailed stat cards and a full transaction list for that date. The **week view** shows individual transaction descriptions directly in each day cell. The calendar has its own navigation controls and is completely independent of the global period filter.

![Calendar View](https://i.imgur.com/zTMaLgB.png)

### 🔍 Balance Lookup

Enter any date — past or future — to see exact account balances as of that moment. Dates before today show historical balances reconstructed from your journal. Dates after today show forward projections based on average spending patterns, clearly flagged with a projection warning banner. Jump presets (Today, End of Month, +1 Mo, +3 Mo, +6 Mo, +1 Yr) make it fast to check common scenarios.

![Balance Lookup](https://i.imgur.com/kFwKxP8.png)

### 📋 Account Ledger (Balances)

A full ledger of every account in the selected period with current balance, a color-coded gain/loss indicator, and a trend arrow. Click any account row to jump directly to the Transactions panel pre-filtered to that account.

![Account Ledgers](https://i.imgur.com/hQVqjoy.png)

### 📝 Transactions

The complete transaction log for the selected period. Filter to any account using the dropdown — matching postings are highlighted in indigo. A clear-filter button resets the view. The account filter also works as a destination for click-throughs from the Account Balances panel.

### 🎛️ Period Selector

Switch between **Week, Month, Quarter, Year**, and **All Time** views with a single click. Use the ‹ › arrows to step backward and forward. All panels update together.

### 📤 Export

- **PNG** — screenshots the active panel at 2× resolution using html2canvas

- **PDF** — opens the browser print dialog; choose "Save as PDF" for a clean printout
---

## Getting Started

**Quick Start:** You can use Folio by simply [visiting this link!](https://arianhgserv-source.github.io/folio/) Remember, this application runs entirely in your browser- your data never leaves your machine.

**Offline or Downloaded Files:** Just open `index.html` directly in any modern browser (Chrome, Firefox, Safari, Edge). No server required.

### Loading your data
- **Drag and drop** your `.ledger`, `.journal`, `.hledger`, or `.txt` file onto the upload area
- Or click the upload area to browse for the file
- Click **"No file? Try sample data →"** to explore with 16 months of generated transactions

![Landing Page](https://i.imgur.com/nKe1aD8.png)

---

## File Format Support

Folio parses standard hLedger / Ledger CLI plain-text journal format:

```ledger
2025-01-15 * Payroll
	Assets:Checking $5,800.00
	Income:Salary
2025-01-16 Rent
	Expenses:Housing:Rent $1,750.00
	Assets:Checking
```
Supported features: dated transactions, `*`/`!` status flags, multi-posting transactions, implicit balancing amounts, commodity/currency amounts (`$`, with or without commas).

---
## Privacy
Folio has no backend. Your `.ledger` file is read by JavaScript running in your browser tab and is never transmitted anywhere. Closing the tab discards everything. The only network requests made are to load Chart.js and html2canvas from a public CDN on first load.

---
## Tech Stack

| Layer | Library |
|---|---|
| Charts |  [Chart.js 4.4.1](https://www.chartjs.org/)  |
| PNG export |  [html2canvas 1.4.1](https://html2canvas.hertzen.com/)  |
| Sankey diagram | Hand-rolled SVG with Bézier ribbons |
| Everything else | Vanilla JS / CSS — no framework, no build step |
## License
MIT
