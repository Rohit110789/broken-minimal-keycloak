FROM python:3.8-slim

WORKDIR /var/www

COPY requirements.txt .

RUN python3 -m pip install -r requirements.txt

COPY app.py .

ENV PYTHONUNBUFFERED=1

ENTRYPOINT ["gunicorn", "app:app", "--bind=0.0.0.0:8000", "--workers=4", "--log-level=debug", "--reload"]
