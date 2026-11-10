# CAMPVERSE

**Every Campus. One Universe.** A student social app concept for participating Nigerian universities.

## Try the public preview

[Open CAMPVERSE](https://adetolaadegoke.github.io/campverse-social/)

This is a public visual preview with sample content. Accounts and shared posts are not enabled on the hosted preview yet. Those features need a hosted API and database. Never enter a real password or private student information in a demo.

## Run the full local prototype

Requirements: Node.js 24+.

1. Download the latest source bundle: [campverse-source-v4.zip](https://github.com/adetolaadegoke/campverse-social/blob/main/campverse-source-v4.zip)
2. Extract it and open PowerShell in the extracted folder.
3. Run `npm install`.
4. In two PowerShell windows, run `npm run api:dev` and `npm run dev`.
5. Open http://localhost:5173.

The local API uses built-in SQLite and stores accounts, profiles, posts, comments, follows, likes, reports and notifications on that computer. It needs no external credentials.

## Current status

- Responsive CAMPVERSE web interface with sample campus feed, sign-up/sign-in, post composer, comments, follow/unfollow, editable profiles and notifications in the local prototype.
- Local Node API with SQLite, password hashing, signed sessions and rate limits.
- PostgreSQL API starter and schema for future deployment.
- Still to build and configure for a public production app: hosted persistent database/API, email verification, university approval/admin workflows, private media storage, real-time messaging, calls, live rooms and payments.

The Pages demo only renders sample content; authentication and shared interactions require the hosted backend. Payment, admission document uploads and creator payouts are not enabled. Do not commit secrets or real student data.
