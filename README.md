# Next.js Dashboard App

A full-stack financial dashboard application built while following the official [Next.js Learn Course](https://nextjs.org/learn/dashboard-app). This project covers the App Router, data fetching, authentication, and more.

## Demo

The dashboard lets you view revenue charts, latest invoices, manage customers, and perform full CRUD operations on invoices — all backed by a PostgreSQL database.

## Tech Stack

- **Framework:** [Next.js](https://nextjs.org/) (App Router)
- **Language:** TypeScript
- **Styling:** Tailwind CSS
- **Database:** PostgreSQL (via [`postgres`](https://github.com/porsager/postgres) driver)
- **Authentication:** NextAuth.js v5 (beta)
- **Validation:** Zod
- **Package Manager:** pnpm

## Course Progress

### Completed (16/16 chapters) ✅

| #   | Chapter                         | Status |
| --- | ------------------------------- | ------ |
| 1   | Getting Started                 | ✅     |
| 2   | CSS Styling                     | ✅     |
| 3   | Optimizing Fonts and Images     | ✅     |
| 4   | Creating Layouts and Pages      | ✅     |
| 5   | Navigating Between Pages        | ✅     |
| 6   | Setting Up Your Database        | ✅     |
| 7   | Fetching Data                   | ✅     |
| 8   | Static and Dynamic Rendering    | ✅     |
| 9   | Streaming                       | ✅     |
| 10  | Partial Prerendering (Optional) | ✅     |
| 11  | Adding Search and Pagination    | ✅     |
| 12  | Mutating Data                   | ✅     |
| 13  | Handling Errors                 | ✅     |
| 14  | Improving Accessibility         | ✅     |
| 15  | Adding Authentication           | ✅     |
| 16  | Adding Metadata                 | ✅     |

## Key Concepts Covered

- **App Router** — File-based routing with layouts, pages, loading states, and error boundaries
- **Server Components** — Data fetching directly in components without client-side waterfalls
- **Server Actions** — Form handling and data mutations with `'use server'` functions
- **Streaming & Suspense** — Progressive UI rendering with `loading.tsx` and React Suspense
- **Search & Pagination** — URL search params for shareable/bookmarkable search state with debouncing
- **Database Queries** — Direct SQL queries to PostgreSQL with parameterized statements
- **Form Validation** — Schema-based validation using Zod
- **Error Handling** — `error.tsx` boundaries and `not-found.tsx` for graceful error recovery
- **Dynamic & Static Rendering** — Understanding when and how Next.js caches data
- **Cache Revalidation** — Using `revalidatePath` to keep data fresh after mutations
- **Accessibility** — `useActionState` for server-side form validation with `aria` attributes for accessible error messages
- **Authentication** — NextAuth.js with Credentials provider, middleware-based route protection, and bcrypt password hashing
- **Metadata** — Dynamic page titles with `metadata` exports and template-based title patterns

## Project Structure

```
app/
├── layout.tsx                  # Root layout
├── page.tsx                    # Home page
├── lib/
│   ├── actions.ts              # Server Actions (create, update, delete invoices)
│   ├── data.ts                 # Data fetching functions
│   ├── definitions.ts          # TypeScript type definitions
│   ├── placeholder-data.ts     # Seed data
│   └── utils.ts                # Utility functions
├── ui/                         # Reusable UI components
│   ├── dashboard/              # Dashboard-specific components
│   ├── invoices/               # Invoice CRUD components
│   └── customers/              # Customer table component
├── login/page.tsx              # Login page
├── dashboard/
│   ├── layout.tsx              # Dashboard layout with sidenav
│   ├── (overview)/             # Route group for dashboard overview
│   │   ├── page.tsx
│   │   └── loading.tsx         # Streaming skeleton
│   ├── invoices/
│   │   ├── page.tsx            # Invoices list with search & pagination
│   │   ├── create/page.tsx     # Create invoice form
│   │   ├── [id]/edit/page.tsx  # Edit invoice form
│   │   └── error.tsx           # Error boundary
│   └── customers/page.tsx
├── seed/route.ts               # Database seeding route
└── query/route.ts              # Database query route

auth.ts                         # NextAuth config with Credentials provider
auth.config.ts                  # Auth callbacks & route protection rules
middleware.ts                   # Middleware for authenticated route guarding
```

## Getting Started

### Prerequisites

- Node.js 18+
- pnpm
- A PostgreSQL database (e.g., [Vercel Postgres](https://vercel.com/docs/storage/vercel-postgres))

### Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/bhuvanpatle/nextjs-dashboard.git
   cd nextjs-dashboard
   ```

2. **Install dependencies**

   ```bash
   pnpm install
   ```

3. **Set up environment variables**

   Create a `.env` file in the root with your credentials:

   ```env
   POSTGRES_URL=your_postgres_connection_string
   AUTH_SECRET=your_auth_secret
   ```

4. **Seed the database**

   Visit `/seed` in the browser after starting the dev server to populate the database with placeholder data.

5. **Run the development server**

   ```bash
   pnpm dev
   ```

   Open [http://localhost:3000](http://localhost:3000) in your browser.

## Resources

- [Next.js Learn Course](https://nextjs.org/learn/dashboard-app)
- [Next.js Documentation](https://nextjs.org/docs)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [NextAuth.js Documentation](https://authjs.dev/)
