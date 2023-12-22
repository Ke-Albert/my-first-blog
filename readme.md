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
  After creating an app, we need to tell django to use it. We do that in the file `mysite/settings.py`
  find the `INSTALLED_APPS` and add a line containing 'blog'.

* create a blog post model in blog/models.py
* create tables for models in your database
  
  We need to add our model to our database
  * First we need to let django know that we have some changes in our model.
  console: (myvenv) ~/blog web: `python manage.py makemigrations blog`
  * console: (myvenv) ~/blog web: `python manage.py migrate blog`
# django admin
___
* To add, edit and delete the posts we've just modeled, we will use Django admin. To make our
  model visible to the admin page, we need to register the model with `admin.site.register(Post)`.
* To log in, you need to create a superuser - a user account that has control over everything on the site.
  * console: (myvenv) ~/blog web: `python manage.py createsuperuser`
# deploy to pythonanywhere
___
# Django URLS
___
We want 'http://127.0.0.1:8000/' to be the home page of our blog and to display a list of posts.
We also want to keep the `mysite/urls.py file clean`, so we will import URLs from our blog application to the main `mysite/urls.py` file.
* We need to create a `blog/urls.py` file then import `views.py` to this file.
* So the relationship is views.py->urls.py->mysite/urls.py
# Django views
___
A view is a place where we put the "logic" of our application. It will request information from the model you created before and pass it to a template.
Views are placed in the view.py file.
# Dynamic data in templates
___
Till now, we have different pieces in place: the `Post` in `models.py`, we have `post_list` in
`views.py`, we have `blog/urls.py` in `mysite/urls.py`.


# Useful Links
___
Developing wonderful websites https://getbootstrap.com

If you want to know more about CSS Selectors https://www.w3schools.com/cssref/css_selectors.php

With many colors to choose https://www.colorpicker.com

Free Online courses https://www.freecodecamp.org/learn/
