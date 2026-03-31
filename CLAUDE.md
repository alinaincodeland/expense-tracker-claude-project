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

This is a single-component React app (Vite + React 19). All logic lives in `src/App.jsx`:

- **State**: `transactions` array (seeded with hardcoded data), plus form fields (`description`, `amount`, `type`, `category`) and filter fields (`filterType`, `filterCategory`).
- **Known bug**: `amount` is stored as a string in state. The `totalIncome`/`totalExpenses` reducers use `+` on string values, causing string concatenation instead of numeric addition.
- **No routing, no backend, no persistence** — state resets on page reload.
