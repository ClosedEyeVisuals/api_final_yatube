# REST API для социальной сети Yatube

## Возможности:
- Публикация постов и комментариев к ним
- Подписка на других пользователей
- Аутентификация по JWT-токену

## Проект реализован с помощью:
![](https://img.shields.io/badge/Python-3.9.12-lightblue)
![](https://img.shields.io/badge/Django-3.2.16-darkgreen)
![](https://img.shields.io/badge/Django_REST_framework-3.12.4-blue)
![](https://img.shields.io/badge/Django_REST_framework_simplejwt-5.3.1-red)
![](https://img.shields.io/badge/Djoser-2.2.3-orange)

## Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone <ссылка на репозиторий>
```

```
cd <...>
```

Cоздать и активировать виртуальное окружение:

```
python -m venv env
```

```
source venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python manage.py runserver
```

### Примеры запросов к API:

1. Получение токена для аутентификации:
```
POST /api/v1/jwt/create/
```
```json
{
  "username": "string",
  "password": "string"
}
```
Ответ:
```json
{
  "refresh": "string",
  "access": "string"
}
```
2. Получение списка всех постов:
```
GET /api/v1/posts/
```
Ответ без пагинации:
```json
[
    {
    "id": 1,
    "author": "string",
    "text": "string",
    "pub_date": "2024-09-17T20:41:29.648Z",
    "image": "string",
    "group": 3
    },
  
    {
    "id": 2,
    "author": "string",
    "text": "string",
    "pub_date": "2024-09-18T20:41:29.648Z",
    "image": null,
    "group": 1
    }
]
```
Ответ с учётом пагинации:
```json
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2024-09-16T17:58:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```
3. Подписка на пользователя:
```
POST /api/v1/follow/
```
```json
{
  "following": "string"
}
```
Ответ:
```json
{
  "user": "string",
  "following": "string"
}
```
>Полная документация доступна после запуска проекта по относительному url-адресу /redoc/.

### Автор

[github](https://github.com/ClosedEyeVisuals)
