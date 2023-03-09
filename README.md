![example workflow](https://github.com/github/docs/actions/workflows/yamdb_workfolow.yml/badge.svg)

### Проект Yamdb_final предназначен для сбора отзывов на произведения, произведения делятся на категории, и на жанры, пользователи могут оставлять коментарии под произведениями.

### Стек с технологиями:
- Python 3
- DRF (Django REST framework)
- Django ORM
- Docker
- Gunicorn
- nginx
- PostgreSQL
- GIT

### Шаблон ENV файла расположен по пути infra/.env:
```
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql 
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД
```

### Автор: Балуев Евгений