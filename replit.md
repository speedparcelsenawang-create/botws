# ScheduleBot

WhatsApp scheduled-message bot with a web dashboard (imported project).

## Tech Stack
- Node.js + Express, EJS views
- WhatsApp connection via `atexovi-baileys`
- Schedule storage: PostgreSQL (via `DATABASE_URL`), falls back to in-memory if unset

## Running on Replit
- `npm start` runs `node src/server.js`, bound to `0.0.0.0:5000` (the "Start application" workflow does this).
- Uses Replit's built-in PostgreSQL database automatically via the `DATABASE_URL` env var provided by the environment — no manual secret setup was needed.
- `PORT`, `TZ`, `DEFAULT_DIAL_CODE` are set as shared env vars in `.replit`.
- To link a WhatsApp account, open the dashboard's Account page and scan the QR/pairing code — until then the dashboard shows "Offline" and some API calls return 409, which is expected pre-connection.

## Notes
- The imported `.env.example` contained a live-looking Neon Postgres connection string. It was left untouched but is not used — the app connects to Replit's own Postgres instead. Treat that credential as compromised if it was ever real.

## User preferences
None recorded yet.
