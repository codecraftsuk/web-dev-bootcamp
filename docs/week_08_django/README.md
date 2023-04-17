# 1. Introduction to Django

## 1.1 What is Django

## 1.2 Setting up Django Environment


# 2. Fundamentals

## 2.1 Creating the Environment

Before creating a Django project, the first step would be to create a python virtual environment. Creating a Python virtual environment is a best practice for developing Python applications, especially when working on multiple projects or collaborating with others. The reason is because a virtual environment creates an isolated Python environment that allows you to install and manage packages independently of your system's global Python installation. This means that you can have different versions of Python and packages installed for each project without conflicting with each other. Additionally, you can install specific versions of packages, ensuring that the project is reproducible, amongst other benefits.

1. Open up a directory in which you want to create this application and run the following command in the terminal:

    ```bash
    python -m venv venv
    ```

    This will create a directory with the name `venv` that essentially has all the necessary files to run python.

2.  To activate this new virtual environment created, run the following command:

    ```bash
    source venv/bin/activate
    ```

    At this point, you should see `(venv)` appear at the beginning of your terminal prompt, indicating that you are now working within the virtual environment.

3. Now that the virtual environment is created, it is time to download the dependencies needed to run Django. It is good practise to create a `requirements.txt` file to put all your dependencies inside. Create a new text file as such and type `Django` and save.

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/django-requirements.png">
</p>

4. Install Django by running the following `pip` command:

    ```bash
    pip install -r requirements.txt
    ```

## 2.2 Creating a Django Project

In this demo, we will create a Todo application which allows the user to have CRUD (Create, Read, Update, Delete) functionalities. Hemce, the following instructions will demonstrate how to set up the Django project for this.

1. To create the Django environment, run the following command in the terminal:

    ```bash
    django-admin startproject todoproject
    ```

    TWhen you run the command `django-admin startproject todoproject`, it creates a new directory called `todoproject` (the name you provide as an argument) in your current working directory. The myproject directory contains the necessary files and directories for a basic Django project, such as `manage.py`, `settings.py`, and `urls.py`.

    - `manage.py` is a Python script that is used to run various commands related to your project, such as starting the development server, creating database tables, and running tests.

    - `settings.py` contains the configuration settings for your Django project, including database settings, installed apps, middleware, and more.

    - `urls.py` defines the URL routing for your project, mapping URLs to views in your application.

2. Change directories into the  `todoproject` and create the application for the Django project by running the following command:

    ```bash
    python manage.py startapp todoapp
    ```

    This will create a directory called `todoapp`, containing the following files:

    - `models.py`: This file is used to define the data models for your application.
    - `views.py`: This file is used to define the views (i.e. the functions that handle HTTP requests) for your application.
    - `urls.py`: This file is used to define the URL routing for your application, mapping URLs to views.
    - `admin.py`: This file is used to register your models with the Django admin interface.
    - `apps.py`: This file is used to define the configuration for your application.
    - `tests.py`: This file is used to write tests for your application.
    - A migrations directory: This directory is used to store database migration files, which are used to make changes to your database schema over time.

    Your codebase should look something like the following. Note: if you do not have the `urls.py` file, simply create it.


<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/django-boilerplate.png">
</p>

3. Now, we have to install our new app. To do this, we go to `settings.py`, scroll down to the list of `INSTALLED_APPS`, and add the name of our new application to this list, as shown below:

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/installapp.png">
</p>


4. To check if the Django project has been installed succesfully, you can start up the project as follows:

    ```bash
    python manage.py runserver
    ```

    This will start the deployment server, which can be accessed on `localhost:5000`. This development server is being run locally on your machine, meaning other people cannot access your website. You should see the following:

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/django-success.png">
</p>


At this point, all the boilerplate files have been created, and now it is time to start creating the todo application.

## 2.3 Creating Our First View

In Django, a view is a Python function that processes a web request and returns an HTTP response.

When a user visits a URL on a Django-powered website, Django uses a URL dispatcher to route the request to the appropriate view. The view then processes the request by performing any necessary database queries or calculations, and returns an HTTP response to the client. It is time to write our first view. In the `todoapp/views.py` file, write the following:

```python
todoapp/views.py

from django.http import HttpResponse

def index(request):
    return HttpResponse("Hello, world. This is the index function, which is rendering this string")
```

This is the simplest view possible in Django whereby we are returning a Http response with the string demosntrated. To call the view, we need to map it to a URL - and for this we need a URLconf which we have created in `todoapp/urls.py`.

In the` todoapp/urls.py` file include the following code:

```python
todoapp/urls.py

from django.urls import path

from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
```

In this code,  we are using the `path` function in Django to define URL patterns for a Django application. The next line in the code says that in this current directory, we want to import the views.py file. Finally, we are creating a URL pattern to map our view to a URL.

The next step is to link the `todoapp/urls.py` file to the `todoproject/urls.py` file. This is because the `todoproejct/urls.py` file is the URL config file for the Django project and what we have done so far is creatd a new application in the project and linked it to the project. However, we also need to link the app URLs to the main Django project. In the `todoproejct/urls.py`, you should see that there’s already a path called admin which we’ll go over later. For now, add the `todoapp` urls to the `todoproject` urls as follows:

```python
todoproject/urls.py

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include("todoapp.urls"))
]
```
This sets the default base URL i.e. `localhost:5000/` to be rendered onto the `todoapp` urls and in the `todoapp` urls, you can see that the path `''` also maps the index function to `localhost:5000/` i.e. the base url. If your Django proejct is running, refresh the page or go to `localhost:5000/`. If your Django project is not running, make sure you are in your virtual environment and run the server as shown above. The following page should be seen.

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/firstwebpage.png">
</p>

We now know that in Django, we can return a Http reponse and display a web page using a function created in the views file which is mapped onto a url in urls file. How about if we want to render a HTML page? To do this, the first step would be to create a directory called `templates` and in `todoapp` directory, another directory called `app`. Additionally, for the CSS, we can create a directory called `static` and inside it `css`, demonstrated as follows:


<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/directoryforhtmlcss.png">
</p>

## 2.4 Rendering a HTML Page

Before we create any files, for our todo app, we will have a homepage that will have the todo lists with CRUD functioanlity. Hence, we will rename the `index` function to `home` and edit the urls application urls file to rename our view function name. Now, we will create a html file in `templates/app` called `home.html`. In `home.html`, we will write some basic code which will display our home page.


```html
templates/app/home.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Home</title>
</head>
<body>
    <div id="header">
        <h1>My Todo List</h1>
    </div>

    <div id="list">
        <h2>Items:</h2>
    </div>
</body>
</html>
```


```python
todoapp/views.py

from django.shortcuts import render

def home(request):
    return render(request, 'app/home.html')
```



```python
todoapp/urls.py

from django.urls import path

from . import views

urlpatterns = [
    path('', views.home, name='home'),
]   
```

Outcome:

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/todowithhtmlrender.png">
</p>

The key difference in the view this time around is that rather than using hte `HttpResponse` function to render a string, we used the built in `render` to render the request and our html file. Now that we understand how to render a html page into our views, lets move onto how to add data into our views.


## 2.5 Creating a Django Model

In Django, a model is a Python class that represents a database table. Models define the structure of the data that will be stored in the database and provide an interface for accessing and manipulating that data.

Each attribute of a model class represents a field in the corresponding database table. The field types define the kind of data that can be stored in the database, such as text, numbers, dates, or relationships to other tables.

Django uses an Object-Relational Mapping (ORM) system to interact with the database, so developers can work with models as Python objects, rather than writing raw SQL queries.

We will create a Django model that store the following data from the user:

- `title` which is a CharField that represents the title of the todo item. It has a maximum length of 200 characters.

- `created_at` which is a DateTimeField that represents the date and time when the todo item was created. It is automatically set to the current date and time when a new todo item is created.

- `completed` which is a BooleanField that represents whether the todo item has been completed or not. It defaults to False.

In our `todoapp/models.py` file, we can create this table as follows:

```python
todoapp/models.py

from django.db import models

class Todo(models.Model):
    title = models.CharField(max_length=200)
    created_at = models.DateTimeField(auto_now_add=True)
    completed = models.BooleanField(default=False)
```

Once we have defined our model, we will need to create a migration to apply the changes to the database schema. This can be done using Django's manage.py command-line tool:

```bash
python manage.py makemigrations
python manage.py migrate
```

These commands will create a new migration file in the `todoapp/migrations` directory and apply the changes to the database. Hence, we have now created a new table in our database which will need to be populated by user input. Before that, we can verify the table has been made by using Django Admin.

## 2.6 Using Django Admin

Django Admin is a built-in application in the Django web framework that provides an administration interface for managing your application's data. It is a powerful tool that allows you to manage your project's data through a web-based interface, without needing to write any views or templates.

With the Django Admin, you can create, read, update, and delete records in your database, as well as perform more advanced tasks like running database queries, exporting data to CSV or Excel, and managing users and groups. The Django Admin automatically generates forms and tables based on your model definitions, making it easy to get started and reducing the amount of code you need to write. 

To use the Django Admin, follow these steps:

1. Make sure you have created a superuser account. You can create one by running the command `python manage.py createsuperuser`. This will prompt you for a username, email address (optional), and password.

2. Open your web browser and navigate to `http://localhost:8000/admin/`. You should see a login page.

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/adminlogin.png">
</p>

3. Log in with your superuser account credentials.

4. Once you are logged in, you should see the Django Admin dashboard. 

Before you can see your model in Django Admin, you need to register your mdoel by locating the `todoapp/admin.py` file and adding the following code:

```python
todoapp/admin.py

from django.contrib import admin
from .models import Todo

admin.site.register(Todo)
```

This registers the `Todo` model with the Django Admin so that it will appear in the interface. Now in the dashboard you should see the model as follows:


<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/modelinadmin.png">
</p>

From the admin page, we can add and edit data in our model. Let us add a row of data in our table and then render it onto our HTML page.

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/rowaddedadmin.png">
</p>

Now, let us modify our `home` view function so that we can read in this data from our `Todo` model.

```python
todoapp/views.py

from django.shortcuts import render
from .models import Todo

def home(request):
    # Retrieve all Todo objects from the database
    todos = Todo.objects.all()
    
    # Pass the todos to the template as context
    context = {'todos': todos}
    return render(request, 'app/home.html', context)
```

In the code above, we first import the `Todo` model from `models.py`. Then, we retrieve all `Todo` objects from the database using the `objects.all()` method. Finally, we pass the `todos` queryset to the template as context.

Now that our `home` view is able to retrieve all the data from the database, we need to be able to render the data onto our html page. Open `templates/app/home.html` and modfiy the code to the following:

```html
templates/app/home.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Home</title>
</head>
<body>
    <div id="header">
        <h1>My Todo List</h1>
    </div>

    <div id="list">
        <h2>Items:</h2>
        <table>
            <thead>
              <tr>
                <th>Title</th>
                <th>Created At</th>
                <th>Completed</th>
              </tr>
            </thead>
            <tbody>
              {% for todo in todos %}
              <tr>
                <td>{{ todo.title }}</td>
                <td>{{ todo.created_at }}</td>
                <td>{{ todo.completed }}</td>
              </tr>
              {% endfor %}
            </tbody>
        </table>          
    </div>
</body>
</html>
```

In this example, we have added a table with the table rows of our data that we have defined in our model. Then we rendered our data for each column using a for loop written in Django template, whereby we accessed each column after the `.`.

The double curly braces indicate that `todo.title`, `todo.created_at`, and `todo.completed` are dynamic variables that will be populated with values from the `Todo` model. When the template is rendered, these variables will be replaced with the actual values from the `Todo` objects that are passed to the template context. This will render the following onto our pagge:

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/firsttable.png">
</p>

So far, we have learned how to retrieve and display data from a model that we created using Django Admin. However, in a real-world application, we will be getting data from users through forms, which we will cover next.

## 2.7 Creating a Django Form

Django forms are a built-in part of the Django framework and are used to handle user input. They provide an easy and efficient way to collect data from users and validate it on the server side. Django forms are based on Python classes, and they can be used to create HTML forms that can be rendered in templates. They can also be used to create custom form fields, validate form data, and handle form submissions. Using Django forms can save a lot of time and effort by taking care of common form-handling tasks, such as data validation and sanitization, automatically.

The first step in creating our form is to create a `forms.py` file in our application. The following code demonstrated a form that takes in two fields; the title of the todo and the status of whether the todo is completed or not.

```python
todoapp/forms.py

from django import forms
from .models import Todo

class TodoForm(forms.ModelForm):
    class Meta:
        model = Todo
        fields = ['title', 'completed']
```

In this example, we import the `forms` module from Django, as well as the `Todo` model from our `models.p`y file. We then create a `TodoForm` class that inherits from `forms.ModelForm`.

Inside the `Meta` class, we specify the model to use (`Todo`) and the fields to include in the form (`title` and `completed`). This tells Django to automatically generate the form fields based on the model fields.

Now we can use this `TodoForm` class in our views to render the form and handle form submissions. In order to take data from the user using this form, we need to create a html file that allows us to do so. In `templates/app`, create a new file called `forms.html` and create the form as such:

```html
templates/app/forms.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Forms</title>
</head>
<body>
    <div id="header">
        <h1>Form</h1>
    </div>
    
    <div id="form">
        <h2>Create a new Todo</h2>
        <form method="post">
            {% token %}
            {{ form.as_p }}
            <button type="submit">Save</button>
        </form>
    </div>
</body>
</html>
```
Note: Replace `token` with `csrf_token`.

In this code, The `method` attribute specifies the HTTP method used to submit the form data to the server, which in this case is `POST`. The`csrf_token` template tag outputs a hidden input field with a CSRF token, which is a security measure to prevent Cross-Site Request Forgery (CSRF) attacks. The `{{ form.as_p }}` template tag outputs the form fields as paragraphs (`<p>` elements)


We also need to create a new function in our `views.py` file so that we can render the form onto our html page as well as our html page, as shown below:

```python
todoapp/views.py

from django.shortcuts import render, redirect
from .models import Todo
from .forms import TodoForm

def home(request):
    # Retrieve all Todo objects from the database
    todos = Todo.objects.all()
    
    # Pass the todos to the template as context
    context = {'todos': todos}
    return render(request, 'app/home.html', context)

def form(request):
    # Check if the request method is POST
    if request.method == 'POST':
        # Create a form instance with the POST data
        form = TodoForm(request.POST)
        # Check if the form is valid
        if form.is_valid():
            # Save the form data to the database
            form.save()
            # Redirect to the same page after submission
            return redirect('form')
    # If the request method is GET
    else:
        # Create a blank form instance
        form = TodoForm()

    context = {'form': form}
    return render(request, 'app/forms.html', context)
```

Our `form` function  handles a GET and a POST request for a form. Here is what this code does:

1. If the request method is POST, then it creates a `TodoForm` instance with the data in the POST request.
2. It checks if the form is valid. If the form is valid, it saves the form data to the database and redirects the user to the same page (`form`).
3. If the request method is GET, then it creates a blank `TodoForm` instance.
4. It creates a dictionary named `context` with the `form` instance as a value associated with the key `form`.
5. It renders the `forms.html` template with the `context` dictionary as a context instance.


Finally, we need to add a new url for the form page as follows:

```python
todoapp/urls.py

from django.urls import path

from . import views

urlpatterns = [
    path('', views.home, name='home'),
    path('form/', views.form, name='form'),
]   
```

Now, we can check out our new page by going to the url `localhost:5000/form/`


<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/form.png">
</p>

To see whether the form has worked and added a new row in our model, we can go back to the base url i.e. `localhost:5000/` and view the table.


<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/formcreateddata.png">
</p>

We have successfully created a form that allows for a user to input a todo which will be saved and displayed in the main todo table. However, what if we wanted to edit and delete the current todos that we have? We will explore that next.

