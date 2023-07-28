# "API for the Yatube service" project
### Description
Yatube is a service for publishing and commenting on posts.<br>
"API for the Yatube service" project rovides to interact with the Yatube using API requests.
### Main functions
- Publish posts;
- Comment on posts;
- Subscribe to authors.
### Run project
- Clone the repository:<br>
```git clone git@github.com:Nekustetnaz/api_final_yatube.git```
- Create and activate virtual environment:<br>
```python3 -m venv venv```
- Activate virtual environment for Linux/macOS:<br>
```source env/bin/activate```
- Activate virtual environment For Windows:<br>
```source env/scripts/activate```
- Install dependencies form the "requirements.txt" file:<br>
```pip install -r requirements.txt```
- Apply migrations:<br>
```python3 manage.py migrate```
- Run the project:<br>
```python3 manage.py runserver```
### API endpoints for unauthorized users
```
GET api/v1/posts/ - get a list of all posts;
GET api/v1/posts/{id}/ - get a post by id;
GET api/v1/groups/ - get a list of all groups;
GET api/v1/groups/{id}/ - get a group by id;
GET api/v1/{post_id}/comments/ - get all comments for post;
GET api/v1/{post_id}/comments/{id}/ - get a comment by id
```
### API endpoints for authorized users
All the features from the previous section are available for authorized users as well as:
```
POST /api/v1/posts/ - create a post;
PUT /api/v1/posts/{id}/ - completely update a post;
PATCH /api/v1/posts/{id}/ - partially update a post;
DEL /api/v1/posts/{id}/ - delete a post;
POST /api/v1/posts/{post_id}/comments/{id}/ - create a comment;
PUT /api/v1/posts/{post_id}/comments/{id}/ - completely update a comment;
PATCH /api/v1/posts/{post_id}/comments/{id}/ - partially update a comment;
DEL /api/v1/posts/{post_id}/comments/{id}/ - delete a comment;
GET /api/v1/follow/ -  get a list of user subscriptions;
POST /api/v1/follow/ - subscribe to authors
```
Updates to posts and comments are available only to authors.
### Sign up a new user
```
POST /api/v1/users/ - create new user;
POST /api/v1/jwt/create/ - get JWT token;
```
### Examples of API requests
- create post:
```
{
  "text": "string",
  "image": "string",
  "group": 0
}
```
- create comment:
```
{
  "text": "string"
}
```
- subscribe:
```
{
  "following": "string"
}
```
### Technologies
Python 3.7<br>
Django 2.2<br>
Django Rest Framework<br>
JWT + Djoser
### Author
Anton Akulov - https://github.com/Nekustetnaz
