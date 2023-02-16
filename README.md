### 1 Описание

Данная работа сделана на основании выданного технического задания
Проект YaMDb собирает отзывы пользователей на произведения. Сами произведения в Y
aMDb не хранятся, здесь нельзя посмотреть фильм или послушать музыку.
C помощью программы Docker Descop создан контейнер с готовым набором данных

### 2 Установка

# 1 Клонировать репозиторий и перейти в него в командной строке:
git clone git@github.com:A60874022/infra_sp2.git


# 2 Системные переменные:

1 Необходимо в папке infa создать файл .env c переменными окружения:
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=postgres # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД 

# 3 Выполнить миграции:

docker-compose exec web python manage.py migrate

# 4 Создать суперпользователя:

docker-compose exec web python manage.py createsuperuser


### 5 Собрать статику:
docker-compose exec web python manage.py collectstatic --no-input

### 5 Запускить проект:

1 выполнить команду docker-compose up

После запуска проекта документация и примеры запросов приведены адресу http://127.0.0.1:8000/redoc/ 
