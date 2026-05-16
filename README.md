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
