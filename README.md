# straight-dominos-2# Straight Domino — Frontend + Mock Server

This repo contains a React + Vite frontend and a lightweight Socket.io mock server so you can run the full UI locally without a real backend.

Features
- Double-6 domino set (mock server deals tiles)
- Up to 4 players (teams not enforced in mock)
- No-draw pass rule (players pass when they cannot play)
- Private/public lobby concept (mock uses a single demo lobby)
- Real-time updates via Socket.io

Run locally
1. Install deps:
   npm install

2. Start dev servers (runs mock server + Vite):
   npm run dev

3. Open the app:
   Frontend: http://localhost:5173
   Mock server: http://localhost:3001 (Socket.io)

Deploy (public URL)
- Frontend (Vercel):
  1. Create a new Vercel project, link to your GitHub repo, and set framework to Vite.
  2. Add Environment Variable: VITE_SOCKET_URL = https://your-mock-server-url
  3. Deploy.

- Mock server (Render recommended):
  1. Create a new Web Service on Render.
  2. Connect to your GitHub repo and point to `server/index.js`.
  3. Set start command: `node server/index.js`
  4. Ensure port 10000+ isn't forced — Render sets PORT; for Render replace hardcoded port in server/index.js with process.env.PORT || 3001.
  5. Deploy and copy the public URL; set VITE_SOCKET_URL in Vercel to `https://<render-url>`.

Notes
- This mock server is for demo purposes only. Replace with your real backend for production.
- Password/private-lobby logic, scoring persistence, and full rules are not enforced in the mock server — the code is a simple simulation to test the frontend UI and socket flows.

If you want, I can modify server/index.js to use process.env.PORT and add extra files (.env.example) and a production-ready Dockerfile. Tell me which and I’ll paste them.
