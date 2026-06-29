# Практическая работа. Docker. Создание сайта в контейнере


Структура проекта

my-site/
├── Dockerfile
├── index.html
└── README.md

Ход выполнения работы

1. Создание HTML-страницы

Был создан файл `index.html` со следующим содержимым:

```html
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>Мой сайт</title>
</head>
<body>
    <h1>Мой первый сайт в Docker</h1>
    <p>Сайт успешно запущен в контейнере Docker.</p>
</body>
</html>
```

2. Создание Dockerfile

Был создан файл `Dockerfile`:

```dockerfile
FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80
```

3. Сборка Docker-образа

```bash
docker build -t my-site .
```

4. Запуск контейнера

```bash
docker run -d --name my-site-container -p 8081:80 my-site
```

5. Проверка работы

После запуска контейнера сайт стал доступен по адресу:

http://localhost:8081


```bash
docker build -t my-site .
docker run -d --name my-site-container -p 8081:80 my-site
docker ps
docker stop my-site-container
docker rm my-site-container

```<img width="1197" height="639" alt="photo" src="https://github.com/user-attachments/assets/62972c89-b46a-4186-b145-f6150be2ec8c" />

