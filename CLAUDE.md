# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # Start dev server (Vite, default port 5173)
npm run build    # Production build
npm run lint     # Run ESLint
npm run preview  # Preview production build
```

No test suite is configured.

## Architecture

React 19 + Vite app with no routing, no backend, and no persistence — state resets on page reload.

**Component tree:**
- `App` — holds the `transactions` array in state (seeded with hardcoded data); passes it down and handles `onAdd`
  - `Summary` — receives `transactions`, computes `totalIncome`, `totalExpenses`, and `balance` internally
  - `TransactionForm` — owns its own form state (`description`, `amount`, `type`, `category`); calls `onAdd` prop with the new transaction object
  - `TransactionList` — receives `transactions`, owns filter state (`filterType`, `filterCategory`) internally
