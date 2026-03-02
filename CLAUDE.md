# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev      # Start development server at http://localhost:3000
npm run build    # Production build
npm run lint     # Run ESLint
npm run start    # Start production server
```

## Stack

- **Next.js 16** with App Router (`src/app/`)
- **React 19**
- **TypeScript**
- **Tailwind CSS v4** (PostCSS-based, no `tailwind.config.js`)

## Structure

All app code lives under `src/app/`. The entry point is `src/app/page.tsx`; `layout.tsx` wraps the entire app with global font and CSS setup. Global styles are in `src/app/globals.css`.

Path alias `@/*` maps to `src/*`.

## Authentication

Uses **Clerk** (`@clerk/nextjs`) for auth. `ClerkProvider` wraps the root layout; `clerkMiddleware()` in `src/middleware.ts` protects routes. The middleware is configured to skip Next.js internals and static files. Clerk keys are stored in `.env.local` (`NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`, `CLERK_SECRET_KEY`).

Use `SignedIn`/`SignedOut` components for conditional rendering based on auth state.
w