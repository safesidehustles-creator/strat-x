# STRAT-X — Demonbreun Strat Options Agent

Disciplined options analysis using The Strat methodology (created by Rob Smith).
Built by Demonbreun Dynasty Empire LLC.

## What it is

A web app with a Claude-powered agent that runs a strict 10-step Strat analysis
on any ticker. It refuses to guess, refuses to hype, and says NO TRADE when the
setup is not clean.

- **Frontend:** static HTML/CSS/JS (no build step)
- **Backend:** one serverless function (`/api/chat.js`)
- **Security:** your API key lives server-side only, never exposed to the browser

---

## Deploy in 3 steps

### 1. Get an Anthropic API key
Go to https://console.anthropic.com → API Keys → Create Key. Copy it.
Add a few dollars of credit under Billing.

### 2. Push this folder to GitHub
```bash
git init
git add .
git commit -m "STRAT-X initial"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/strat-x.git
git push -u origin main
```

### 3. Deploy on Vercel
1. Go to https://vercel.com → **Add New → Project**
2. Import your `strat-x` repo
3. Framework Preset: **Other** (leave build settings empty)
4. Expand **Environment Variables** and add:
   - Name: `ANTHROPIC_API_KEY`
   - Value: your key from step 1
5. Click **Deploy**

Live in ~30 seconds at `your-project.vercel.app`.

---

## Custom domain

Vercel → your project → Settings → Domains → add your domain
(e.g. `strat.yourdomain.com`) and follow the DNS instructions.

---

## Add to iPhone home screen

Open the live URL in Safari → Share → **Add to Home Screen**.
Runs full-screen like a native app.

---

## Changing the agent's behavior

All agent rules live in the `SYSTEM_PROMPT` constant at the top of
`api/chat.js`. Edit it, commit, push — Vercel redeploys automatically.

---

## Disclaimer

Educational tool only. Not financial advice. Options trading involves
substantial risk of loss. Never trade money you cannot afford to lose.
