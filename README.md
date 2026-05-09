<div align="center">

<br/>

```
  █████╗ ██╗     ██████╗ ██████╗ ██████╗ ███████╗    ██████╗ ███████╗██╗   ██╗
 ██╔══██╗██║    ██╔════╝██╔═══██╗██╔══██╗██╔════╝    ██╔══██╗██╔════╝██║   ██║
 ███████║██║    ██║     ██║   ██║██║  ██║█████╗      ██████╔╝█████╗  ██║   ██║
 ██╔══██║██║    ██║     ██║   ██║██║  ██║██╔══╝      ██╔══██╗██╔══╝  ╚██╗ ██╔╝
 ██║  ██║██║    ╚██████╗╚██████╔╝██████╔╝███████╗    ██║  ██║███████╗ ╚████╔╝ 
 ╚═╝  ╚═╝╚═╝     ╚═════╝ ╚═════╝ ╚═════╝ ╚══════╝    ╚═╝  ╚═╝╚══════╝  ╚═══╝  
```

### AI-Powered Automated Code Review via GitHub Actions & Google Gemini

<br/>

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-Automated-2088FF?style=flat-square&logo=github-actions&logoColor=white)](https://github.com/features/actions)
[![Google Gemini](https://img.shields.io/badge/Google%20Gemini-AI%20Powered-4285F4?style=flat-square&logo=google&logoColor=white)](https://deepmind.google/technologies/gemini/)
[![Gmail SMTP](https://img.shields.io/badge/Gmail%20SMTP-Email%20Delivery-EA4335?style=flat-square&logo=gmail&logoColor=white)](https://gmail.com)


<br/>

</div>

---

## Overview

**AI Code Reviewer** is a fully automated, CI/CD-native code review pipeline. Every time code is pushed to the `main` branch, the system extracts the latest git diff, sends it to **Google Gemini AI** for intelligent analysis, and delivers a structured review report directly to your inbox — no manual intervention required.

> Built for developers who want instant, AI-powered feedback without leaving their workflow.

---

## How It Works

```
  Push to main
       │
       ▼
┌─────────────────┐     ┌──────────────────┐     ┌──────────────────┐     ┌─────────────────┐
│  GitHub Actions │────▶│  Extract Git Diff │────▶│  Gemini AI Review│────▶│  Email Delivery │
│  Trigger (CI)   │     │  (Latest Commits) │     │  (Analysis + Tips│     │  via Gmail SMTP │
└─────────────────┘     └──────────────────┘     └──────────────────┘     └─────────────────┘
```

| Step | Action | Description |
|------|--------|-------------|
| **1** | Push Code | A commit to `main` triggers the GitHub Actions workflow |
| **2** | Extract Changes | Python script fetches the latest `git diff` |
| **3** | AI Analysis | Diff is sent to the Gemini API for review |
| **4** | Generate Feedback | Gemini identifies bugs, style issues, and improvements |
| **5** | Email Report | Review is delivered to your inbox automatically |

---

## Features

- 🤖 **AI-Generated Reviews** — Powered by Google Gemini for intelligent, context-aware feedback
- ⚡ **Zero-Touch Automation** — Runs entirely via GitHub Actions on every push
- 📧 **Instant Email Delivery** — Feedback lands in your inbox within seconds
- 🔐 **Secure by Design** — All credentials managed via GitHub Secrets
- 🔍 **Smart Diff Detection** — Extracts only the changed code, not the entire codebase
- 🧹 **PEP 8 & Best Practices** — Flags style violations, unused imports, and anti-patterns
- 🛡️ **Security Analysis** — Surfaces potential vulnerabilities in new code
- 🪶 **Lightweight** — Pure Python, minimal dependencies, no complex infrastructure

---

## Tech Stack

| Technology | Role |
|------------|------|
| **Python 3.10+** | Core backend logic and orchestration |
| **GitHub Actions** | CI/CD workflow automation |
| **Google Gemini AI** | Intelligent code analysis engine |
| **Gmail SMTP** | Automated email delivery |
| **Git** | Change detection via `git diff` |

---

## Project Structure

```
AI_Code_Rev/
│
├── .github/
│   └── workflows/
│       └── python_app.yml      # GitHub Actions workflow definition
│
├── scripts/
│   └── review.py               # Core review logic (diff extraction + AI call + email)
│
├── app.py                      # Entry point / local runner
├── requirements.txt            # Python dependencies
├── .gitignore
└── README.md
```

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/akshitgajera1013/AI_Code_Review.git
cd AI_Code_Rev
```

### 2. Set Up Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate — Windows
venv\Scripts\activate

# Activate — macOS / Linux
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure GitHub Secrets

Navigate to your repository:  
**Settings → Secrets and variables → Actions → New repository secret**

| Secret Name | Description |
|-------------|-------------|
| `GOOGLE_API_KEY` | Your Google Gemini API key |
| `MAIL_APP_PASSWORD` | Gmail App Password (see setup below) |

### 5. Run Locally

```bash
python scripts/review.py
```

---

## Gmail App Password Setup

This project uses Gmail SMTP for email delivery. Standard passwords won't work — you need an **App Password**.

1. Go to your [Google Account Security settings](https://myaccount.google.com/security)
2. Enable **2-Step Verification**
3. Search for **App Passwords** → generate one for "Mail"
4. Add the 16-character password as the `MAIL_APP_PASSWORD` secret in GitHub

> ⚠️ Never commit your App Password directly in code. Always use GitHub Secrets.

---

## GitHub Actions Workflow

The workflow (`.github/workflows/python_app.yml`) triggers on every push to `main` and performs the following steps:

```yaml
on:
  push:
    branches: [main]
```

| Step | Action |
|------|--------|
| ✅ Checkout code | Pulls the latest repository state |
| ✅ Setup Python | Configures the Python runtime environment |
| ✅ Install dependencies | Runs `pip install -r requirements.txt` |
| ✅ Run review script | Executes `scripts/review.py` |
| ✅ Send email | Delivers AI-generated feedback to recipient |

---

## Example AI Review Output

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  🤖 AI Code Review Report
  Commit: a3f92c1 · Branch: main
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

✦ [BUG]      Logical error detected in `multiply()` — returns incorrect result
             for negative inputs. Consider handling edge cases explicitly.

✦ [SECURITY] No input validation in the SMTP block — raw user input passed
             directly. Sanitize before use.

✦ [STYLE]    3 PEP 8 violations found: inconsistent indentation on lines 42,
             87, and 103. Use `black` or `autopep8` to auto-format.

✦ [CLEANUP]  `requests` imported but never used. Remove unused dependencies
             from requirements.txt to keep the environment lean.

✦ [OPTIMIZE] The nested loop on line 67 can be simplified to a list
             comprehension — reduces time complexity from O(n²) to O(n).

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  5 issues found · 2 critical · 3 minor
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Environment Variables Reference

| Variable | Source | Purpose |
|----------|--------|---------|
| `GOOGLE_API_KEY` | GitHub Secrets | Authenticates with Gemini API |
| `MAIL_APP_PASSWORD` | GitHub Secrets | Authenticates Gmail SMTP sender |

---

## Contributing

Contributions are welcome! If you have ideas for new features, better prompts, or additional integrations, feel free to open an issue or submit a pull request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request



<div align="center">

**Built by [Akshit Gajera](https://github.com/akshitgajera1013)**  
*Aspiring Data Scientist & Machine Learning Developer*

<br/>

⭐ If this project helped you, consider giving it a star!

</div>
