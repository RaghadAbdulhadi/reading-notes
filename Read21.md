# Custom User Model

## AbstractUser vs AbstractBaseUser
There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser. In both cases we can subclass them to extend existing functionality however AbstractBaseUser requires much, much more work. 

## Custom User Model
**Creating our initial custom user model requires four steps:**

- update django_project/settings.py
- create a new CustomUser model
- create new UserCreation and UserChangeForm
- update the admin

- In settings.py we'll add the accounts app and use the AUTH_USER_MODEL config to tell Django to use our new custom user model in place of the built-in User model. We'll call our custom user model CustomUser.

- Within INSTALLED_APPS add accounts at the bottom. Then at the bottom of the entire file, add the AUTH_USER_MODEL config.

- Now update accounts/models.py with a new User model which we'll call CustomUser.

- We need new versions of two form methods that receive heavy use working with users. Stop the local server with Control+c and create a new file in the accounts app called forms.py.

- We'll update it with the following code to largely subclass the existing forms.

- Finally we update admin.py since the Admin is highly coupled to the default User model.

- And we're done! We can now run makemigrations and migrate for the first time to create a new database that uses the custom user model.

## Superuser
It's helpful to create a superuser that we can use to log in to the admin and test out log in/log out. On the command line type the following command and go through the prompts.

## Templates/Views/URLs
- Our goal is a homepage with links to log in, log out, and sign up. Start by updating settings.py to use a project-level templates directory.

- Then set the redirect links for log in and log out, which will both go to our home template. Add these two lines at the bottom of the file.

- Create a new project-level templates folder and within it a registration folder as that's where Django will look for the log in template. We will also put our signup.html template in there.

- Then create four templates using either the touch command on macOS or your text editor on Windows.

- Update the files

- Create a urls.py file in the accounts app using the touch command on macOS or your text editor on Windows.

- Last step is our views.py file in the accounts app which will contain our signup form.