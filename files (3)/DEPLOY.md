# Quick Deploy — Phone-Friendly

## Option A: GitHub web upload (no terminal needed)

1. Go to github.com → **New repository** → name it `strat-x` → Create
2. Click **uploading an existing file**
3. Drag in ALL files from this folder (keep the `api/` and `public/` folders intact)
4. Commit

Then:
5. vercel.com → **Add New → Project** → Import `strat-x`
6. Framework Preset: **Other**
7. Environment Variables → add `ANTHROPIC_API_KEY` = your key
8. **Deploy**

Done. You get a live URL.

## Option B: Vercel CLI

```bash
npm i -g vercel
cd strat-x
vercel
vercel env add ANTHROPIC_API_KEY
vercel --prod
```

## Troubleshooting

**"ANTHROPIC_API_KEY is not set"**
→ Vercel → Settings → Environment Variables → add it → then Deployments → Redeploy

**401 / authentication error**
→ Key is wrong or has no credit. Check console.anthropic.com → Billing

**404 on /api/chat**
→ Make sure `api/chat.js` is at the repo root, not nested inside `public/`

**Page loads but nothing happens on send**
→ Open browser console. Usually a missing env var.
