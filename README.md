# SWE 2 Prep Tracker

## Project structure

```
swe2-tracker/
├── index.html      ← the full app
├── api/
│   └── chat.js     ← Vercel serverless proxy (hides your API key)
├── vercel.json     ← routing config
└── README.md
```

## Deploy in 5 steps

### 1. Create a GitHub repo

- Go to https://github.com/new
- Name it `swe2-tracker`, make it **private**
- Don't add any files yet, just create it

### 2. Push this folder to GitHub

Open your terminal in the `swe2-tracker` folder and run:

```bash
git init
git add .
git commit -m "initial"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/swe2-tracker.git
git push -u origin main
```

### 3. Deploy to Vercel

- Go to https://vercel.com and sign in with GitHub
- Click **Add New → Project**
- Import your `swe2-tracker` repo
- Leave all settings as default
- Click **Deploy**

### 4. Add your Anthropic API key

- In Vercel, go to your project → **Settings → Environment Variables**
- Add:
  - **Name:** `ANTHROPIC_API_KEY`
  - **Value:** your key from https://console.anthropic.com
- Click Save
- Go to **Deployments** → click the three dots on the latest deploy → **Redeploy**

### 5. Share the URL

Vercel gives you a URL like `https://swe2-tracker.vercel.app`.
Share that with your friend — no login needed, works on any device.

## Notes

- Progress is saved in the browser's localStorage per device.
  If your friend uses a different device, progress won't carry over
  (that would need a database — ask if you want to add that later).
- Your API key is never exposed to the browser — all Claude calls
  go through `/api/chat` on the server.
