![Deploy](https://github.com/Spechaly/yamdb_final/actions/workflows/yamdb_workfolow.yml/badge.svg)

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

### Сайт можно посетить по ссылке http://158.160.27.187:

### Шаблон ENV файла расположен по пути infra/.env:
```
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql 
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД
```
### Для запуска приложения в контейнерах необходимо выполнить команду docker-compose up -d --build находясь в директории (infra_sp2/infa) с docker-compose.yaml: 
- docker-compose exec web python manage.py migrate    Выполняем миграции 
- docker-compose exec web python manage.py createsuperuser    Создаем суперппользователя 
- docker-compose exec web python manage.py collectstatic --no-input    Собираем статику со всего проекта 
- docker-compose exec web python manage.py dumpdata > dump.json    Для дампа данных из БД 

### Для заполнения базы данными выполняем команду, находясь в дирректории (infra_sp2/infa) с docker-compose.yaml: 
- docker cp dump.json <id>:app/ 
- docker-compose exec web python manage.py loaddata dump.json 

### Автор: Балуев Евгений