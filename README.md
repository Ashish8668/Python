# 🟢 GitHub Automated Heartbeat

Keep your GitHub contribution graph green — automatically!

This repository uses **GitHub Actions** to make an automated commit every 6 hours.

- No server required
- No external tools
- No personal access token
- Works on public & private repositories

---

## 🚀 What Does This Do?

Every 6 hours, GitHub Actions will:

- Update (or create) `heartbeat.txt`
- Write the current UTC timestamp
- Commit with message:  
  `chore: automated heartbeat`
- Push directly to the `main` branch

This keeps your GitHub contribution graph active automatically.

---

## 📁 Required Folder Structure

Your repository must look exactly like this:

```
your-repo/
│
├── heartbeat.txt (auto-created if missing)
│
└── .github/
    └── workflows/
        └── heartbeat.yml
```

⚠ **Important:**  
The folder must be named `.github/workflows/`  
**NOT** `.github/.workflows`  
Even one extra dot will break it.

---

## 🛠 Step-By-Step Setup Guide

### 1. Create Repository

- Create a new repository on GitHub
- Default branch must be `main`
- You may initialize with README (recommended)

---

### 2. Add Workflow File

- Create `.github/workflows/heartbeat.yml`
- Paste the workflow inside it

---

### 3. Update Your Identity (Very Important)

Inside `heartbeat.yml`, find:

```yaml
git config user.name "YOUR_USERNAME"
git config user.email "YOUR_EMAIL"
```

Replace with your actual GitHub username and verified email:

```yaml
git config user.name "YourGitHubUsername"
git config user.email "your_verified_email@gmail.com"
```

⚠ The email **MUST**:
- Be added in GitHub → Settings → Emails
- Be verified

Otherwise, commits will show as `github-actions[bot]`.

---

### 4. Commit & Push

From your terminal:

```sh
git add .
git commit -m "setup: enable automated heartbeat"
git push origin main
```

---

### 5. Enable GitHub Actions Permissions

Go to:

- Repository → Settings → Actions → General

Make sure:

- Allow all actions
- Workflow permissions → Read and write permissions

Without write permission, pushing will fail.

---

### 6. Trigger First Run Manually

Go to:

- Repository → Actions → Automated Heartbeat

Click:

- Run workflow

Select branch: `main`  
Click: Run workflow

Wait 10–20 seconds to verify everything works before waiting 6 hours.

---

## 💡 Why Use This?

- Keeps your contribution graph green
- No manual commits needed
- Fully automated and secure

---

## 📄 License

MIT