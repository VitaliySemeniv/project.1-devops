# 1. Використовуємо офіційний образ Python як базовий
FROM python:3.8-slim-buster

# 2. Встановлюємо оновлення системи та необхідні пакети
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# 3. Встановлюємо робочу директорію для нашого додатка
WORKDIR /app

# 4. Копіюємо файл requirements.txt у контейнер
COPY requirements.txt /app/requirements.txt

# 5. Встановлюємо Python-залежності
RUN pip install --no-cache-dir -r /app/requirements.txt

# 6. Копіюємо всі файли додатка у робочу директорію
COPY . /app

# 7. Налаштовуємо порти (зазвичай Django працює на 8000)
EXPOSE 8000

# 8. Команда для запуску додатка (замість цього може бути інший скрипт)
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
