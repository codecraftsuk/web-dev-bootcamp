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
            {{ csrf_token }}
            {{ form.as_p }}
            <button type="submit">Save</button>
        </form>
    </div>
</body>
</html>
```

**Note for students:** In the code block above, replace the inner `{}` with `%%` for the `csrf_token` like in previous examples with the for loops. The brackets have been changed to avoid conflicts in this documentation.

In this code, The `method` attribute specifies the HTTP method used to submit the form data to the server, which in this case is `POST`. The `{{ csrf_token }}` template tag outputs a hidden input field with a CSRF token, which is a security measure to prevent Cross-Site Request Forgery (CSRF) attacks. The `{{ form.as_p }}` template tag outputs the form fields as paragraphs (`<p>` elements)


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

## 2.8 Editing and Deleting Existing Data

The first thing we need to do to be able to edit or delete our data is to create buttons that will allow us to do so. Hence, in `home.html` where we rendered the data headings and rows, we can add another header called `actions` and two buttons called `edit` and `delete` as shown below:

```html
templates/app/home.html

<thead>
  <tr>
    <th>Title</th>
    <th>Created At</th>
    <th>Completed</th>
    <th>Actions</th>
  </tr>
</thead>
<tbody>
  {% for todo in todos %}
  <tr>
    <td>{{ todo.title }}</td>
    <td>{{ todo.created_at }}</td>
    <td>{{ todo.completed }}</td>
    <td>
      <a class="edit-btn" href="">Edit</a>
      <a class="delete-btn" href="">Delete</a>
    </td>
  </tr>
  {% endfor %}
</tbody>
```

This will create another column in the data table with two buttons.

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/buttons.png">
</p>

At the very moment, thw two buttons do not do anything as the `href` is not redirecting to any links. Hence, we need to create two views that can handle both the edit and delete functionality.

```python
todoapp/views.py

def delete(request, id):
    # Retrieve the Todo object with the specified id
    todo = Todo.objects.get(id=id)
    
    # Check if the request method is POST
    if request.method == 'POST':
        # If it is, delete the Todo object from the database
        todo.delete()
        # Redirect to the home page after deletion
        return redirect('home')
    
    # If the request method is GET, display a confirmation page
    context = {'todo': todo}
    return render(request, 'app/delete.html', context)
```

The function takes two arguments: the request object, which contains information about the current request being made, and the `id` of the todo item that we want to delete.

First, we retrieve the todo item with the specified `id` from the database using the `get()` method on the Todo model.

Next, we check whether the request method is a POST request. If it is, it means that the user has submitted a form to delete the todo item. In this case, we call the `delete()` method on the todo object to remove it from the database, and then redirect the user to the home page using the `redirect()` function.

If the request method is not POST, it means that the user is trying to view the confirmation page to delete the todo item. In this case, we render the `delete.html` template and pass in the todo object as context so that we can display information about it on the confirmation page.

Likewise, the same can be done for the edit button:

```python
todoapp/views.py

def edit(request, id):
    # Retrieve the Todo object with the specified id
    todo = Todo.objects.get(id=id)
    
    # Check if the request method is POST
    if request.method == 'POST':
        # If it is, create a form instance with the POST data and the retrieved Todo object
        form = TodoForm(request.POST, instance=todo)
        
        # Check if the form is valid
        if form.is_valid():
            # Save the form data to the database
            form.save()
            # Redirect to the home page after submission
            return redirect('home')
    
    # If the request method is GET, display the form with the retrieved Todo object pre-filled
    else:
        form = TodoForm(instance=todo)
    
    # Pass the form and Todo object to the template as context
    context = {'form': form, 'todo': todo}
    return render(request, 'app/edit.html', context)
```
The `edit` function retrieves a `Todo` object with a specific `id` from the database and displays a form to edit its data. If the request method is POST, the function creates a form instance with the POST data and the retrieved `Todo` object, validates the form data, saves it to the database, and redirects to the home page. If the request method is GET, the function displays the form with the retrieved `Todo` object pre-filled. The function passes the form and `Todo` object to the template as context.

Once the views for both edit and delete are created, corresponding URLs need to be defined to map the user's request to the appropriate view.

```python
todoapp/urls.py

urlpatterns = [
    path('', views.home, name='home'),
    path('form/', views.form, name='form'),
    path('edit/<int:id>/', views.edit, name='edit'), 
    path('delete/<int:id>/', views.delete, name='delete'),
]   
```

The URL pattern for edit view is defined as` edit/<int:id>/`, where `<int:id>` captures the `id` of the `Todo` object to be edited. Similarly, the URL pattern for delete view is defined as `delete/<int:id>/,` where `<int:id>` captures the `id` of the `Todo` object to be deleted.

When a URL is requested that matches either of these URL patterns, Django will call the corresponding view function with the `id` captured from the URL pattern as an argument. This `id` is used by the view function to retrieve the relevant `Todo` object from the database, and perform the appropriate action (update or delete) based on the request method.

To provide a user interface for editing or deleting a Todo item, HTML templates need to be created and rendered when the corresponding buttons are clicked by the user. These templates will display the necessary information and provide forms for submitting any changes made by the user.

```html
templates/app/edit.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Edit</title>
</head>
<body>
  <section id="hero">
    <div class="content-wrapper">
        <h1>Edit Todo</h1>
    </div>
    </section>
    
    <form method="post">
      {{ csrf_token }}
      {{ form.as_p }}
      <input type="submit" value="Update">
      <a href="{% url 'home' %}"><input type="button" value="Return"></a>
    </form>
</body>
</html>
```

Note: make the same adjustment with the `csrf_token`, where the inner brackets are `%`.

```html
templates/app/delete.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Delete</title>
</head>
<body>
  <h3>Are you sure you want to delete the todo: {{ todo.title }}?</h3>
  <form method="post">
        {% csrf_token %}
        <input type="submit" value="Confirm">
        <a href="{% url 'home' %}"><input type="button" value="Deny"></a>
    </form>
</body>
</html>
```
The final step to make sure that when the buttons are clicked on `home.html`, they redirect to their respective changes, is to edit the href for each button created in `home.html`

```html
templates/app/home.html

{% for todo in todos %}
<tr>
  <td>{{ todo.title }}</td>
  <td>{{ todo.created_at }}</td>
  <td>{{ todo.completed }}</td>
  <td>
    <a class="edit-btn" href="{% url 'edit' todo.id %}">Edit</a>
    <a class="delete-btn" href="{% url 'delete' todo.id %}">Delete</a>
  </td>
</tr>
{% endfor %}
```

Now, when the edit and delete buttons are clicked, the following pages are rendered:

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/edit-todo.png">
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/delete-todo.png">
</p>

Now we have full CRUD functionality, where we can `create` new data using our form, `read` data on our home page which reads from our database, `update` and `delete` our exisitng data.

The last part left for this website is to be able to navigate from our homepage, which renders the `Todos` to our form, which allows us create new `Todos`. To do this, we will create a nav bar that will allow us to access each page and the easiest way to ensure the nav bar is rendered on every single page is to create a `base.html` adn extend the html elements needed for a nav bar onto all of our other html pages.

## 2.9 Creating a Nav Bar and Extending HTML

In the `templates/app` folder, create a html file called `base.html`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% block title %}{% endblock %}</title>
</head>
<body>
    <nav>
        <div class="nav-wrapper content-wrapper">
            <div class="logo"><a href="{% url 'home' %}">TODO APP</a></div>
            <div class="nav-links">
                <a href="{% url 'form' %}">ADD TODO</a>            
            </div>
        </div>
    </nav>
    <main>
        {% block content %}
        {% endblock %}
    </main>
</body>
</html>
```

The `base.html` file is used to create a base template that can be extended by other templates. It contains the basic structure of the HTML file, such as the `<!DOCTYPE html>` declaration, the `html`, `head`, and `body` tags. The template language used in Django is used to define `blocks` of content that can be overridden by other templates that extend the base template.

For example, the `{% block title %}{% endblock %}` block in the head section can be overridden by a child template by defining a new block with the same name. Similarly, the `{% block content %}{% endblock %}` block in the main section can be overridden to define the main content of the page.

When a child template extends the `base.html` file, it essentially inherits all of its content and can override any block defined in the parent template. This makes it easier to reuse common elements of a website across multiple pages. For example, if you have a header and footer that appear on every page, you can define them in the `base.html` file and then extend that file in each child template to include the header and footer on every page. In this scenario, we will havea a nav bar in every section.

To extend this `base.html` file to the rest of the html files created, simply add the following to each html file:

```html
{% extends "app/base.html" %}
{% block content %}

{% endblock %}
```

where, in between block content and end block, the webpage will be enclosed in. An example of this is shown below:

```html
templates/app/home.html

{% extends "app/base.html" %}
{% block content %}
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
                <th>Actions</th>
              </tr>
            </thead>
            <tbody>
              {% for todo in todos %}
              <tr>
                <td>{{ todo.title }}</td>
                <td>{{ todo.created_at }}</td>
                <td>{{ todo.completed }}</td>
                <td>
                  <a class="edit-btn" href="{% url 'edit' todo.id %}">Edit</a>
                  <a class="delete-btn" href="{% url 'delete' todo.id %}">Delete</a>
                </td>
              </tr>
              {% endfor %}
            </tbody>
        </table>          
    </div>
</body>
</html>
{% endblock %}
```

Now, we should expect that a nav bar to be rendered on this page, followed by the `home.html` content.

<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/navbarextended.png">
</p>

Follow this template and add it to each html page to get the nav bar onto every page.

Now, the functionality of the application is finished, all is left is to add some styling using css.

## 3.0 Adding CSS

We can add CSS styling to each page of the website as we wish, but for this demo, we will only add styling to the nav i.e. the `base.html` file. From this, we will learn how to add css to any web page.

The css files are contained inside the `static/css` folder as that is where will look for these files. Hence, for the `base.html` file, we will create a `base.css` file to go with it. 

After creating the css file, we will need to link it to the `base.html` file so that the styling can be rendered onto that page. That can be done by simply loading the static file onto the html page as follows:

```html
templates/app/base.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>{% block title %}{% endblock %}</title>
    {% load static %}
    <link rel="stylesheet" type="text/css" href="{% static 'css/base.css' %}">
</head>
<body>
    <nav>
        <div class="nav-wrapper content-wrapper">
            <div class="logo"><a href="{% url 'home' %}">TODO APP</a></div>
            <div class="nav-links">
                <a href="{% url 'form' %}">ADD TODO</a>            
            </div>
        </div>
    </nav>
    <main>
        {% block content %}
        {% endblock %}
    </main>
</body>
</html>
```

In the head of the `base.html` file, we added the Django template for loading a static file alongside the link tag to link the stylesheet to the html. 

Now that the files are linked, let's add some styling to the nav bar.

```css
static/css/base.css

body {
    padding: 0;
    margin: 0;
    font-family: 'Poppins', sans-serif;
  }

.content-wrapper {
    max-width: 900px;
    margin: 0 auto;
}

nav {
    background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(75,74,186,1) 49%, rgba(76,76,189,1) 50%, rgba(48,62,97,1) 100%);
    padding: 1em;
    display: flex;
    align-items: center;
    justify-content: space-between;
    
  }
  
  nav a {
    color: #f1f1f1;
    text-decoration: none;
    margin-right: 1em;
    font-size: .9rem;
    font-weight: 500;
    transition: all 0.3s ease-in-out;
  }

  .logo a {
    float: left;
    font-size: 1.3em;
    font-weight: bold;
    display: flex;
    align-items: center;
    justify-content: center;
    transition: all 0.3s ease-in-out;
  }

  nav a:hover, nav .btn:hover, .logo:hover {
    opacity: 0.7;
  }
  
  .nav-wrapper {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100%;
  }
  
  .nav-links {
    display: flex;
    align-items: center;
    justify-content: center;
  }
```

By adding this styling and adding the following class to the main tag i.e. `<main class="content-wrapper">` tag in the `base.html` file, we have the follwoing styled page:

```html
templates/app/base.html

<main class="content-wrapper">
    {% block content %}
    {% endblock %}
</main>
```
<p align="center">
  <img src="https://raw.githubusercontent.com/codecraftsuk/web-dev-bootcamp/main/docs/_media/week_08_django/basecss.png">
</p>

The class `content-wrapper` created a max-width margin of 900px, hence, we also added it to the main tag to make sure the content is aligned with the nav bar. 

Now that is the website complete!


