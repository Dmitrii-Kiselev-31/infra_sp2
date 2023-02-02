# API_yatube 


Сервис YaMDb
Проект YaMDb собирает отзывы пользователей на произведения. Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий может быть расширен администратором.

## Техническое описание проекта

К проекту по адресу http://localhost/redoc/ подключена документация **API YaMDb**.
В ней описаны возможные запросы к API и структура ожидаемых ответов.
Для каждого запроса указаны уровни прав доступа: пользовательские роли, которым разрешён запрос.

## Технологии:
* Python 3.7
* Django 2
* Docker
* Nginx

## Установка:
1. Клонируйте репозиторий на локальную машину.
```git clone https://github.com/Dmitrii-Kiselev-31/infra_sp2```
2. Установите виртуальное окружение в папке проекта.
```
cd infra_sp2
python -m venv venv
```
3. Активируйте виртуальное окружение.
```source venv\Scripts\activate```
4. Установите зависимости.
```
python -m pip install --upgrade pip
pip install -r api_yamdb\requirements.txt
```
## Запуск проекта в контейнерах
1. Перейдите в директорию `infra/`, заполните файл .venv_example и после этого переименуйте его в .env
2. Выполните команду:
```docker-compose up -d --build```
3. Для остановки контейнеров из директории `infra/` выполните команду:
```docker-compose down -v```
4. Загрузка данных для примера из папки `infra/`
```docker-compose exec web python manage.py loaddata fixtures.json```

Выполнить миграции и собрать статику
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
```

## Проверка работы приложения
Для проверки работы приложения, при запущенном виртуальном окружении, из корня директории
выполните команду `pytest`

## Автор:

[Дмитрий Киселев](https://github.com/Dmitrii-Kiselev-31)