# Kittygram #

[![Kittygram Workflow](https://github.com/svitlanasheptur/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/svitlanasheptur/kittygram_final/actions/workflows/main.yml)

Kittygram - это веб-приложение для обмена фотографиями и видео с котиками. Пользователи могут создавать аккаунты, загружать медиафайлы, ставить лайки и оставлять комментарии.

### Стек технологий ###

- Backend: Python, Django, Django REST Framework
- Frontend: React, HTML, CSS
- База данных: PostgreSQL
- Контейнеризация: Docker, Docker Compose
- CI/CD: GitHub Actions

## Как развернуть проект ##

Клонируйте репозиторий:

```
git clone https://github.com/yandex-praktikum/kittygram_final.git
```
Перейдите в директорию проекта:

```
cd kittygram_final
```

Cоздайте и активируйте виртуальное окружение:

```
python3 -m venv env
```

* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

Установите зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполните миграции:

```
python3 manage.py migrate
```

Запустите проект:

```
python3 manage.py runserver
```

Создайте файл .env в корневой директории проекта и заполните его следующими переменными:

DB_HOST=db
DB_PORT=5432

POSTGRES_DB=имя_базы_данных
POSTGRES_USER=имя_пользователя
POSTGRES_PASSWORD=пароль

SECRET_KEY=ваш_секретный_ключ
DEBUG=False
ALLOWED_HOSTS=localhost,127.0.0.1

Запустите проект с помощью Docker Compose:

```
docker-compose up -d --build
```

Выполнение миграций и сбор статических файлов:

```
docker-compose exec backend python manage.py migrate
docker-compose exec backend python manage.py collectstatic --no-input
```

Откройте веб-браузер и перейдите по адресу http://localhost (или другому адресу, указанному в переменных окружения ALLOWED_HOSTS) для доступа к приложению Kittygram.

### Автор ###
Проект разработан Светланой Шептур