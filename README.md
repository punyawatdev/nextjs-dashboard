## Next.js App Router Course - Starter

This is the starter template for the Next.js App Router Course. It contains the starting code for the dashboard application.

For more information, see the [course curriculum](https://nextjs.org/learn) on the Next.js Website.


### Key technologies

- Next.js (App Router)
- React
- TypeScript
- Tailwind CSS
- Auth.js / NextAuth (routing & middleware example)

### Getting started (short)

1. Install dependencies (pnpm):

```bash
pnpm install
```

2. Create a `.env.local` (see below) and ensure Postgres is running locally (or set `POSTGRES_URL` to a reachable DB).

3. (Optional) Seed the database with a demo user (see "Seeding the database" section).

4. Run the dev server:

```bash
pnpm dev
```

5. Open http://localhost:3000 in your browser.

### Environment variables (.env.local)

Create a `.env.local` file in the project root. The app expects at minimum a Postgres connection and an auth secret for NextAuth.

Example `.env.example` (copy & edit):

Copy from .env.local on the Vercel dashboard:
https://nextjs.org/learn/dashboard-app/setting-up-your-database#create-a-postgres-database

```
POSTGRES_URL=
POSTGRES_PRISMA_URL=
POSTGRES_URL_NON_POOLING=
POSTGRES_USER=
POSTGRES_HOST=
POSTGRES_PASSWORD=
POSTGRES_DATABASE=

AUTH_SECRET=your-very-secure-random-string
NEXTAUTH_URL=http://localhost:3000
```

- `AUTH_SECRET` (or `NEXTAUTH_SECRET`) — required in production; used by Auth.js / NextAuth to sign/encrypt tokens/cookies. Use a long random string.
- `NEXTAUTH_URL` (or `AUTH_URL`) — the base URL for your app. Helpful to set in dev when behind proxies.

Generate a secure random secret on macOS (zsh):

```bash
# append a 48-byte base64 secret to .env.local
echo "AUTH_SECRET=$(openssl rand -base64 48)" >> .env.local
```

### Seeding the database (demo user)

Go to `http://localhost:3000/seed` and get message `Database seeded successfully` is successfully:
Default demo credentials created by the seed script (if you don't override):

- Email: user@nextmail.com
- Password: 123456

Available scripts

- `pnpm dev` — start Next.js in development mode
- `pnpm build` — build the app for production
- `pnpm start` — run the production server

### Project structure (important files)

- `app/` — App Router routes and layouts
  - `app/layout.tsx` — Root layout
  - `app/page.tsx` — Home page
  - `app/dashboard/` — Dashboard routes and nested layouts

- `ui/` — Reusable UI components (buttons, nav, tables, forms, etc.)
- `lib/` — Shared utilities, types, and placeholder data
- `auth.config.ts` — NextAuth configuration and route authorization callbacks
- `auth.ts` — authentication entry (uses Credentials provider + Postgres)
- `middleware.ts` — middleware wiring for auth