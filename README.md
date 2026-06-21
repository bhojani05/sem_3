# 💪 Fitness Tracker Pro

A full-featured fitness tracking web application built with **Streamlit**, featuring activity logging, nutrition & water tracking, workout plans, progress analytics, and an AI-powered fitness coach.

## 📋 Overview

**Fitness Tracker Pro** is an all-in-one personal fitness dashboard. Users can create a secure account, log daily activities and meals, track water intake, follow workout plans, monitor progress over time with visual charts, and chat with an AI coach for personalized fitness advice — all from an interactive web interface powered by Streamlit and backed by a local SQLite database.

## ✨ Features

- **🔐 Secure Authentication** — User signup/login with salted, hashed passwords (PBKDF2-SHA256) and enforced password strength rules.
- **📊 Dashboard** — At-a-glance overview of daily stats and goals.
- **🏃 Activity Tracking** — Log workouts with type, duration, calories burned, distance, and intensity.
- **🍎 Nutrition Logging** — Track meals and calorie/macro intake against daily goals.
- **💧 Water Intake Tracker** — Monitor daily hydration against a configurable goal.
- **🏋️ Workout Plans** — Create and follow structured workout routines.
- **🏆 Achievements** — Unlock milestones as you hit fitness goals.
- **🤖 AI Fitness Coach** — Get personalized advice via Groq's LLaMA 3.1 model, with a rule-based fallback if no API key is configured.
- **📈 Progress & Reports** — Visualize trends over time using Plotly and Matplotlib charts.
- **⚙️ Settings** — Manage profile details and preferences.

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend / App Framework | [Streamlit](https://streamlit.io/) |
| Database | SQLite |
| Charts | Plotly, Matplotlib |
| Data Handling | Pandas |
| AI Coach | [Groq API](https://groq.com/) (LLaMA 3.1 8B Instant) |
| Auth/Security | `hashlib`, `secrets` (PBKDF2 password hashing) |

## 📂 Project Structure

```
fitness-tracker-pro/
├── Fitness_Tracker.py     # Main Streamlit application
├── requirements.txt       # Python dependencies
└── README.md
```

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/your-username/fitness-tracker-pro.git
cd fitness-tracker-pro
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Configure your AI coach (optional)
The AI coach feature requires a [Groq API key](https://console.groq.com/). Create a `.streamlit/secrets.toml` file (this file is git-ignored and should **never** be committed):

```toml
GROQ_API_KEY = "your-groq-api-key-here"
```

If no key is provided, the app still runs — the AI coach will just be unavailable.

### 4. Run the app
```bash
streamlit run Fitness_Tracker.py
```

The app will open automatically in your browser at `http://localhost:8501`.

## 🔒 Security Notes

- Passwords are never stored in plain text — they're salted and hashed using PBKDF2-HMAC-SHA256 with 100,000 iterations.
- API keys and secrets belong in `.streamlit/secrets.toml`, which should always be added to `.gitignore` and never pushed to version control.
- The local `fitness_pro.db` SQLite file (created on first run) should also be excluded from version control, as it may contain real user data.

## 🔮 Future Improvements

- Migrate from SQLite to a production-grade database (e.g., PostgreSQL) for multi-user deployments
- Add data export (CSV/PDF) for reports
- Add social/sharing features for achievements
- Containerize with Docker for easier deployment

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
