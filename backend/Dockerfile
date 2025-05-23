FROM python:3.9-slim

WORKDIR /app

RUN pip install gunicorn==20.1.0

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# Создаем директории для статики и медиафайлов
RUN mkdir -p /app/static /app/media && \
    chmod -R 755 /app/static /app/media

CMD ["gunicorn", "kittygram_backend.wsgi:application", "--bind", "0.0.0.0:8000"] 