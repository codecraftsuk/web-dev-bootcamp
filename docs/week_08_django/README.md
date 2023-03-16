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

    This will create a folder with the name `venv` that essentially has all the necessary files to run python.

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

    This will create a folder called `todoapp`, containing the following files:

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

## 2.3 Views

