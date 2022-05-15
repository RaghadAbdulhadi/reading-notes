
## Models
- The most important part of any website is the ability to accept information from a user and input it into a database and retrieve information from a database and use it to generate content for the user
- Models are used to incorporate a database into a Django Project
- Django comes equipped with SQLite, but can connect to a variety of SQL engine backends
- To change the engine used go to the settings.py file and change the ENGINE parameter
- To create an actual model we use a class structure inside the models.py file
- This class object will be a subclass of Django's built-in class -> django.db.models.Model
- Each attribute of the class represents a field, which is just like a column name with constaints in SQL
- SQL operates like a giant table, with each column representing a field, and each row representing an entry
- Each column has a type of field such as (CharField, IntegerField, DateField, ..etc)
- Each field can have constraints such as (max_length)
- Table or Models relationships
    - Often models will refrence each other
    - We use PrimaryKey and ForeignKey for refrencing
    - PrimaryKey-> is a unique identifier for each row in a table
    - ForeignKey-> just denotes that the column coincides with a primary key of another table
- After we've set up the models we can migrate the database
    - This lets Django create a SQL database that correspond to the models we created
    - python manage.py migrate
    - python manage.py makemigrations appname
    - python manage.py migrate
- Register the models to the admin.py file 
    - from django.contrib import admin
    - from app.models import Model1, Model2
    - admin.site.register(Model1)
    - admin.site.register(Model2)
- With the models and database created we can use Django Admin interface to interact with the database
- Create a superuser
    - python manage.py createsuperuser

### Population Script
To create fake data to populate our models with
- poetry add Faker

### Models-Templates-Views Paradigm (MTV)

1. First: In the views.py file we import any models that we will need to use
2. Second: Use the view to query the model for data that we will need
3. Third: Pass results from the model to the template
4. Fourth: Edit the template so that it is ready to accept and display the data from the model
5. Map a URL to the view
