# How to restart:
    You are trying to add a non-nullable field 'bidder' to bids without a default; we can't do that (the database needs something to populate existing rows).

    rm  your_app/migrations/*  !!don't delete the __init__.py
    rm db.sqlite3
    python manage.py makemigrations
    python manage.py migrate

# Create super user
    python manage.py createsuperuser

# kill port 8000
    fuser -k 8000/tcp

# pylint-django
    pip install pylint-django
    And add to VSC config:

    "python.linting.pylintArgs": [
        "--load-plugins=pylint_django"
    ],

# Django [Errno 13] Permission denied

    # ?whoami
    # ?sudo groupadd django
    # ?sudo usermod -aG django $USER
    # ?newgrp django

    sudo chown "$USER":"$USER" "<path>" -R
    sudo chmod g+rwx "<path>" -R

[File Permissions in Linux/Unix with Example](https://www.guru99.com/file-permissions.html)

