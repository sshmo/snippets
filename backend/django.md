# Django

## Start a Project

```bash
    # Start a Project
    django-admin startproject <project name>

    # cd to <project name>
    cd <project name>

    # Create the application
    python manage.py startapp <app name>

    # Start using the files.
    python manage.py runserver #optional 0:8000 or 8080
```

```py
    
    # add urls.py to the <appname> folder
    from django.urls import path

    from . import views

    urlpatterns = [
        path('', views.index, name='index'),
    ]
```

## How to restart data

ERROR: You are trying to add a non-nullable field xxx to yyy without a default; we can't do that (the database needs something to populate existing rows).

``` bash
    rm  your_app/migrations/*  #!!don't delete the __init__.py
    rm db.sqlite3
    python manage.py makemigrations
    python manage.py migrate
    ## Create super user
    python manage.py createsuperuser
```

## kill port 8000

``` bash
    fuser -k 8000/tcp
```

## Add pylint-django to vscode

```bash
    pip install pylint-django
```

Edit .vscode/settings.json as following:

```json
    {    
        "python.linting.pylintArgs": [
            "--load-plugins=pylint_django"
        ],
    }
```

## Django [Errno 13] Permission denied (in WSL)

``` bash
    sudo chown "$USER":"$USER" "<path>" -R
    sudo chmod g+rwx "<path>" -R
```

[File Permissions in Linux/Unix with Example](https://www.guru99.com/file-permissions.html)

## auth.User.groups: (fields.E304) Reverse accessor for 'User.groups' clashes with reverse accessor for 'User.groups'

``` bash
    Add AUTH_USER_MODEL="your app name.User" in settings.py
```
