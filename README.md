***Проект YaMDb***
![example workflow](https://github.com/github/docs/actions/workflows/main.yml/badge.svg)

---
### Описание:
Проект YaMDb собирает отзывы пользователей на произведения («Книги», «Фильмы», «Музыка»).
Пользователь может оставить развернутый отзыв с выставлением индивидуальной оценки.
У пользователей есть возможность комментировать отзывы

С помощью YaMDb возможно:
* Создавать отзыв на произведение
* Оставить комментарий на  отзыв автора
* Получение/добавление жанров, категорий и наименований произведений

---

### Стэк технологий:
Python, Django, Django Rest Framework, JWT, Swagger

---
### Шаблон наполнения env-файла:
* SECRET_KEY: Секретный ключ проекта. Задается в  settings проекта Django.
* DB_ENGINE: Тип базы данных. Используется PostgreSQL.
* DB_NAME: Наименование базы данных.
* POSTGRES_USER: Логин пользователя БД.
* POSTGRES_PASSWORD: Пароль пользователя БД.
* DB_HOST: Название контейнера с БД.
* DB_PORT: Порт используемый БД. По умолчанию 5432.

---
### Инструкция по запуску:
#### 1. Авторизоваться через консоль в Docker:
*sudo docker login -u <имя пользователя>*

#### 2. Скачайте образ с DockerHub:
*sudo docker pull bazilit/infra_sp2:v1.0.3*

#### 3. Проверьте наличие скаченного образа в системе:
*sudo docker images ls -a*

#### 4. Пройдите по пути infra_sp2/infra/ и запустите контейнер с данным образом:
*sudo docker-compose up -d --build*

#### 5. Проверьте, что все контейнеры запущены и имеют статус "up":
*sudo docker container ls*

#### 6. При успешном запуске, осуществите миграцию БД:
*sudo docker-compose exec web python manage.py migrate*

#### 7. По завершению миграции, создайте суперпользователя:
*sudo docker-compose exec web python manage.py createsuperuser*

#### 8. После, осуществите сбор файлов статики и медиафайлов внутри контейнера:
*sudo docker-compose exec web python manage.py collectstatic --no-input*

#### 9. Проверяем доступность сервиса. Зайдите в админку под суперпользователем и создайте жанры, категорию, отзыв о произведение:
*http://localhost/admin*

---
### Автор: *Шарковский А.*
*https://github.com/Bazilit*

---
