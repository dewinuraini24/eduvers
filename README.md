# EDUVERSE: THE LEARNING CITY — Web Multiplayer Starter

Students open the website on their own phones and join the same Colyseus room using a code.

## Run locally
Requirements: Node.js 20+ and npm 10+.
```bash
npm install
npm run dev
```
Open the Vite URL. One browser window selects Teacher and creates a room; another selects Student and joins with that room code.

## Publish as a website
The web client and multiplayer server must be deployed separately:
1. Put this project in a GitHub repository.
2. Deploy the Node service using `render.yaml` or another host supporting persistent WebSockets.
3. Copy the server's secure WebSocket URL (wss://...).
4. Import the repository into Netlify. Build command: `npm run build -w client`; publish directory: `client/dist`.
5. Set Netlify environment variable `VITE_GAME_SERVER_URL` to the server WebSocket URL, then redeploy.
6. Share the Netlify website URL with students. The teacher creates a room and shares its code.

Included: basic 3D city, blocky avatar, Colyseus room connections, room codes, server-side learning timer/phase, and a simple quiz message flow.

Not yet included: production teacher authentication, full teacher dashboard/editor, persistent Supabase integration, complete learning interiors, synchronized airplane/parachute cutscenes, full obstacle course/checkpoint system, comprehensive leaderboard/reporting, and real-device QA. Room state is in memory and clears on server restart.

Teacher mode is a demo role, not secure authentication. Do not use with real student data until authentication, authorization, database RLS, privacy controls, abuse prevention, and deployment security are implemented and reviewed.
