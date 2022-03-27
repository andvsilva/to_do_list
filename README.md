# To-Do Lists Using Python and Django

In this project I will build a Django to-do list manager ```to_do_list```. This work is based on the [Real Python Tutorial](https://realpython.com/django-todo-lists/) that is great resource to learn and sharp your skills in python.

## TODO's

- Create a web app using Django
- Build a data model with one-to-many relationships
- Use the Django admin interface to explore your data model and add test data
- Design templates for displaying your lists
- Leverage class-based views to handle the standard database operations
- Control the Django URL dispatcher by creating URL configurations

## Project Overview

- **Step 1**: Set Up Your Virtual Environment and Django
```bash
# create folder
$ mkdir ~/repo/to_do_list
$ cd ~/repo/to_do_list

# activate the virtual environment
$ python -m venv venv
$ source venv/bin/activate
```

- **Step 2**: Install and Test Django
```bash
python -m pip install django=="3.2.9"
```
(**NOTE**: Maybe in the future you should install the last version of Django)

You can use the python interpreter to verify if Django has been installed correctly.

```bash
$ python                               
Python 3.9.7
>>> import django
>>> django.get_version()
'3.2.9'
>>> exit()
(venv) (base) 
```

One good idea when you are developing a project is to use ```freeze``` to get the list of packages and versions installed. We use the file text name ```requirements.txt```:

```bash
python -m pip freeze > requirements.txt
```

- **Step 3**: Create Your Django To-Do App

```bash
django-admin startproject todo_project .
```
- **Step 4**: Get Started on Your Django To-Do List App

```bash
django-admin startapp todo_app
```

After start the app is necessary to configure your project, you need to ```'todo_app'``` to the file ```todo_project/settings.py```

Below where you need add the ```'todo_app'```:

```bash
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'todo_app',  # ADDED TODO APP! <<<<
]
```

The DATABASES is set up by default to use the ```sqlite3``` database.

- **SECRET_KEY** is important if you plan to put your app on a public server. Django generates a new random SECRET_KEY for every new project. **You can ignore it for now**.

The second thing to do is to modify the file in the project folder call ```urls.py```, located in the ```todo_project/urls.py```

Here How to do this:

```bash
# file - todo_project/urls.py
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path("admin/", admin.site.urls),
    path("", include("todo_app.urls")) # Add path to the app
]
```

You will create that app-level URL configuration file now. Open a new file in your editor and save it in the ```todo_app``` directory under the name ```urls.py```:


```bash
# todo_app/urls.py
urlpatterns = [
]
```

You can test your work so far by starting the Django development server:


```bash
$ python manage.py runserver
Watching for file changes with StatReloader
Performing system checks...

System check identified no issues (0 silenced).

You have 18 unapplied migration(s). Your project may not work properly until you apply the migrations for app(s): admin, auth, contenttypes, sessions.
Run 'python manage.py migrate' to apply them.
March 27, 2022 - 14:56:07
Django version 3.2.9, using settings 'todo_project.settings'
Starting development server at http:....
```

After this command you need to open the browser tip your localhost at the URL and you will see the image below and the message ```The install worked successfully! Congratulations!```:


![](gifs/django_runserver_success.gif)

Django’s default page provides links to lots of helpful documentation. 

You’ve completed all the standard setup tasks for a new Django app. It’s time to start coding the unique features of your application.

- **Step 5**: Design Your To-Do Data

**Resources**

- [Django documentation](https://docs.djangoproject.com/en/4.0/)