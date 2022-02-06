# API Yatube
**API для проекта Yatube - работа с постами, группами, комментариями и подписками.**
* Создано несколько эндпойнтов для работы с постами, группами, комментариями и подписками.
* Настроены права доступа для пользователей, аутентификация через JWT.

### Технологический стек
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat&color=008080)](https://www.django-rest-framework.org/) [![JSON](https://img.shields.io/badge/-JSON-464646?style=flat&logo=JSON&logoColor=56C0C0&color=008080)](https://www.json.org/json-en.html) [![JWT](https://img.shields.io/badge/-JWT-464646?style=flat&color=008080)](https://jwt.io/) [![ReDoc](https://img.shields.io/badge/-ReDoc-464646?style=flat&color=008080)](https://redoc.ly/redoc/) [![Postman](https://img.shields.io/badge/-Postman-464646?style=flat&logo=Postman&logoColor=56C0C0&color=008080)](https://www.postman.com/)

### Запуск приложения
1) Клонировать репозиторий и перейти в него в командной строке:
    - ```git clone https://github.com/needred/api_final_yatube```
    - ```cd yatube_api```
2) Cоздать и активировать виртуальное окружение:
    - ```python -m venv env```
    - ```. venv/Scripts/activate``` или ```. venv/bin/activate```
    - ```python -m pip install --upgrade pip```
3) Установить зависимости из файла requirements.txt:
    - ```pip install -r requirements.txt```
4) Выполнить миграции:
    - ```python manage.py migrate```
5) Запустить проект:
    - ```python manage.py runserver```

### Примеры запросов к API
+ Получить **список всех публикаций**:
```
GET http://127.0.0.1:8000/api/v1/posts/
GET http://127.0.0.1:8000/api/v1/posts/?limit=2&offset=4
```

Добавление **новой публикации** в коллекцию публикаций:
```
POST http://127.0.0.1:8000/api/v1/posts/
{
    "text": "Текст поста",
    "image": "string",
    "group": 0
}
```

Частичное **обновление публикации** по id. Обновить публикацию может только автор публикации:
```
PATCH http://127.0.0.1:8000/api/v1/posts/2/
{
    "text": "Исправленный текст поста"
}
```

Получение **всех комментариев** к публикации:
```
GET http://127.0.0.1:8000/api/v1/posts/4/comments/
```
_где 4 - id публикации (post_id)_

Получение **комментария** к публикации по id:
```
GET http://127.0.0.1:8000/api/v1/posts/4/comments/1/
```

Получение информации о **сообществе** по id:
```
GET http://127.0.0.1:8000/api/v1/groups/3/
```

**Подписка пользователя** от имени которого сделан запрос на пользователя переданного в теле запроса:
```
POST http://127.0.0.1:8000/api/v1/follow/
{
    "following": "user234"
}
```

Получение **JWT-токена**:
```
POST http://127.0.0.1:8000/api/v1/jwt/create/
{
    "username": "user234",
    "password": "DLkt48NbvmC"
}
```
