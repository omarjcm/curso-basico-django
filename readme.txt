mkdir premiosups
cd premiosups
python -m venv venv
.\venv\Scripts\activate

pip install django
django-admin startproject premiosupsapp

cd premiosupsapp
python manage.py runserver

python manage.py startapp polls


