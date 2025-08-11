# VirtuWeather
A fluid, responsive weather app built with **Next.js 15**, **Tailwind CSS v4**, and the **OpenWeatherMap** API. Features city search, geolocation (“Use my location”), °C/°F units, current conditions, hourly strip, and 5-day outlook—with graceful loading/error states and an optional demo fallback for local development.

## ✨ Features
- React + Tailwind UI with smooth micro-interactions (Framer Motion)
- City search with quick results
- **Use my location** (HTML5 Geolocation → lat/lon endpoints)
- API-driven units (**metric/imperial**)
- Current, hourly (3-hour blocks), and 5-day grouped outlook
- Clear loading/error states; optional mock fallback for offline demos

## 🧰 Tech Stack
- **Framework:** Next.js 15 (App Router)
- **Styling:** Tailwind CSS v4
- **UI/Icons:** Framer Motion, lucide-react
- **Data:** OpenWeatherMap REST API

## 🚀 Quick Start
**Prereqs:** Node.js 18+ and npm

```bash
# 1) Install deps
npm install

# 2) Environment variables (create at project root)
# .env.local
NEXT_PUBLIC_OPENWEATHER_API_KEY=YOUR_KEY_HERE

# 3) Dev server
npm run dev
# → http://localhost:3000
```

> Geolocation requires HTTPS or `http://localhost`. Allow the browser permission prompt when asked.

## ⚙️ Configuration
- **API Key:** `NEXT_PUBLIC_OPENWEATHER_API_KEY` (browser-exposed for OWM)
- **Demo fallback:** In `components/VirtuWeather.tsx`, toggle `DEMO_FALLBACK` (or gate via `NEXT_PUBLIC_DEMO_FALLBACK=1`).

## 📁 Project Structure
```
app/
  layout.tsx        # imports ./globals.css
  page.tsx          # renders <VirtuWeather/>
  globals.css       # Tailwind entry (@import "tailwindcss"; or @tailwind ...)
components/
  VirtuWeather.tsx  # 'use client'; main component
postcss.config.js   # Tailwind v4: { plugins: { '@tailwindcss/postcss': {} } }
tailwind.config.js  # optional (v4 can be zero-config)
tsconfig.json       # alias config (e.g., @/* → project root)
```

## 🧪 Scripts
```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint"
  }
}
```

## ☁️ Deployment
**Vercel (recommended)**
1. Push to GitHub
2. Import the repo in Vercel
3. Add env var: `NEXT_PUBLIC_OPENWEATHER_API_KEY` in Project Settings → Environment Variables
4. Deploy

**Firebase Hosting / Netlify**
- Add the same env var in project settings
- Build (`npm run build`) and deploy per host instructions

## 🧩 Tailwind v4 note
Tailwind 4’s PostCSS plugin is now separate. Ensure `postcss.config.js` uses:
```js
module.exports = {
  plugins: {
    '@tailwindcss/postcss': {},
  },
}
```
Use **either** `@import "tailwindcss";` **or** the classic `@tailwind base; @tailwind components; @tailwind utilities;` in `app/globals.css` (pick one).

## 🙌 Credits
Built by **Dillon Noronha** · dnoronhawork@outlook.com

## 📄 License
Released under the **MIT License**. See `LICENSE` for details.
