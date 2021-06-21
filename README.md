# Project_fep
Projeto SEP - Sociedade Equestre Portuguesa

Instalation Part I - Configuration Base

Create github repositorie

Clone repositorie on VScode

Create virtual environment
py -m venv venv

Enter virtual environment
.\venv\scripts\activate

Create file requirements.txt
Necessary apps for project
py -m pip install -r .\requirements.txt

Create project Django (the project is created in base folder with dot in the final)
django-admin startproject <project_name> .

Initialize server manage.py
py .\manage.py runserver

Open link
http://127.0.0.1:8000/

Create database apps - migrate
py manage.py migrate

Edit <project_name>/settins.py
```python
LANGUAGE_CODE = 'pt'
TIME_ZONE = 'Europe/Lisbon'
```

github - 1st commit


Instalation - Part II - Configuration Users

Create app users
py manage.py startapp users

Edit <project_name>/settins.py
```python
INSTALLED_APPS = [
    # Users apps
    'users.apps.UsersConfig',
]

# User Model

AUTH_USER_MODEL = 'users.User'
```

Copy users/admin.py
Copy users/apps.py
Copy users/forms.py
Copy users/models.py

Delete db.sqlite3

Create model - makemigrations
py manage.py makemigrations

Create database apps - migrate
py manage.py migrate

Create super user
py manage.py createsuperuser

github - 2nd commit


Instalation - Part III - Configuration App

Create app
py manage.py startapp <app_name>

Edit <project_name>/settins.py
```python
INSTALLED_APPS = [
    # My apps
    '<app_name>.<(A)pp_name>Config',
]
```

Edit <app_name/>models.py
Edit <app_name/>admin.py
Edit <app_name/>views.py
Edit <project_name/>urls.py
Edit <project_name>/settins.py
```python
'DIRS': [ BASE_DIR / "templates" ],
```

Load fixtures to database
py manage.py loaddata <fixtures>
