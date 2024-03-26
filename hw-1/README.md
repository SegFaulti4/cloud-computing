# Практическая работа №1 "Основы контейнерной виртуализации"

Для сборки и запуска приложения использовался Docker Compose версии `v2.25.0`

Сборка приложения:
```bash
docker compose build
```

Первый запуск приложения (с заполнением БД):
```bash
docker compose --profile init up
```

Удаление приложения и данных БД:
```bash
docker compose down --volumes
```
