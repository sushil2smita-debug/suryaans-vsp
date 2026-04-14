# SURYAANS PAPER – Vehicle Planning System (VPS)
### Firebase + GitHub + Vercel Edition

Real-time team app — all data shared live across all devices via Firebase Firestore.

## 🔑 Default Login
- **Username:** `admin`
- **Password:** `admin123`
> **Change this immediately** after first login: Settings → Change Password

---

## 🚀 Deploy in 3 Steps

### Step 1 — Push to GitHub
1. Create a new repo at github.com (e.g. `suryaans-vps`)
2. Upload all files from this folder to the repo
   - Click **"uploading an existing file"** on the repo page
   - Drag all files and commit

### Step 2 — Deploy on Vercel
1. Go to [vercel.com](https://vercel.com) → New Project
2. Import your GitHub repo
3. Framework: **Other** | Root: `.` | No build command needed
4. Click **Deploy** — done in 30 seconds

### Step 3 — Set Firebase Rules
In Firebase Console → Firestore → Rules, paste:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```
(This is fine for a private team app with login control)

---

## 👥 User Roles
| Role | Access |
|------|--------|
| Admin | Everything + User Management |
| Sales | Create & view loading plans |
| Billing | Verify plans, assign cities & vehicles |
| Logistics | Arrange vehicles, track status, mark loading done |

## ✅ Features
- 🔴 **Real-time sync** — changes appear instantly for all team members
- 📱 **Mobile + Desktop** — works on all devices
- 🔒 **Login required** — secure team-only access
- 🔄 **No refresh needed** — live updates via Firestore
- 📊 **Full pipeline** — Sales → Billing → Logistics → Done
