🤖 AI Code Reviewer

An AI-powered automated code review system built using GitHub Actions, Google Gemini AI, and Python.

This project automatically:

Detects new code changes pushed to GitHub
Extracts the latest git diff / commit changes
Sends the code to Gemini AI for analysis
Generates intelligent code review feedback
Sends the feedback through email automatically
🚀 Features

✅ Automated GitHub Actions workflow
✅ AI-generated code review using Gemini API
✅ Automatic email delivery of review feedback
✅ Secure secret management using GitHub Secrets
✅ CI/CD-based automation pipeline
✅ Detects latest commit changes using Git
✅ Lightweight Python-based implementation

🧠 Tech Stack
Technology	Usage
Python	Core backend logic
GitHub Actions	CI/CD automation
Google Gemini AI	AI code review generation
SMTP / Gmail	Email delivery
Git	Change detection
📁 Project Structure
AI_Code_Rev/
│
├── .github/
│   └── workflows/
│       └── python_app.yml
│
├── scripts/
│   └── review.py
│
├── app.py
├── requirements.txt
├── .gitignore
└── README.md

⚙️ How It Works
Step 1 — Push Code

Whenever code is pushed to the main branch, GitHub Actions automatically triggers.

Step 2 — Extract Code Changes

The Python script uses Git commands to fetch the latest code changes.

Step 3 — AI Review Generation

The extracted code changes are sent to Google Gemini AI.

Step 4 — Generate Feedback

Gemini analyzes:

Logic issues
Formatting problems
Best practices
Security concerns
Optimization suggestions
Step 5 — Email Delivery

The generated review feedback is automatically emailed to the configured recipient.

🔄 GitHub Actions Workflow

The workflow:

Checks out repository code
Sets up Python environment
Installs dependencies
Runs review script
Sends AI-generated review email
🔐 Environment Variables

The project uses GitHub Secrets for secure credential handling.

Required Secrets
Secret Name	Purpose
GOOGLE_API_KEY	Gemini API access
MAIL_APP_PASSWORD	Gmail App Password
📦 Installation
Clone Repository
git clone https://github.com/akshitgajera1013/AI_Code_Review.git
cd AI_Code_Rev

Create Virtual Environment
python -m venv venv

Activate Virtual Environment

Windows
venv\Scripts\activate
Linux / Mac
source venv/bin/activate   

nstall Dependencies
pip install -r requirements.txt

🛠️ GitHub Secrets Setup

Go to:
Repository → Settings → Secrets and variables → Actions

Add:
GOOGLE_API_KEY
MAIL_APP_PASSWORD

📧 Gmail App Password Setup

This project uses Gmail SMTP for automated email delivery.

Enable:

2-Step Verification
Generate Gmail App Password

Use the generated password inside:

📧 Gmail App Password Setup

This project uses Gmail SMTP for automated email delivery.

Enable:

2-Step Verification
Generate Gmail App Password

Use the generated password inside:

▶️ Running Locally

python scripts/review.py

🧪 Example AI Review Output

Code Review Feedback:

1. Logical bug detected in multiplication function.
2. Missing error handling in SMTP block.
3. Improve formatting using PEP 8 standards.
4. Remove unused dependencies from requirements.txt.

👨‍💻 Author
Akshit Gajera

Aspiring Data Scientist & Machine Learning Developer
