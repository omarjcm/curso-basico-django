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

python manage.py shell

##########################################################################
# Importacion de los modelos
from polls.models import Question, Choice

# Llamado de todos los registros de un modelo
Question.objects.all()

from django.utils import timezone
# Creacion de un nuevo registro
q = Question(question_text="¿Cual es el mejor curso de la UPS?", pub_date=timezone.now())

# Guardado del nuevo registro
q.save()

Question(question_text="¿Cuál es la mejor Universidad del Ecuador?", pub_date=timezone.now()).save()
Question(question_text="¿Cuál es la mejor carrera?", pub_date=timezone.now()).save()

import os
os.system('cls')

Question.objects.all()
Question.objects.get(pk=1)
Question.objects.get(pk=2)
Question.objects.get(pk=3)

Question.objects.get(pub_date__year = timezone.now().year)

Question.objects.filter(question_text__startswith='¿Cual')
Question.objects.filter(pub_date__year = timezone.now().year)

q = Question.objects.get(pk=1)
q.choice_set.all()
q.choice_set.create(choice_text='Programacion Hipermedial', votes=0)
q.choice_set.create(choice_text='Programacion y Plataformas Web', votes=0)
q.choice_set.create(choice_text='Plataformas Web', votes=0)

q.choice_set.all()
q.choice_set.count()

Choice.objects.filter(question__pub_date__year==timezone.now().year())

##########################################################################

python manage.py createsuperuser


