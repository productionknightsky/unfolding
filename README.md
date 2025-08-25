# Unfolding

A playful, social self‑reflection app. Users post a problem/pattern/solution and get suggestions. Others can react (❤️/👍/😐), comment, and report. Authors can edit their post for 30 minutes, and delete anytime. Engagement awards fun “récompenses” (badges).

## Quick start

```bash
# in the project root (Unfolding/)
npm run install-all

# development: runs server (http://localhost:5000) and client (http://localhost:5173)
npm start
```

If you prefer manually:
```bash
cd server && npm install && npm start
# in a second terminal
cd client && npm install && npm run dev
```

### Server
- Node + Express, JSON file storage in `server/data/db.json`.
- Enforces: only author can delete; only author can edit; edits allowed within 30 minutes of creation.
- Reports hide posts once report count ≥ 3 (still visible when opening a post directly).

### Client
- React + Vite + Tailwind.
- Local “profile”: a one‑time username prompt saved to `localStorage`. A random userId is created and used for actions.
- “Suggestions” appear while you type; more are returned from the server after submit.

### Environment
- Client expects `VITE_API_URL` (defaults to `http://localhost:5000`).
- Server listens on `PORT` (defaults to `5000`).

## Scripts
- `npm run install-all` – installs client + server deps.
- `npm start` – concurrently starts both.

## Notes
- This demo uses file‑based JSON storage. For production, plug in a real DB and auth provider.
- The rewards system is illustrative only.
