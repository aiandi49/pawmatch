# PawMatch

**Tucson's Dog Playdate Matching App — East Side 85710**

Built by Lamar Myers · VTREI, LLC · AI&I

---

## Quick Setup

### 1. Create Supabase Project
1. Go to [supabase.com](https://supabase.com) and create a new project
2. Copy your **Project URL** and **anon public key** from Settings > API

### 2. Run the Database SQL
Copy the SQL block from the bottom of `index.html` (between the SQL REFERENCE comments) and run it in your Supabase Dashboard > SQL Editor.

This creates:
- `pup_profiles` table
- `playdate_requests` table
- `safety_watchboard` table
- Row Level Security policies on all three tables

### 3. Create the Storage Bucket
1. Supabase Dashboard > Storage > New Bucket
2. Name: `pup-photos`
3. Set to **Public**
4. File size limit: 8MB
5. Allowed MIME types: `image/jpeg, image/png, image/webp, image/gif`

### 4. Add Your Credentials to index.html
Open `index.html` and replace these two lines near the top of the `<script>` block:

```js
var SUPA_URL = '[SUPABASE_PROJECT_URL]';
var SUPA_KEY = '[SUPABASE_ANON_KEY]';
```

Replace with your real values:

```js
var SUPA_URL = 'https://yourproject.supabase.co';
var SUPA_KEY = 'your-real-anon-key-here';
```

**Note:** The anon key is safe to include in client-side code — it only has the permissions defined by your RLS policies.

### 5. Deploy to Vercel
1. Push this folder to a new GitHub repository named `pawmatch`
2. Go to [vercel.com](https://vercel.com) and import the repo
3. No build settings needed — it's a static HTML file
4. Deploy

---

## Security Features Built In

| Feature | Status |
|---------|--------|
| Row Level Security (RLS) | SQL ready — run in Supabase |
| XSS Prevention | `esc()` on all user data renders |
| Input maxlength | All fields capped |
| No credentials in JS | Placeholder tokens only |
| Photo in Supabase Storage | Not base64 in DB |
| Security headers | `vercel.json` configured |
| Clickjacking protection | X-Frame-Options DENY |
| HTTPS enforced | HSTS header set |
| No fake/dummy data | Zero — all real or empty |

---

## Zero Dummy Data Policy

Per AI&I Agent Instructions v5.0:

**No fake names, placeholder emails, lorem ipsum, invented testimonials, test API keys, or synthetic data of any kind appears anywhere in this codebase.**

Placeholder tokens are clearly marked in ALL_CAPS brackets: `[SUPABASE_PROJECT_URL]`

---

## App Features

- **Profile Tab** — Create pup profile with photo upload to Supabase Storage
- **Browse Tab** — View all Tucson pups with East Side filter, size, and energy filters
- **Matches Tab** — See your playdate requests with Safety Checklist access
- **Safety Board** — Community safety reports after every playdate
- **My Pup Tab** — View, edit, and delete your own profile
- **Match Celebration** — Confetti overlay when a request is sent
- **Safety Checklist Modal** — Full in-app confirmation (no browser alerts)
- **Voice Input** — Speech-to-text on bio and name fields
- **Keyboard Accessible** — All interactive elements keyboard navigable
- **Dark Theme** — First and only. No light mode toggle.

---

## East Side Tucson Parks Featured

- Brandi Fenton Dog Park
- Agua Caliente Regional Park
- Pantano River Park
- Saguaro National Park East

---

## Tech Stack

- Pure HTML, CSS, JavaScript — no frameworks, no build step
- Supabase (PostgreSQL + Storage + Realtime)
- Vercel (hosting + CDN)
- Google Fonts (Instrument Serif + Outfit + JetBrains Mono)

---

## Repository Structure

```
pawmatch/
  index.html     Main app
  vercel.json    Deployment config with security headers
  README.md      This file
```

---

VTREI, LLC · AI&I · Tucson Arizona · East Side 85710
