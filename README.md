# BE · DO · HAVE — Identity Dashboard

Your personal identity map and validation space, hosted free online, powered by Google Sheets.

---

## How it works

```
Google Sheets  →  GitHub  →  Netlify (free hosting)
   (your data)    (code)      (live dashboard URL)
```

You add rows to your Google Sheet → the dashboard reads it live → no code needed after setup.

---

## Step 1 — Set up your Google Sheet

### Create the spreadsheet

1. Go to [sheets.new](https://sheets.new) and create a new spreadsheet
2. Rename it **BE·DO·HAVE Identity Map** (or anything you like)
3. Create **3 tabs** with exactly these names: `BE`, `DO`, `HAVE`

---

### Tab: BE

These are your identity declarations — who you already are.

| Column | Name | Example |
|--------|------|---------|
| A | `statement` | builds meaningful client relationships with ease |
| B | `domain` | Sales & Revenue |
| C | `conviction` | 3 *(number 1–5)* |
| D | `date` | 2025-01-20 |

**Conviction scale:**
- 1 = Just declaring it
- 2 = Starting to feel it
- 3 = Becoming real
- 4 = Strongly feel this
- 5 = This is me

---

### Tab: DO

Every action taken *as the person you declared yourself to be*.

| Column | Name | Example |
|--------|------|---------|
| A | `action` | Sent a cold outreach that led to a discovery call |
| B | `identity_link` | builds meaningful client relationships with ease |
| C | `note` | I didn't wait to feel ready. I acted from the identity. |
| D | `date` | 2025-01-21 |

> **`identity_link`** = paste a short label from your BE statement. This is what traces the action back to who you are.

---

### Tab: HAVE

Results, outcomes, and things that manifested — traced back to their identity source.

| Column | Name | Example |
|--------|------|---------|
| A | `result` | Signed a €3k retainer with a new client |
| B | `description` | They reached out after seeing my LinkedIn post |
| C | `identity_link` | builds meaningful client relationships with ease |
| D | `action_link` | Sent a cold outreach that led to a discovery call |
| E | `date` | 2025-01-25 |

---

### Publish your sheet

This is required so the dashboard can read your data.

1. In your Sheet: **File → Share → Publish to web**
2. Select **Entire Document** and **Comma-separated values (.csv)**
3. Click **Publish** → confirm
4. Copy the **Sheet ID** from your URL bar:
   ```
   https://docs.google.com/spreadsheets/d/→ YOUR_SHEET_ID ←/edit
   ```

---

## Step 2 — Connect your Sheet to the dashboard

Open `index.html` and find this line (around line 290):

```js
SHEET_ID: window.SHEET_ID || 'YOUR_SHEET_ID_HERE',
```

Replace `YOUR_SHEET_ID_HERE` with your actual Sheet ID.

---

## Step 3 — Push to GitHub

1. Create a free account at [github.com](https://github.com) if you don't have one
2. Create a new repository — name it `bdh-dashboard` (make it **Public**)
3. Upload your files:

```bash
git init
git add .
git commit -m "initial dashboard"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/bdh-dashboard.git
git push -u origin main
```

Or drag-and-drop the files into the GitHub web interface.

---

## Step 4 — Deploy on Netlify (free, permanent URL)

1. Go to [netlify.com](https://netlify.com) and sign up with your GitHub account
2. Click **Add new site → Import an existing project**
3. Choose **GitHub** → select your `bdh-dashboard` repo
4. Leave all build settings blank (this is plain HTML — no build needed)
5. Click **Deploy site**

Netlify gives you a URL like `https://your-name-bdh.netlify.app` in ~30 seconds.

### Custom domain (optional, free)
In Netlify: **Site settings → Domain management → Add custom domain**

---

## Daily workflow

Once live, your daily workflow is just:

1. Open your Google Sheet
2. Add a row to BE, DO, or HAVE
3. Refresh your dashboard URL — data updates live

No code. No deploys. Just logging.

---

## File structure

```
bdh-dashboard/
├── index.html      ← the entire dashboard (single file)
└── README.md       ← this guide
```

---

## Updating the dashboard design

If you want to change anything visual, edit `index.html` locally and push to GitHub. Netlify auto-deploys within ~10 seconds.

---

## Troubleshooting

**"Could not load data" error**
→ Your sheet is not published. Go to File → Share → Publish to web and publish as CSV.

**Data not showing / wrong columns**
→ Make sure your tab names are exactly `BE`, `DO`, `HAVE` (case-sensitive) and column headers match the table above.

**Sheet shows old data**
→ Google's publish-to-web cache can take 5 minutes to refresh.

---

*Built with the BE→DO→HAVE framework. Identity first. Evidence always.*
