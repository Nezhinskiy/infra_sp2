# API_YAMDB

### Как запустить проект:

```bash
git clone https://github.com/Nezhinskiy/infra_sp2
cd infra_sp2
cd api_yamdb
```

```bash
python3 -m venv venv
source /venv/bin/activate (source /venv/Scripts/activate - для Windows)
python -m pip install --upgrade pip

pip install -r requirements.txt

cd infra

docker-compose up -d --build

docker-compose exec web python manage.py makemigrations reviews

docker-compose exec web python manage.py migrate

docker-compose exec web python manage.py createsuperuser

docker-compose exec web python manage.py collectstatic --no-input

docker-compose exec web python manage.py dumpdata > dumpPostrgeSQL.json

docker-compose down -v
```

### Шаблон наполнения .env расположенный по пути infra/.env
```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```

### Документация API YaMDb
Документация доступна по эндпойнту: http://localhost/redoc/


### [Ссылка на репозиторий, в котором велась разработка проекта в команде](https://github.com/Nezhinskiy/api_yamdb)