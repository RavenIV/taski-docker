## Описание проекта

Сайт для сохранения списка дел. Проект состоит из бэкенд-приложения на Django и фронтенд-приложения на React.
Проект для изучения основ DevOps, CI/CD.

## Стек

* Python (3.9)
* Django (3.2.3)
* Django REST framework (3.12.4)
* Djoser (2.1.0)
* Node.js
* React
* Docker
* Gunicorn

## Запустить проект

Установить [Docker](https://www.docker.com/).

Клонировать репозиторий и перейти в него в командной строке:

```
git clone <ssh link>
cd taski
```

Собрать контейнеры и запустить проект из корневой директории:

```
docker compose -f docker-compose.production.yml up -d
```

Выполнить миграции:

```
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```

Собрать и перенести статику бэкенда:

```
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
```

## Разработчики

* [Irina Vorontsova](https://github.com/RavenIV) - бэкенд
