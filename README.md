# Использование volume в docker
# volume позволяет сохранять настройки проекта при остановке контейнеров
## Python3 + Django проект + Postgres
### Как запустить проект:

- Установить Docker;
- Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/avetvoydrug/docker-volume-w-Django.git
```
```
cd docker-volume-w-Django
```
- Выполнить команды в терминале:
    - Сборка образа #Обратите внимание на точку после PROJECT_NAME
    ```
    docker-compose run django django-admin startproject <PROJECT_NAME> .
    ```
    - Запустить сервисы #после возможно потребуется открыть второй терминал
    ```
    docker-compose up
    ```
    - Выполнить миграции #чтобы создать таблицы пользователей
    ```
    docker-compose run django python manage.py migrate
    ```
    - Создать супер-пользователя #для доступа к админ панели
    ```
    docker-compose run django python manage.py createsuperuser
    ```
    - That's all the services is available right now on 
    ```
    localhost:8000/
    localhost:8000/admin/ # админ-панель
    ```
    - *Остановка контейнеров
    ```
    docker-compose down
    ```