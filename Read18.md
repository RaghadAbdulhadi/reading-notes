# Django 

## To install django for normal python distributions 
    pip install django

- You should activate the virtual environment
- When you install django it installs a command line tool called *django-admin*

#############################################################

### To create a project:
    django-admin startproject first-project

## The main parts of a django project

#### __init__.py

A blank python script that due to its special name lets Python know that this directory can be treated as a package.

#### settings.py

This is where all the settings of the project will be stored.

#### urls.py

This is a python script that will store all the URL patterns for the project. (The different pages of the web application)

#### wsgi.py

This is a python script that acts as the Web Server Gateway Interface(*a simple calling convention for web servers to forward requests to web applications or frameworks written in the Python programming language*). Helps us deploy our web app to production.

#### manage.py

This is a python script that will be associates with many commands as we build our web app

##### Import Error
So we should change the path 
- command: which python
- copy the path
- Change the interpreter path from the vs code

### To run the server:

    python manage.py runserver

**Due to the error that appears when we run the server**

**What is a migration?**

A migration allows you to move databases from one design to another, this is also reversible, so we can migrate our database

**Django project is a collection of applications and con igurations that when combined together will make up the full web application (the website running with Django)**

**A Django application is created to perform a particular functionality for the entire web application.**

**Django Apps can be plugged to aother projects to reuse them**

################################################################

### To create an application

    python manage.py startapp first_app
    (inside the django project)


## The main parts of a django application

#### __init__.py

A blank python script that due to its special name lets Python know that this directory can be treated as a package.

#### admin.py

You can register your models here which Django will then use them with Django's admin interface.(Django provides a default admin interface which can be used to perform create, read, update and delete operations on the model directly)

#### apps.py

Here you can place application specific configuration

#### models.py

Here you store the application's data models
(Where we will specify the relations between the data)

#### tests.py

Tests functions that are used to test the code

#### views.py

This is where you have functions that handle requests and return responses

#### Migrations folder

This directory stores database specific information as it relates to the models


- After creating a new app
- Go to settings.py of the project and add the app to the installed apps list

#############################################################

### To create a view
- Go to the app to the views.py file
- Import from django.http import HttpResponse
- Create a function for each view you will add
- Each view takes atleast one argument
- Each view must return a HttpResponse object
- To see the view when we run the server we have to map the view to the urls.py file
- In the urls patterns list add a path to the list
    path('index/', views.index, name='index')
    index is the name of the function so views.index targets the function we added

## Mapping urls

Using include() function from django.conf.urls

## Templates 
- Templates are a key part to understanding how django works and interacts with the website
- Templates contain the static parts of an html page (parts that are always the same)
- Template tags, which have their own syntax, this syntax allows you to inject dynamic content that your Django App's views will produce, effecting the final HTML

- Create template directory then a subdirectory for each specific app's templates(inside of your top level directory)
