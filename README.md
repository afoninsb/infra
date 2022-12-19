
# API_YamDB

API_YamDB is a platform for film and literature lovers.


## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

```bash
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres_db
POSTGRES_USER=postgres_user
POSTGRES_PASSWORD=postgres_password
DB_HOST=db
DB_PORT=5432
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
  sudo docker-compose up -d --build
  sudo docker-compose exec web python manage.py migrate
  sudo docker-compose exec web python manage.py createsuperuser
  sudo docker-compose exec web python manage.py collectstatic --no-input
```

Go to the http://localhost/admin/ 

Enter into the database

```bash
  sudo docker-compose exec web python manage.py loaddata fixtures.json
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
