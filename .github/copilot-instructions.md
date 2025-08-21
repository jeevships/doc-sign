````markdown
# GitHub Copilot Instructions

This document provides guidance for AI coding agents to be productive in this codebase.

## Project Overview

This is a modern web application built with the T3 stack, featuring:
- **Framework**: [Next.js 15](https://nextjs.org/) with App Router
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **UI**: [React 19](https://react.dev/), [Shadcn UI](https://ui.shadcn.com/), [Radix UI](https://www.radix-ui.com/), and [Tailwind CSS](https://tailwindcss.com/)
- **Backend & Auth**: [Supabase](https://supabase.com/)
- **Payments**: [Stripe](https://stripe.com/)
- **Forms**: [React Hook Form](https://react-hook-form.com/) with [Zod](https://zod.dev/) for validation

## Key Architectural Patterns

- **Server Components by Default**: Most components are React Server Components (RSCs) located in `src/app`. Client components are explicitly marked with `"use client"` and should be used sparingly.
- **UI Components**: Reusable UI components are in `src/components/ui`. These are based on Shadcn UI and should be the primary building blocks for any new UI.
- **Supabase Integration**: The Supabase client is managed via `src/lib/supabase`. Use the provided helpers for interacting with Supabase services.
- **Styling**: Styling is done with Tailwind CSS. Use `clsx` and `tailwind-merge` via the `cn` utility in `src/lib/utils.ts` for constructing dynamic class names.

## Developer Workflow

- **Getting Started**: Run `npm install` to install dependencies, then `npm run dev` to start the development server at `http://localhost:3000`.
- **Linting**: Run `npm run lint` to check for code style issues.
- **Component Scaffolding**: Use the Shadcn UI CLI to add new UI components.

## Code Conventions

- **File Structure**:
  - Pages and layouts are in `src/app`.
  - Reusable components are in `src/components`.
  - Custom hooks are in `src/hooks`.
  - Utility functions are in `src/lib`.
- **State Management**: For client-side state, prefer React's built-in hooks like `useState`, `useReducer`, and `useActionState`. For URL state, consider using a library like `nuqs`.
- **Forms**: Use `react-hook-form` for all forms, with `zod` for schema validation. Find examples in components that use forms.
- **API Routes**: API logic is handled within Server Components or in API routes in the `src/app/api` directory.

## Important Files

- `src/app/layout.tsx`: The root layout of the application.
- `src/lib/supabase/client.ts`: The client-side Supabase client.
- `src/lib/supabase/server.ts`: The server-side Supabase client.
- `src/lib/utils.ts`: Contains the `cn` utility function and other shared helpers.
- `tailwind.config.mjs`: The Tailwind CSS configuration.
````
