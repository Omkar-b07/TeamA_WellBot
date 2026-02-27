# Use Python 3.10 as the base image
FROM python:3.10-slim

ENV PYTHONUNBUFFERED=1

WORKDIR /app

COPY backend/web_api/requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt

COPY backend/web_api/ /app/
COPY frontend/ /frontend/

EXPOSE 5000

CMD ["gunicorn", "--bind", "0.0.0.0:5000", "--workers", "2", "--threads", "4", "app:app"]
