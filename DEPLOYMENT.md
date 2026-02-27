# Deployment Guide (Docker Compose)

This project runs as 3 services:
- `flask_app` (web/API)
- `rasa` (NLU dialog server)
- `action_server` (custom actions)

## 1. Prerequisites on server

- Ubuntu 22.04+ (or equivalent Linux VM)
- Docker + Docker Compose plugin installed
- Ports open: `5000`, `5005`, `5055` (or put behind reverse proxy)

## 2. Clone and configure

```bash
git clone https://github.com/Omkar-b07/TeamA_WellBot.git
cd TeamA_WellBot
cp .env.example .env
```

Edit `.env`:
- Set strong `SECRET_KEY`
- Set strong `JWT_SECRET_KEY`
- Keep cookie flags `true` when using HTTPS

## 3. Start services

```bash
docker compose up --build -d
```

Check status:

```bash
docker compose ps
docker compose logs -f flask_app
docker compose logs -f rasa
docker compose logs -f action_server
```

## 4. Health checks

- Flask health: `http://<server-ip>:5000/health`
- Rasa health: `http://<server-ip>:5005/status`

## 5. Seed data (one-time)

If needed, load CSV data into DB:

```bash
docker compose exec flask_app python load_knowledge.py
docker compose exec flask_app python load_db.py
```

## 6. Recommended production setup

- Put `flask_app` behind Nginx/Caddy with HTTPS
- Keep `JWT_COOKIE_SECURE=true`
- Move from SQLite to PostgreSQL for multi-instance reliability
