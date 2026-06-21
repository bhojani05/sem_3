# 🚀 Project Showcase

This repository contains two independent full-stack projects, each demonstrating a different stack and set of skills — one built with **Python**, the other with **HTML/CSS/JavaScript**.

| Project | Stack | Description |
|---|---|---|
| [💪 Fitness Tracker Pro](#-1-fitness-tracker-pro-python) | Python, Streamlit, SQLite | AI-powered fitness & wellness tracking app |
| [✈️ Tripzy — Tours & Travels](#%EF%B8%8F-2-tripzy--tours--travels-web) | HTML, CSS, Bootstrap, JS | Travel booking website with admin dashboard |

## 📂 Repository Structure

```
project-showcase/
├── fitness-tracker-pro/
│   ├── Fitness_Tracker.py
│   ├── requirements.txt
│   └── .streamlit/
│       └── secrets.toml        # git-ignored, never commit
│
├── tripzy-tours-travels/
│   ├── index.html
│   ├── Explore1.html
│   ├── Hotels_Premium.html
│   ├── Tasty_Bites.html
│   ├── Admin.html
│   ├── PrivacyPolicy.html
│   ├── T&C.html
│   ├── style.css
│   ├── new1.js
│   ├── admin.js
│   └── DataStructures.js
│
├── .gitignore
└── README.md
```

---

## 💪 1. Fitness Tracker Pro (Python)

An AI-powered fitness tracking web app built with Streamlit. Users can log workouts, nutrition, and water intake, follow workout plans, monitor progress with interactive charts, and get personalized coaching from an LLM-powered AI trainer (via the Groq API), all backed by a SQLite database with secure, salted password authentication.

### Features
- 🔐 Secure signup/login with salted, hashed passwords (PBKDF2-SHA256)
- 🏃 Activity, nutrition, and water intake logging
- 🏋️ Workout plans and 🏆 achievements
- 🤖 AI fitness coach powered by Groq's LLaMA 3.1 model
- 📈 Progress charts and reports (Plotly, Matplotlib)

### Tech Stack
Python · Streamlit · SQLite · Pandas · Plotly · Matplotlib · Groq API

### Setup & Run
```bash
cd fitness-tracker-pro
pip install -r requirements.txt
```

Create `.streamlit/secrets.toml` (never commit this file):
```toml
GROQ_API_KEY = "your-groq-api-key-here"
```

Run the app:
```bash
streamlit run Fitness_Tracker.py
```

---

## ✈️ 2. Tripzy — Tours & Travels (Web)

A responsive travel booking website built with HTML, CSS, Bootstrap, and vanilla JavaScript. Users can explore destinations, book hotels and dining, manage their bookings (edit, cancel, like, export as PDF), and sign in through a full authentication flow. A dedicated admin panel handles bookings, listings, and users, with client-side data persistence and custom-implemented data structures.

### Features
- 🔐 Full auth flow — signup, login, password reset (OTP-style)
- 🗺️ Explore destinations, premium hotels, and dining options
- 📑 Manage bookings — edit, cancel, like, and export confirmations as PDF
- 🛠️ Admin dashboard — manage bookings, destinations, hotels, users, and messages
- 🧱 Custom data structures (Stack, Queue, Priority Queue) implemented in vanilla JS
- 🎨 Smooth UI animations via AOS, responsive design via Bootstrap 5

### Tech Stack
HTML5 · CSS3 · Bootstrap 5 · JavaScript (ES6) · Font Awesome · AOS · html2pdf.js
*(Data persistence via browser `localStorage` — no backend server)*

### Setup & Run
No build step required — it's a static site.
```bash
cd tripzy-tours-travels
```
Then simply open `index.html` in your browser, or serve it locally:
```bash
npx serve .
```

---

## 🔒 Security Notes

- The Fitness Tracker's `.streamlit/secrets.toml` (API keys) and `fitness_pro.db` (local database) are excluded via `.gitignore` and must never be committed.
- The Tripzy admin password and demo accounts are for **local/demo use only** — this site has no real backend authentication and should not be used to handle real user data in production.

## 🔮 Future Improvements

- **Fitness Tracker Pro:** migrate to a production database, add data export, containerize with Docker
- **Tripzy:** connect to a real backend/database instead of `localStorage`, add payment gateway integration

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
