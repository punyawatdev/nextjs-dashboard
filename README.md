## Next.js App Router Course - Starter

This is the starter template for the Next.js App Router Course. It contains the starting code for the dashboard application.

For more information, see the [course curriculum](https://nextjs.org/learn) on the Next.js Website.


Key technologies

- Next.js (App Router)
- React
- TypeScript
- Tailwind CSS
- next-auth (routing & middleware example)

Quick links

- Docs: https://nextjs.org/docs
- Tailwind: https://tailwindcss.com/docs

Getting started

1. Install dependencies (this project uses pnpm):

   ```bash
   pnpm install
   ```

2. Run the development server:

   ```bash
   pnpm dev
   ```

3. Open http://localhost:3000 in your browser.

Available scripts

- pnpm dev — start Next.js in development mode (Turbopack enabled)
- pnpm build — build the app for production
- pnpm start — run the production server

Notes about environment and dependencies

- This starter pins Next.js to a canary release in package.json ("next": "16.0.0-canary.1"). You may want to upgrade to a stable release depending on your needs.
- Authentication wiring is present in `auth.config.ts` and `auth.ts`. Providers are left empty by default — add any NextAuth providers you want in `auth.config.ts`.
- The project includes `bcrypt` and `postgres` in dependencies as examples if you plan to add credential-based auth and a Postgres database.

Project structure (important files)

- `app/` — App Router routes and layouts
  - `app/layout.tsx` — Root layout
  - `app/page.tsx` — Home page
  - `app/dashboard/` — Dashboard routes and nested layouts

- `ui/` — Reusable UI components (buttons, nav, tables, forms, etc.)
- `lib/` — Shared utilities, types, and placeholder data
- `auth.config.ts` — NextAuth configuration and route authorization callbacks
- `middleware.ts` — Middleware used to protect routes (see auth config)

Authentication & demo credentials

This template contains authentication scaffolding but no pre-configured providers. If you want a quick local demo, add a simple credentials provider or a static check in `auth.ts`.

If this repository was seeded from the Next.js tutorial, it may expect a test username/password — check `auth.ts` or `lib/placeholder-data.ts` for any hard-coded demo users.

Deployment

- For production, build with `pnpm build` and run `pnpm start`.
- Host on Vercel for zero-config deployments. Make sure to set any environment variables (auth providers, secrets, DB connection strings) in your hosting provider.

## Example Username Login

For demonstration purposes, you can use the following credentials to log in locally:

- **Username:** `user@nextmail.com`
- **Password:** `123456`

These demo credentials are defined in the project for testing authentication flows.
