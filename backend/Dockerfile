FROM python:3.9-slim

WORKDIR /app

# переменные окружения
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN pip install gunicorn==20.1.0

COPY requirements.txt ./

RUN pip install -r requirements.txt --no-cache-dir

COPY . .

# При старте контейнера запустить сервер разработки.
# CMD ["python", "manage.py", "runserver", "0:8000"]
CMD ["gunicorn", "--bind", "0.0.0.0:8080", "kittygram_backend.wsgi"]
