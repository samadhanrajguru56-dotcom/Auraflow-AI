# 🚀 Deploying AURAFLOW AI to Vercel

This guide outlines how to deploy **AuraFlow AI** to Vercel in just a few clicks.

---

## 🌟 Method 1: Deploy Frontend to Vercel (Recommended & Most Popular)

Vercel is the premier global platform for hosting modern React/Vite frontends.

### Step 1: Push your Code to GitHub
Ensure your repository is pushed to your GitHub account (e.g. `https://github.com/your-username/auraflow-ai`).

### Step 2: Import Project on Vercel
1. Go to [https://vercel.com/new](https://vercel.com/new) and log in.
2. Click **"Import"** next to your GitHub repository.
3. In the project configuration:
   - **Framework Preset**: Select `Vite`
   - **Root Directory**: Click `Edit` and select **`frontend`**
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`

### Step 3: Add Environment Variables
Under the **Environment Variables** section, add:

| Key | Value | Description |
|---|---|---|
| `VITE_API_URL` | `https://your-backend.onrender.com/api` (or your backend URL) | Points frontend to your live backend |

### Step 4: Click Deploy!
- Vercel will install dependencies, compile the production bundle via Vite, and launch your global edge deployment in ~30 seconds.
- The included [`frontend/vercel.json`](file:///frontend/vercel.json) already has Single Page Application (SPA) rewrite rules configured so routes like `/dashboard`, `/approvals`, `/tasks`, and `/create-request` will never return 404 on refresh!

---

## ⚡ Method 2: Deploy Full-Stack Monorepo on Vercel

If you want both the **frontend** and **backend** on Vercel under the same domain (`your-app.vercel.app` and `your-app.vercel.app/api/*`):

### Configured Files:
- Root [`vercel.json`](file:///vercel.json): Automatically routes `/api/*` to the serverless backend function and `/*` to the Vite frontend.
- Backend Entrypoint [`backend/api/index.js`](file:///backend/api/index.js): Serverless handler with MongoDB connection caching.

### Steps on Vercel:
1. Import the root repository on [https://vercel.com/new](https://vercel.com/new).
2. Leave **Root Directory** as `./` (the root).
3. Add your production environment variables:

| Key | Example Value |
|---|---|
| `MONGODB_URI` | `mongodb+srv://<user>:<password>@cluster.mongodb.net/flowpilot?retryWrites=true&w=majority` |
| `JWT_SECRET` | `flowpilot_super_secure_jwt_secret_hackathon_2026` |
| `GEMINI_API_KEY` | *(Optional for live Gemini calls)* |
| `NODE_ENV` | `production` |

4. Click **Deploy**.

---

## 🛡️ Backend Hosting Alternatives (For Persistent Daemons)
Because Express applications that use background timers (like the SLA Watchdog) run best as persistent services, many developers host:
- **Frontend** on **Vercel** ([vercel.com](https://vercel.com))
- **Backend** on **Render** ([render.com](https://render.com)) or **Railway** ([railway.app](https://railway.app))

### Deploying Backend to Render in 2 minutes:
1. Go to [dashboard.render.com](https://dashboard.render.com) → **New Web Service**.
2. Connect your repo and set:
   - **Root Directory**: `backend`
   - **Build Command**: `npm install`
   - **Start Command**: `node src/server.js`
3. Copy your Render service URL (e.g. `https://auraflow-backend.onrender.com`) and paste it as `VITE_API_URL` in your Vercel frontend settings!
