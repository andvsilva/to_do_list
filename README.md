# To-Do Lists Using Python and Django

In this project I will build a Django to-do list manager ```to_do_list```. This work is based on the [Real Python Tutorial](https://realpython.com/django-todo-lists/).

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