# API для социальной сети Yatube

## Возможности:
- ### Публикация постов и комментариев к ним
- ### Подписка на других пользователей

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

Получение токена для аутентификации:
```
POST /api/v1/jwt/create/
```
Получение списка всех постов:
```
GET /api/v1/posts/
```
Подписка на пользователя:
```
POST /api/v1/follow/
```