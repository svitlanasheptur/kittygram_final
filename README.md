# Kittygram #

Kittygram - это веб-приложение для обмена фотографиями и видео с котиками. Пользователи могут создавать аккаунты, загружать медиафайлы, ставить лайки и оставлять комментарии.

### Стек технологий ###

- Backend: Python, Django, Django REST Framework
- Frontend: React, HTML, CSS
- База данных: PostgreSQL
- Контейнеризация: Docker, Docker Compose
- CI/CD: GitHub Actions

## Как развернуть проект ##

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/yandex-praktikum/kittygram_final.git
```

```
cd kittygram_final
```

Cоздать и активировать виртуальное окружение:

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

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```
## Как заполнить env ##

Создайте файл .env в корневой директории проекта и заполните его следующими переменными:

DB_HOST=db
DB_PORT=5432

POSTGRES_DB=имя_базы_данных
POSTGRES_USER=имя_пользователя
POSTGRES_PASSWORD=пароль

SECRET_KEY=ваш_секретный_ключ
DEBUG=False
ALLOWED_HOSTS=localhost,127.0.0.1

##  Как работать с репозиторием финального задания ##

### Что нужно сделать ###

Настроить запуск проекта Kittygram в контейнерах и CI/CD с помощью GitHub Actions

### Как проверить работу с помощью автотестов ###

В корне репозитория создайте файл tests.yml со следующим содержимым:
```yaml
repo_owner: ваш_логин_на_гитхабе
kittygram_domain: полная ссылка (https://доменное_имя) на ваш проект Kittygram
taski_domain: полная ссылка (https://доменное_имя) на ваш проект Taski
dockerhub_username: ваш_логин_на_докерхабе
```

Скопируйте содержимое файла `.github/workflows/main.yml` в файл `kittygram_workflow.yml` в корневой директории проекта.

Для локального запуска тестов создайте виртуальное окружение, установите в него зависимости из backend/requirements.txt и запустите в корневой директории проекта `pytest`.

### Чек-лист для проверки перед отправкой задания ###

- Проект Taski доступен по доменному имени, указанному в `tests.yml`.
- Проект Kittygram доступен по доменному имени, указанному в `tests.yml`.
- Пуш в ветку main запускает тестирование и деплой Kittygram, а после успешного деплоя вам приходит сообщение в телеграм.
- В корне проекта есть файл `kittygram_workflow.yml`.

### Автор ###
Проект разработан Светланой Шептур