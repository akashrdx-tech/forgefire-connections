# Copy "connection-forge-spark" repository into this project

## Goal
Replicate the cloned GitHub repository (a disguised chat app with a Shopify-research front page, hidden `/unlock` gate, auth, and chat room) into the current TanStack Start project.

## Scope
- Copy application source: `src/components`, `src/routes`, `src/hooks`, `src/lib`, `src/integrations`, `src/assets`, and supporting files.
- Replace design system and root layout with the copied `src/styles.css` and `src/routes/__root.tsx`.
- Merge/update `package.json` and `vite.config.ts` to match the source project's dependencies and build setup.
- Copy public assets (`favicon.ico`, `favicon.png`, `logo.png`).
- Copy Supabase migration files from `supabase/migrations` into this project.
- Enable Lovable Cloud so the required Supabase backend (auth, tables, storage, realtime) is provisioned for this project.
- Apply the copied migrations to the new Lovable Cloud project.
- Skip copying source `.env`, `.lovable/project.json`, and `.git` history; keep this project's identity and let Lovable Cloud inject fresh credentials.

## Verification
- Run the dev build/typecheck after file copy and dependency install.
- Open the preview and confirm the keyword-research landing page renders.
- Spot-check `/unlock` route exists and `/auth` route is reachable after passing the gate.

## Notes
- The access key for the hidden gate is hardcoded as `rdxsardarrdx@11` in `src/lib/gate.functions.ts`; this will be preserved.
- The original project uses Supabase RLS, realtime, and storage buckets; these are recreated through migrations once Lovable Cloud is active.
