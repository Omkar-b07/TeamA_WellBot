<div align="center">

# 🤖 WellBot

### AI-Powered Global Wellness Assistant

<p align="center">
An intelligent wellness chatbot that provides personalized guidance for fitness, nutrition, sleep, hydration, and mental well-being through Natural Language Processing and Conversational AI.
</p>

<p>

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Rasa](https://img.shields.io/badge/Rasa-5A2FC2?style=for-the-badge&logo=rasa&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![NLTK](https://img.shields.io/badge/NLTK-154F3C?style=for-the-badge&logo=nltk&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

</p>

### 🌍 Your 24×7 Digital Wellness Companion

📖 Documentation • 🚀 Installation • ✨ Features • 🤝 Contributing

</div>

---

# 🌟 Overview

**WellBot** is an AI-powered conversational assistant designed to help users maintain a healthy lifestyle through personalized wellness guidance and recommendations.

The platform combines:

* 🧠 Natural Language Processing (NLP) with Rasa NLU
* 🤖 Conversational AI with multi-language support (English & Hindi)
* 📊 Wellness Analytics (Admin Dashboard & Activity tracking)
* 🎯 Personalized Recommendation Engine (from custom Rasa SDK actions)
* 🌍 Multi-domain Health Guidance (Symptoms, Prevention, First-Aid, Wellness tips)

WellBot assists users in managing:

* 🏃 Fitness Goals & Wellness Metrics
* 🥗 Nutrition & Diet suggestions
* 💧 Hydration tips
* 😴 Sleep tracking guidance
* 🧘 Mental Well-being & Stress Management

---

# 🎯 Problem Statement

Maintaining a balanced lifestyle is challenging due to fragmented health applications and the lack of personalized wellness guidance.

WellBot addresses this problem by providing a single AI-powered platform capable of understanding user queries (in multiple languages) and delivering precise recommendations related to fitness, diet, sleep, hydration, and mental wellness.

---

# ✨ Features

| 👤 User Features             | 🤖 AI Capabilities            | 🔒 Security            |
| ---------------------------- | ----------------------------- | ---------------------- |
| Interactive Chat Interface   | Intent Recognition            | Secure JWT Cookies Auth|
| Personalized Recommendations | NLP-based Query Understanding | Protected User Data    |
| Wellness Data Logging        | Context-Aware Responses       | Session Management     |
| Bilingual Support (EN & HI)  | Recommendation Engine         | Privacy-Focused Design |

---

# 💡 Smart Features

* 🎭 Emotion and mood understanding
* 🧠 NLP-based query processing (English & Hindi models)
* 🎯 Personalized wellness suggestions from SQLite DB
* 📊 Interactive Admin dashboard with feedback metrics
* 🔄 Context-aware dialog management
* 🌍 24×7 digital wellness support
* 💬 Thumbs Up/Down and comments logging feedback loop

---

# 🏗️ Project Modules

## 📊 Module 1 – Data Collection & Management
* Pre-loaded wellness metrics in CSV format
* Multi-language knowledge dataset loaded in the database
* User profile, language choice, and feedback persistence

## 🧠 Module 2 – NLP & Intent Understanding (Rasa)
* Text preprocessing and whitespace tokenization
* Intent classification (e.g., `ask_symptom`, `ask_first_aid`, `ask_prevention`, `ask_wellness_tip`)
* Condition entity extraction
* Hindi to English synonym mapper for unified backend search

## 🎯 Module 3 – Recommendation Engine & Chatbot
* Custom database query actions via Rasa SDK action server
* Automatic translation fallback for the requested language
* Admin interface to add/delete/manage wellness tips

---

# 🏗️ System Architecture

```text
       User (Web Interface)
               │
               ▼  HTTP/HTTPS Requests
      Flask API Web Server
        /      │       \
       /       │        \
      ▼        ▼         ▼
    SQLite   Rasa NLU  Rasa Custom Actions
   (AuthDB)  (Parser)    (SQL Query Engine)
```

---

# 🛠️ Technology Stack

| Category         | Technologies                          |
| ---------------- | ------------------------------------- |
| Frontend         | HTML5, CSS3, JavaScript, Bootstrap 5  |
| Backend          | Flask 3.0.3, Python 3.8+              |
| NLP              | Rasa 3.6.2, NLTK                      |
| Machine Learning | TensorFlow, Scikit-Learn (Rasa NLU)   |
| Database         | SQLite (Default), PostgreSQL (Prod)   |
| Authentication   | Flask-JWT-Extended                    |
| Deployment       | Docker, Docker Compose                |

---

# 📁 Repository Structure

```text
TeamA_WellBot/
│
├── frontend/
│   ├── static/                    # CSS stylesheets and Frontend auth/chat JS
│   │   ├── css/
│   │   └── js/
│   └── templates/                 # Login, Register, Profile, Chat, and Admin views
│
├── backend/
│   ├── rasa_bot/                  # Rasa NLU config, models, actions, and datasets
│   │   ├── actions/
│   │   ├── data/ (EN & HI NLU files)
│   │   └── config.yml
│   │
│   └── web_api/                   # Flask web API, database models, CSV loaders
│       ├── app.py
│       └── requirements.txt
│
├── docs/                          # PDF slide deck and project documentation
├── docker-compose.yml             # Docker services orchestration
├── DEPLOYMENT.md                  # Detailed deployment guide
└── README.md
```

---

# 🚀 Installation & Running

## Clone Repository

```bash
git clone https://github.com/Omkar-b07/TeamA_WellBot.git
cd TeamA_WellBot
```

## Running with Docker Compose (Recommended)

1. Copy env parameters:
   ```bash
   cp .env.example .env
   ```
2. Start all 3 services (`flask_app`, `rasa`, `action_server`):
   ```bash
   docker compose up --build -d
   ```
3. Load knowledge and seed database tables:
   ```bash
   docker compose exec flask_app python load_knowledge.py
   ```

## Running Manually (Development)

### 1. Setup Virtual Environment
```bash
python -m venv venv
# Windows:
venv\Scripts\activate
# Linux/macOS:
source venv/bin/activate
```

### 2. Install Web Dependencies
```bash
pip install -r backend/web_api/requirements.txt
```

### 3. Run Web App
```bash
python backend/web_api/app.py
```

*Note: You will also need to install Rasa separately in your environment and run `rasa run --enable-api` and `rasa run actions` to enable the chatbot features.*

---

# 📸 Screenshots

*Add screenshots here after deployment.*

| Login Page     | Dashboard      |
| -------------- | -------------- |
| Add Screenshot | Add Screenshot |

| Chat Interface | Recommendations |
| -------------- | --------------- |
| Add Screenshot | Add Screenshot  |

---

# 🚀 Future Enhancements

* 📱 Mobile Application (React Native/Flutter)
* 🎙️ Voice Assistant Integration
* ⌚ Smartwatch Integration
* 📊 Advanced Machine Learning Wellness Analytics
* 🤖 Generative AI-based LLM Fallbacks

---

# 👨‍💻 Team

## Team A – WellBot

* Omkar Bondge
* Team Member 2
* Team Member 3
* Team Member 4

### Project Guide

Prof. Santhiya Krishnasamy

---

# 🤝 Contributing

Contributions, issues, and feature requests are welcome.
Feel free to fork the repository and submit pull requests.

---

# 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

<div align="center">

### 🌍 Building Healthier Lives Through Conversational AI

⭐ If you like this project, consider giving it a star.

Made with ❤️ by Team WellBot

</div>
