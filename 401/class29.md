# Class 29 Reading Notes

### Django Custum User Model

***Setup***

To start, create a new Django project from the command line. We need to do several things:

- create and navigate into a dedicated directory called accounts for our code
- install Django
- make a new Django project called django_project
- make a new app accounts
- start the local web server

```
# Windows
> cd onedrive\desktop\code
> mkdir pages
> cd pages
> python -m venv .venv
> .venv\Scripts\Activate.ps1
(.venv) > python -m pip install django~=4.0.0
(.venv) > django-admin startproject django_project .
(.venv) > python manage.py startapp accounts
(.venv) > python manage.py runserver
```

**Note that we did not run migrate to configure our database. It's important to wait until after we've created our new custom user model before doing so.**

Creating our initial custom user model requires four steps:

- update django_project/settings.py
- create a new CustomUser model
- create new UserCreation and UserChangeForm
- update the admin

```
# django_project/settings.py
INSTALLED_APPS = [
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
    "accounts",  # new
]
...
AUTH_USER_MODEL = "accounts.CustomUser"  # new
```

```
# accounts/models.py
from django.contrib.auth.models import AbstractUser
from django.db import models

class CustomUser(AbstractUser):
    pass
    # add additional fields in here

    def __str__(self):
        return self.username
```

`(accounts) $ touch accounts/forms.py`

```
# accounts/forms.py
from django import forms
from django.contrib.auth.forms import UserCreationForm, UserChangeForm

from .models import CustomUser

class CustomUserCreationForm(UserCreationForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")

class CustomUserChangeForm(UserChangeForm):

    class Meta:
        model = CustomUser
        fields = ("username", "email")
```

```
# accounts/admin.py
from django.contrib import admin
from django.contrib.auth.admin import UserAdmin

from .forms import CustomUserCreationForm, CustomUserChangeForm
from .models import CustomUser

class CustomUserAdmin(UserAdmin):
    add_form = CustomUserCreationForm
    form = CustomUserChangeForm
    model = CustomUser
    list_display = ["email", "username",]

admin.site.register(CustomUser, CustomUserAdmin)
```

`
(.venv) > python manage.py makemigrations accounts
(.venv) > python manage.py migrate
`

### DjangoX

```
$ python -m venv .venv

# Windows
$ Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
$ .venv\Scripts\Activate.ps1

$ pipenv install
$ pipenv shell
(.venv) $ python manage.py migrate
(.venv) $ python manage.py createsuperuser
(.venv) $ python manage.py runserver
# Load the site at http://127.0.0.1:8000
```

**Docker**

```
# django_project/settings.py
DATABASES = {
    "default": {
        "ENGINE": "django.db.backends.postgresql",
        "NAME": "postgres",
        "USER": "postgres",
        "PASSWORD": "postgres",
        "HOST": "db",  # set in docker-compose.yml
        "PORT": 5432,  # default postgres port
    }
}
```

***The INTERNAL_IPS configuration in django_project/settings.py must be also be updated.***

```
# config/settings.py
# django-debug-toolbar
import socket
hostname, _, ips = socket.gethostbyname_ex(socket.gethostname())
INTERNAL_IPS = [ip[:-1] + "1" for ip in ips]
```

***And then proceed to build the Docker image, run the container, and execute the standard commands within Docker.***

```
$ docker-compose up -d --build
$ docker-compose exec web python manage.py migrate
$ docker-compose exec web python manage.py createsuperuser
# Load the site at http://127.0.0.1:8000
```

- Add environment variables. There are multiple packages but I personally prefer environs.
- Add gunicorn as the production web server.
- Update the EMAIL_BACKEND and connect with a mail provider.
- Make the admin more secure.
- django-allauth supports social authentication if you need that.

Reference [Django Custum User Model](https://learndjango.com/tutorials/django-custom-user-model)  
Reference [DjangoX](https://github.com/wsvincent/djangox)  

## Things I want to know more about

[Back to Home](../../README.md)
