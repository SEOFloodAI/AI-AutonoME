# AI-AutonoME

AI-AutonoME is a full-stack AI application with:
- A modern **web frontend** (React + Vite + React Router + Tailwind + Chakra UI)
- A **mobile app** (React Native + Expo + Expo Router)

It appears designed for autonomous AI features, possibly involving task automation, subscriptions (via RevenueCat), advanced graphics (Skia), and more.

> **Note**: This repo currently has separate `/web` and `/mobile` directories. The web version is Vite-based (not Next.js), and the mobile version requires a custom Expo dev client due to native modules.

## Project Structure
AI-AutonoME/
├── mobile/          # React Native + Expo app (iOS/Android + web hybrid support)
├── web/             # React web app (Vite + React Router)
├── .gitattributes
└── README.md        # ← You are here
text## Web Version (/web)

### Tech Stack
- React 18+
- Vite (build tool)
- React Router (file-based routing via react-router.config.ts)
- Tailwind CSS + PostCSS
- Chakra UI (components)
- TypeScript
- TanStack Query (data fetching)
- Bun (preferred package manager, but npm/pnpm work)

### Quick Start (Local Development)
1. Navigate to the web folder:
   ```bash
   cd web

Install dependencies:Bashbun install
# or npm install
Run dev server:Bashbun dev
# or npm run dev→ Opens at http://localhost:5173 (Vite default)

Deployment (Vercel / Netlify / etc.)

Root directory: /web
Build command: bun run build (or npm run build)
Output directory: dist
Install command: bun install (or npm ci)

Important Fix: Make sure index.html exists in /web root (Vite entry point). A minimal version looks like:
HTML<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>AI-AutonoME</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>
If preview/deploy fails, double-check this file and your src/main.tsx (or src/index.tsx) rendering to #root.
Mobile Version (/mobile)
Tech Stack

Expo SDK ~51+
Expo Router (file-based navigation)
React Native Reanimated, Gesture Handler
RevenueCat (in-app purchases/subscriptions)
Shopify React Native Skia (advanced 2D graphics)
Other: Maps, 3D (expo-three?), WebGL (expo-gl)

Important: Expo Go Limitations
This app cannot run in standard Expo Go because of custom native modules (RevenueCat, Skia, etc.). You need a custom development build.
Setup Steps

Navigate to mobile folder:Bashcd mobile
bun install   # or npm install / yarn
Install EAS CLI (if not already):Bashnpm install -g eas-cli
eas login
(Optional but recommended) Add config plugins to app.json for RevenueCat/Skia if missing.
Build custom dev client:Basheas build --profile development --platform ios    # or androidInstall the resulting build on your device.
Start dev server:Bashnpx expo start --dev-clientScan QR with your custom client app.

For web preview from mobile code (hybrid):
Bashnpx expo start --web
Contributing / Next Steps

Add environment variables (.env) for API keys, RevenueCat public keys, etc.
Write tests (Vitest in web, Jest in mobile?).
Add CI/CD (GitHub Actions for builds).
Create separate READMEs in /web and /mobile for more detailed docs.

Feel free to open issues or PRs!
Built with ❤️ by SEO
