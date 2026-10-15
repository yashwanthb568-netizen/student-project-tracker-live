# Student Project Tracker — Cloud Variant

This is a hands-on web app development workshop project. This cloud variant uses **Vercel** for hosting and **Supabase PostgreSQL** for shared project records.

## Local rehearsal

Requirements: Node.js 22.x and Git.

1. In PowerShell, open the project folder.
2. Install dependencies:

   ```powershell
   npm.cmd ci
   ```

3. Create a private `.env` file from `.env.example` and set `DATABASE_URL` to your Supabase PostgreSQL transaction-pooler URI. Keep `.env` private and never commit it.

   ```powershell
   Copy-Item .env.example .env
   ```

4. Start the local server:

   ```powershell
   npm.cmd start
   ```

5. Open <http://localhost:3000>. The health endpoint is <http://localhost:3000/api/health>.

## Database setup

- `schema.sql` creates the `public.projects` table in Supabase.
- `DATABASE_URL` is server-only. Do not put the database connection URI or database password in browser code or commit them to the repository.
- The app has shared demo records and no sign-in. Anyone who can access the hosted app may be able to view or change the shared records; do not use private or sensitive data.
- Local SQLite rows are not migrated to Supabase. The cloud variant uses the PostgreSQL database configured through `DATABASE_URL`.

## Deployment

The hosted URL will be added here after deployment.

## Verification notes

Checks completed during local rehearsal:
- The local health endpoint returned `ok true`.
- A `Cloud Test` project was created through the app and appeared in Supabase `public.projects`.
- The `Cloud Test` status was changed to `Completed`, and the matching row was visible in Supabase.

Deletion-cancellation behavior, confirmed deletion, and persistence after stopping and restarting the server have not yet been recorded as verified.
