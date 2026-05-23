# Agent instructions

## Cursor Cloud specific instructions

- Use the `HDDS-9225-website-v2` branch as the development base for Apache Ozone Website v2. This branch is the Docusaurus source site; do not use the rendered legacy `asf-site` branch for Website v2 development.
- Dependency refresh is pnpm-based. The startup update script should activate `pnpm@9.12.3` with Corepack and run `pnpm install --frozen-lockfile` from the repository root.
- The main local service is the Docusaurus development server on port 3001. `CONTRIBUTING.md` documents the standard Docker and pnpm preview options; in Cursor Cloud, `pnpm start --host 0.0.0.0` works for the local dev server.
- Run Website v2 static checks with the scripts in `.github/scripts/` and use `pnpm build` for the production build. If `pnpm build` runs while `pnpm start` is watching the same tree, the dev server can report transient service-worker theme resolution errors; stop it, run `pnpm clear`, and restart `pnpm start --host 0.0.0.0`.
