# Використовуємо базовий образ Nginx
FROM nginx:alpine

# Встановлюємо робочу директорію в контейнері
WORKDIR /app

# Копіюємо файли фронтенду в стандартну директорію Nginx
COPY index.html /usr/share/nginx/html/index.html
COPY config.json /usr/share/nginx/html/config.json

# Відкриваємо порт 80
EXPOSE 80

# Запускаємо Nginx
CMD ["nginx", "-g", "daemon off;"]
