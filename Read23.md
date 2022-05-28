# Guide to Docker
## Linux Containers

Docker is really just Linux containers which are a type of virtualization.

Docker containers are like apartments: they share common infrastructure like plumbing and heating, but come in various sizes that match the exact needs of an owner.

## Containers vs Virtual Environments
Virtual environments are used to isolate Python software packages locally. We can create an isolated box for individual projects so one can use Python 2.7 and Django 1.5 while another can use Python 3.5 and Django 2.1 on the same computer. Virtual environments are great.

But…virtual environments can only isolate Python packages. They still rely on a global, system-level installation of Python albeit they can refer to the proper version. So when we use Python 2.7 in a project, we’re pointing to an installation of Python 2.7 on the computer itself, not actually within the virtual environment.

Also we can’t run a production database or other services within virtual environments so compared to Docker containers they are far more limited.

## Install Docker

To install Docker we need to download the desktop app on our computer and create a free account. The initial download of Docker might take some time to download. It’s a big file. Feel free to stretch your legs at this point!

Once Docker is done installing we can confirm the correct version is running. It should be at least version 19.

Docker Compose is an additional tool that is automatically included with Mac and Windows downloads of Docker. However if you are on Linux, you will need to add it manually. You can do this by running the command sudo pip install docker-compose after your Docker installation is complete.

To confirm Docker installed correctly we can run our first command docker run hello-world. This will download an official image and then run the container.

## Images and Containers

Images and containers are the two fundamental concepts to grasp when you start with Docker. An image is a snapshot in time of what a project contains. A container is a running instance of the image.

### Images

First create a local directory on your computer for our code. I’ve chosen to make a code folder on my Desktop (I’m using an Apple computer) and then a python3.7 folder within that.

Now we need to define the image with a Dockerfile. This is similar to a Pipenv or a requirements.txt file; it is a list of all the requirements needed to build our image. It is simpler to have them all in one place rather than install each manually line-by-line.


### Library Website

Django REST Framework works alongside the Django web framework to create web APIs. We cannot build a web API with only Django Rest Framework. It always must be added to a project after Django itself has been installed and configured.

### Traditional Django
Navigate to the existing code directory on the Desktop and make sure you are not in a current virtual environment. You should not see (.venv) before the shell prompt. If you do, use the command deactivate to leave it. Make a new directory called library, create a new virtual environment, activate it, and install Django.

A traditional Django website consists of a single project with multiple apps representing discrete functionality. Let’s create a new project with the startproject command called django_project. Don’t forget to include the period . at the end which installs the code in our current directory. If you do not include the period, Django will create an additional directory by default.

The manage.py file is not part of django_project but is used to execute various Django commands such as running the local web server or creating a new app. Let’s use it now with migrate to sync the database with Django’s default settings and start up the local Django web server with runserver.

Open a web browser to http://127.0.0.1:8000/ to confirm our project is successfully installed and running.

### First app

The next step is to add our first app which we’ll call books. Stop the local server by typing Control+c and then run the startapp command plus our app name to create it.

Typically, developers will also create an urls.py file within each app for routing.

Before moving on we must add our new app to the INSTALLED_APPS configuration in the django_project/settings.py

### Models

This is a basic Django model where models is imported from Django on the top line and a new class, called Book, extends it. There are four fields: title, subtitle, author, and isbn. We also include a __str__ method so that the title of a book will display in readable format in the admin later on. Note that an ISBN is a unique, 13-character identifier assigned to every published book.

python manage.py makemigrations

python manage.py migrate

### Admin
python manage.py createsuperuser

update our books app’s admin.py file.

python manage.py runserver

Navigate to http://127.0.0.1:8000/admin and log in. This brings up the admin homepage.

### Views

The views.py file controls how the database model content is displayed. Since we want to list all books we can use the built-in generic class ListView. Update the books/views.py file.

### URLs

We need to set up both the project-level urls.py file and then one within the books app. When a user visits our site they will initially interact with the django_project/urls.py file so let’s configure that one first. Add the include import on the second line and then a new path for the books app.

### Templates

The final step is to create our template file that controls the layout on the actual web page. We have already specified its name as book_list.html in our view. There are two options for its location: by default the Django template loader will look for templates within our books app in the following location: books/templates/books/book_list.html. We could also create a separate, project-level templates directory instead and update our django_project/settings.py file to point there.

### Tests

Tests are a vital part of writing software and we should add them now before moving on to the API portion of this project. We want to be sure that the Book model works as expected as well as our view, urls, and template. Our books app already has an empty books/tests.py file that we can use for this



