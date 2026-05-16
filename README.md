# 🦅 Telegram Quiz Bot – Falcon Bot

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://python.org)
[![Telegram Bot](https://img.shields.io/badge/Telegram-Bot-blue)](https://core.telegram.org/bots)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A fully-featured, production-ready Telegram bot for creating and managing quizzes. Designed for teachers, trainers, and educational platforms. Supports images per question, detailed analytics, leaderboards, and automatic backup to GitHub.

---

## ✨ Features

- 📚 **Multiple Quizzes** – Create unlimited quizzes, each with its own set of questions.
- 🖼️ **Image Support** – Attach an image to every question.
- 📊 **Detailed Analytics** – Track correct/wrong answers per question, participation rate.
- 🏆 **Leaderboard** – Displays top 5 scores for each quiz (first attempt only).
- 🔄 **Merge Questions** – Upload a `.json` file to merge new questions without losing existing data (admin only).
- 👑 **Admin Panel** – View statistics and upload new quizzes via Telegram commands.
- ☁️ **GitHub Sync** – Automatically backs up `leaderboard.json` and `analytics.json` to a private GitHub repo.
- ⚡ **High Performance** – In-memory caching + thread pool (max 5 concurrent uploads) to avoid blocking.
- 🔒 **Secure** – Tokens stored as environment variables; JSON upload restricted to admin.
- 🛡️ **Always Online** – Built-in Flask dummy server + UptimeRobot support to prevent sleeping on free hosts (Render, etc.).

---

## 🚀 Demo

> Send `/start` to the bot, then click on a quiz link like `https://t.me/YourBot?start=quiz_id`.

![Demo animation placeholder](https://via.placeholder.com/600x300?text=Telegram+Quiz+Bot+Demo)

---

## 📦 Installation

### 1. Clone the repository
```bash
git clone https://github.com/FALCONZeroX/Telegram-Quiz-Bot.git
cd Telegram-Quiz-Bot
```
2. Install dependencies
bash
pip install -r requirements.txt
3. Set up environment variables
Copy .env.example to .env and fill in your values:

env
BOT_TOKEN=your_telegram_bot_token
GITHUB_TOKEN=your_github_personal_access_token
ADMIN_ID=your_telegram_user_id
ADMIN_ID is optional; you can hardcode it in the script. But environment variable is recommended.

4. Run the bot locally
bash
python falcon_bot.py
☁️ Deploy to Render (Free)
Push the code to a private GitHub repository (or public if you removed tokens).

Sign up at Render.com and create a new Web Service.

Connect your GitHub repo.

Add environment variables (BOT_TOKEN, GITHUB_TOKEN, ADMIN_ID).

Set start command: python falcon_bot.py

Deploy. Your bot will stay alive with the built-in Flask server.

To prevent sleeping on free tier, use UptimeRobot to ping https://your-bot.onrender.com/ every 5 minutes.

📂 JSON Structure (questions.json)
json
{
  "python_basics": {
    "description": "Test your knowledge of Python basics",
    "questions": [
      {
        "text": "What is the correct way to print 'Hello' in Python?",
        "image": "https://example.com/python.jpg",
        "options": ["print('Hello')", "echo 'Hello'", "console.log('Hello')"],
        "correct": 0
      },
      {
        "text": "Which data type is immutable?",
        "image": null,
        "options": ["list", "tuple", "dict"],
        "correct": 1
      }
    ]
  }
}
description: short quiz description (shown before start).

image: optional URL (must be HTTPS and publicly accessible).

options: list of strings.

correct: zero‑based index of the correct option.

👑 Admin Commands
Command	Description
/admin	Open admin panel (only the user with ADMIN_ID).
📊 Statistics	Full analytics report: participation, success rate per question, top 5 leaderboard.
📤 Upload JSON	Send a .json file to merge new quizzes/ questions.
Upload is restricted to the admin user. Others will get a permission error.

📈 Analytics & Leaderboard
analytics.json – Stores per‑quiz, per‑question counts: correct, wrong.

leaderboard.json – Stores each user’s first attempt score only. No spamming.

Both files are automatically saved locally and pushed to GitHub asynchronously (using a ThreadPoolExecutor with max 5 workers).

🛠️ Built With
python-telegram-bot – Telegram API wrapper.

Flask – Dummy web server to keep service alive.

Requests – GitHub API communication.

Render – Recommended free hosting.

🤝 Contributing
Contributions are welcome! Feel free to open an issue or submit a pull request.

Fork the repository.

Create your feature branch: git checkout -b feature/amazing-feature.

Commit your changes: git commit -m 'Add some amazing feature'.

Push to the branch: git push origin feature/amazing-feature.

Open a Pull Request.

📄 License
Distributed under the MIT License. See LICENSE file for more information.

👤 Author
FALCONZeroX – GitHub

Special thanks to AI assistants for code structuring and problem solving.

🙏 Acknowledgements
python-telegram-bot documentation

Render free tier

UptimeRobot for keeping the bot awake.
