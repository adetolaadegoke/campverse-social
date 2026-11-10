# CAMPVERSE

**Every Campus. One Universe.** A dark, gold-accented campus social product for students at participating Nigerian private universities.

## What is in this project

- Responsive Vite web app / installable PWA shell with an original campus feed, stories rail, trending cards and event card.
- Working client-side interactions for navigation, composing a text post, likes, saves and feedback messages. Demo posts are sample interface data and are not persisted.
- Express API starter with registration, login, public post listing, authenticated text-post creation, likes, reports, rate limiting and Helmet headers.
- PostgreSQL relational schema covering the main account, university, verification, social, messaging, calls, live, gift, wallet, notification and moderation entities.
- Environment variable examples and setup notes.

## Run the web app

Requires Node.js 20 or later.

```sh
npm install
npm run dev
```

## Run the API

Create a PostgreSQL database, then apply `db/schema.sql`. Copy `server/.env.example` to `server/.env`, set a long random `JWT_SECRET` and your `DATABASE_URL`, and configure `WEB_ORIGIN`.

```sh
cd server
npm install
npm run dev
```

The health endpoint is `GET /api/health`. Do not use sample content as real student data.

## Delivery status

| Area | Status |
| --- | --- |
| Responsive web interface / PWA manifest | Implemented as a runnable frontend shell; install behavior and cross-browser QA still need verification |
| Demo feed, navigation, composer, likes and saved feedback | Implemented in browser memory only; no persistence or media upload |
| API registration/login and text posts | Implemented as starter routes; requires configured PostgreSQL and production security review |
| PostgreSQL schema | Initial schema provided; migrations, row-level access policies and backup/restore procedures remain to be added |
| Email verification and admission document workflow | Awaiting email provider, private object storage and reviewer workflow |
| Admin dashboard and university management | Not implemented |
| Realtime messaging, stories, short-video upload, calls and live streaming | Not implemented; requires realtime and media providers |
| Wallet, Paystack, gifts, real-money payment or creator payouts | Not implemented; intentionally requires legal, compliance and provider review before launch |
| Native Android/iOS applications | Not implemented |
| Production deployment and automated test suite | Not configured or verified |

## Security notes

Admission documents and media should use private object storage and short-lived signed access. Never serve verification files from a public bucket. The API uses parameterized SQL, password hashing, JWT bearer tokens, Helmet and a basic IP rate limit; production deployment still needs email verification, refresh/session revocation, CSRF strategy for cookie auth, audit review, authorization tests, secret rotation, TLS, backups and monitoring. JWT secret and database credentials must remain outside source control.

## Before a real launch

Complete the unfinished features above, add migrations and automated tests, review Nigerian privacy and payment requirements, configure providers, perform security review, and test on supported mobile and desktop browsers. No external integration is represented as live in this starter.
