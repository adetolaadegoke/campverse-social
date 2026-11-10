# CAMPVERSE

**Every Campus. One Universe.** A student social web starter for participating Nigerian private universities.

## Run locally on Windows

Requirements: Node.js 24+ for the built-in SQLite development API. Docker Desktop is only needed for the PostgreSQL setup.

1. In the project folder run:

   ```powershell
   npm install
   ```

2. Open two PowerShell windows in the project folder. Run `npm run api:dev` in one and `npm run dev` in the other.
3. Open the Vite address, usually `http://localhost:5173`.

The local API uses Node's built-in SQLite module and creates `server/data/campverse-dev.sqlite` automatically. Accounts and text posts persist locally; no API npm packages, Docker, or external credentials are needed for this development mode. This mode is for local development only.

To switch to PostgreSQL, copy `.env.example` to `.env` and `server/.env.example` to `server/.env`, set fresh local secrets, start Docker Desktop, then run `npm run db:up` and install the Express API dependencies with `npm --prefix server install`. The PostgreSQL schema loads when the database volume is first created.

The database schema in `db/schema.sql` is applied automatically when Docker creates the PostgreSQL volume the first time. To reset a local development database, stop the stack with `npm run db:down`; use `docker compose down -v` only when you intend to erase all local database data.

## Current status

- **Web app:** responsive CAMPVERSE UI, sample feed, navigation, stories rail, compose flow, registration and login forms.
- **Local API:** Node's built-in HTTP and SQLite modules with scrypt password hashes, signed JWT sessions, registration/login, post feed, text-post creation, likes, reports, health check and request limits.
- **PostgreSQL API:** Express/PostgreSQL starter in `server/src/index.js`, prepared for the schema and protected verification queue route.
- **Database:** initial PostgreSQL schema for universities, profiles, verifications, posts, social graph, stories, messages, calls, live rooms, gifts, wallet ledger, notifications and moderation.
- **Persistence:** real accounts and posts work only after PostgreSQL is running and the API is configured. Never use sample content as real student data.
- **Not implemented yet:** email verification, admission document upload/review actions, admin UI, university directory management, comments, real media upload, real-time chat, stories, calls, live streaming, payment and gifts, native Android/iOS apps, production deployment, and automated tests.

The frontend calls the API configured by `VITE_API_URL` (defaults to the local development API). The browser session stores the short-lived UI token in `sessionStorage`; production should move to a reviewed secure session design, add email verification, authorization tests, migrations, backups and monitoring.

## Safety and launch notes

Admission documents and media must use private object storage with short-lived signed access. Payment and creator payouts are not enabled; complete legal, provider and compliance review before considering real-money flows. Do not commit `.env` files or real student data. No external provider integration is represented as active.
