# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install      # Install dependencies
npm run dev      # Start dev server at http://localhost:5173
npm run build    # Production build
npm run lint     # Run ESLint
npm run preview  # Preview production build
```

## Architecture

This is a React 19 + Vite app with no routing, no backend, and no external state management — all data is ephemeral in-memory React state.

**Component tree:**
- `App` — holds the `transactions` array in state and passes it down; the only component that can add transactions
  - `Summary` — receives `transactions`, computes totalIncome/totalExpenses/balance internally
  - `TransactionForm` — owns its own form field state; calls `onAdd(transaction)` prop when submitted
  - `TransactionList` — receives `transactions`, owns filter state (filterType, filterCategory) internally

**Known intentional issue** (part of a course exercise):
- Transaction #4 ("Freelance Work") is typed as `"expense"` but categorized as `"salary"` — intentional data inconsistency.
