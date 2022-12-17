
# API_YamDB

API_YamDB is a platform for film and literature lovers.


## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

```bash
DB_ENGINE=django.db.backends.postgresql # указываем, что работаем с postgresql
DB_NAME=postgres_db # имя базы данных
POSTGRES_USER=postgres_user # логин для подключения к базе данных
POSTGRES_PASSWORD=postgres_password # пароль для подключения к БД (установите свой)
DB_HOST=db # название сервиса (контейнера)
DB_PORT=5432 # порт для подключения к БД 
```

## Run Locally

Clone the project

```bash
  git clone git@github.com:afoninsb/infra_sp2.git
```

Go to the '/infra/' in the project directory

```bash
  cd my-project/infra
```

Run commands

```bash
  docker-compose up -d --build
  docker-compose exec web python manage.py migrate
  docker-compose exec web python manage.py createsuperuser
  docker-compose exec web python manage.py collectstatic --no-input
```

Go to the http://localhost/admin/ 

Enter into the database

```bash
  sudo docker-compose exec web python manage.py import_csv
```
## Request examples
### Getting a list of all titles
```bash
http://localhost/api/v1/titles/
```
Response
```bash
[
{
"count": 0,
"next": "string",
"previous": "string",
"results": []
}
]
```
### Get review by id
```bash
http://localhost/api/v1/titles/{title_id}/reviews/{review_id}/
```
Response
```bash
{
"id": 0,
"text": "string",
"author": "string",
"score": 1,
"pub_date": "2019-08-24T14:15:22Z"
}
```
