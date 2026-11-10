# CAMPVERSE

**Every Campus. One Universe.** A student social web starter for participating Nigerian private universities.

## Run locally on Windows

Requirements: Node.js 24+ (built-in SQLite). Docker Desktop is needed only for PostgreSQL.

1. In the project folder run `npm install`.
2. Open two PowerShell windows in the folder. Run `npm run api:dev` in one and `npm run dev` in the other.
3. Open the Vite address, usually http://localhost:5173.

The local API creates `server/data/campverse-dev.sqlite` automatically. Accounts, profiles, text posts, comments, follows, likes, reports and notifications persist locally. No API packages, Docker or external credentials are needed for local development.

For PostgreSQL setup, copy `.env.example` to `.env` and `server/.env.example` to `server/.env`, set fresh local secrets, start Docker Desktop, run `npm run db:up`, then install server dependencies with `npm --prefix server install`. The schema loads when the database volume is created for the first time.

## Current status

- Responsive web app with sample feed, registration/login, post composer, comments, follow/unfollow, profile view/edit and notifications.
- Local API with SQLite, scrypt password hashes, signed JWT sessions, accounts, social features, health check and request limits.
- PostgreSQL API starter and schema for universities, profiles, verification, social content, messages, calls, live rooms, gifts, wallet ledger and moderation.
- Not implemented: email/admission verification workflows, admin UI, real media storage, real-time chat, interactive stories, calls, live streaming, payments/gifts, native apps and production deployment.

Local mode is for development. Use sample content only for demos. Do not commit `.env` files or real student data. Production needs secure sessions, verification, private media storage, migrations, backups, monitoring and external provider setup. Payments and creator payouts are not enabled.

Latest source bundle: `campverse-source-v2.zip`.
