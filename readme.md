# initiallize django
___
* console: (myvenv) ~/blog web: `django-admin startproject mysite .`
* the directory structure looks like this:
    ```
    djangogirls
    ├── manage.py
    ├── mysite
    │   ├── asgi.py
    │   ├── __init__.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    ├── myvenv
    │   └── ...
    └── requirements.txt
    ```
# set up a database
___
* using the default database software: sqlite3
* create database for blog
  * console: (myvenv) ~/blog web: `python manage.py migrate`

# starting the web server
___
* console: (myvenv) ~/blog web: `python manage.py runserver`
# django model
___
* a model in django is a special kind of object-it is saved in the database.
* create an application
  * console: (myvenv) ~/blog web: `python manage.py startapp blog`
  * a new blog directory is created
  ```
  djangogirls
  ├── blog
  │   ├── admin.py
  │   ├── apps.py
  │   ├── __init__.py
  │   ├── migrations
  │   │   └── __init__.py
  │   ├── models.py
  │   ├── tests.py
  │   └── views.py
  ├── db.sqlite3
  ├── manage.py
  ├── mysite
  │   ├── asgi.py
  │   ├── __init__.py
  │   ├── settings.py
  │   ├── urls.py
  │   └── wsgi.py
  ├── myvenv
  │   └── ...
  └── requirements.txt
  ```
* create a blog post model in blog/models.py
* create tables for models in your database
  * console: (myvenv) ~/blog web: `python manage.py makemigrations blog`
  * console: (myvenv) ~/blog web: `python manage.py migrate blog`
# django admin
___
* To add, edit and delete the posts we've just modeled, we will use Django admin.
* To log in, you need to create a superuser - a user account that has control over everything on the site.
  * console: (myvenv) ~/blog web: `python manage.py createsuperuser`
  * 