# Kittygram
## Бейджик об удачно завершенном workflow

[![Main Kittygram workflow](https://github.com/mirovata/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/mirovata/kittygram_final/actions/workflows/main.yml)

## Описание
Проект о наших домашних питомцах, вы можете зарегистрироваться и добавлять ваших питомцев, нужно указать имя и год рождения питомца, а так же добавить фотографии и указать его достижения.
## Технологии
- Docker
- Django
- Python
- PostgreSQL
- Gunicorn
- Javascript

## Как развернуть проект.

Клонировать репозиторий:

```
git@github.com:mirovata/kittygram_final.git
```
Создать и заполнить .env.Как заполнить с примерами ниже

C главной директории перейдите в папку backend и введите комманду.

```
cd backend
```
```
Docker build -t (ИМЯ ВАШЕГО БИЛДА) .
```

C главной директории перейдите в папку frontend и введите комманду.

```
cd frontend
```
```
Docker build -t (ИМЯ ВАШЕГО БИЛДА) .
```

C главной директории перейдите в папку nginx и введите комманду.

```
cd ngingx
```
```
Docker build -t (ИМЯ ВАШЕГО БИЛДА) .
```
В главной директории запустите docker compose.

```
docker compose up
```
Для полноценной работы соберите статику бэкенда.

```
docker compose exec backend python manage.py collectstatic
```
```
docker compose exec backend cp -r /app/collected_static/. /backend_static/static/
```

Чтобы завершить программу введите.

```
docker compose down
```
## Как заполнить .env
SECRET_KEY-Нужно указать секретный ключ для django.

**Пример**:SECRET_KEY='qolwvjicds5p53gvod1pyrz*%2uykjw&a^&c4moab!w=&16ou7' 

POSTGRES_DB-Нужно вести имя базы данных.

**Пример**:POSTGRES_DB=kitty

POSTGRES_USER-Нужно ввести имя пользоватя.

**Пример**:POSTGRES_USER=user

POSTGRES_PASSWORD-Нужно ввести пароль для базы данных.

**Пример**:POSTGRES_PASSWORD=123456

DB_PORT-Порт, по которому Django будет обращаться к базе данных.

**Пример**:DB_PORT=5432

DB_HOST-Адрес, по которому Django будет соединяться с базой данных.

**Пример**:DB_HOST=db

DEBUG-Для отладки.

**Пример**:DEBUG='True'

ALLOWED_HOSTS-Введите хосты для сайта.

**Пример**:ALLOWED_HOSTS='dom.ru,street.kz'
