mkdir premiosups
cd premiosups
python -m venv venv
.\venv\Scripts\activate

pip install django
django-admin startproject premiosupsapp

cd premiosupsapp
python manage.py runserver

python manage.py startapp polls

Listado de la base de datos
https://en.wikipedia.org/wiki/List_of_tz_database_time_zones

pip install psycopg2

python manage.py makemigrations polls
python manage.py migrate
