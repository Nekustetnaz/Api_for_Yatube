# Проект «API для сервиса Yatube»
### Описание
Проект «API для сервиса Yatube» предоставляет возможность взаимодействия с социальной сетью Yatube при помощи API запросов. 
### Основные функции
- Публикация записей;
- Комментирование записей;
- Подписка на авторов
### Технологии
Python 3.7, Django 2.2, DRF, JWT + Djoser
### Запуск проекта
- Клонировать репозиторий и перейти в него в командной строке:
```git clone git@github.com:Nekustetnaz/api_final_yatube.git```
```cd api_final_yatube```
- Cоздать и активировать виртуальное окружение:
```python3 -m venv env```
* Если у вас Linux/macOS
    ```source env/bin/activate```
* Если у вас windows
    ```source env/scripts/activate```
```python3 -m pip install --upgrade pip```
- Установить зависимости из файла requirements.txt:
```pip install -r requirements.txt```
- Выполнить миграции:
```python3 manage.py migrate```
- Запустить проект:
```python3 manage.py runserver```
### Работа с API для неавторизованных пользователей
```
GET api/v1/posts/ - получить список всех записей;
GET api/v1/posts/{id}/ - получение определенной записи по id;
GET api/v1/groups/ - получение списка всех сообществ;
GET api/v1/groups/{id}/ - получение информации о сообществе по id;
GET api/v1/{post_id}/comments/ - получение всех комментариев к публикации;
GET api/v1/{post_id}/comments/{id}/ - получение одного комментария к публикации по id
```
### Работа с API для авторизованных пользователей
Для авторизованных пользователей доступны все возможности из предыдущего раздела, а также:
```
POST /api/v1/posts/ - создание публикации;
PUT /api/v1/posts/{id}/ - изменение публикации;
PATCH /api/v1/posts/{id}/ - частичное изменение публикации;
DEL /api/v1/posts/{id}/ - удаление публикации;
POST /api/v1/posts/{post_id}/comments/{id}/ - создание комментария;
PUT /api/v1/posts/{post_id}/comments/{id}/ - изменение комментария;
PATCH /api/v1/posts/{post_id}/comments/{id}/ - частичное изменение комментария;
DEL /api/v1/posts/{post_id}/comments/{id}/ - удаление комментария;
GET /api/v1/follow/ -  получение списка подписок пользователя;
POST /api/v1/follow/ - подписка на автора;
```
изменение публикаций и комментариев доступно только авторам.
### Регистрация нового пользователя
```
POST /api/v1/users/ - создание нового пользователя;
POST /api/v1/jwt/create/ - получение JWT токена;
```
### Примеры API запросов
- создание публикации:
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
- создане комментария:
```
{
  "text": "string"
}
```
- оформление подписки:
```
{
  "following": "string"
}
```
