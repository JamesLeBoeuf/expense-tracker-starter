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

This is a React 19 + Vite app. The entire application lives in a single component: `src/App.jsx`.

**State**: All state is managed with `useState` in `App` — transactions list, form fields (description, amount, type, category), and filter state (filterType, filterCategory).

**Known intentional issues** (part of a course exercise):
- Transaction #4 ("Freelance Work") is typed as `"expense"` but categorized as `"salary"` — intentional data inconsistency.
- UI and code organization are intentionally messy for refactoring exercises.

No routing, no backend, no external state management — all data is ephemeral in-memory React state.
