# API Yatube
### Описание
API для проекта Yatube - работа с постами, группами, комментариями и подписками.

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/needred/api_final_yatube
```

```
cd yatube_api
```

Cоздать и активировать виртуальное окружение:

```
python -m venv env
```

```
. venv/Scripts/activate
или
. venv/bin/activate
```

```
python -m pip install --upgrade pip
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
python manage.py runserver
```

### Примеры запросов к API:

Получить **список всех публикаций**:

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
