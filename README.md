# Django-Commands
List of Django commands
1. First install Python in your machine and add path to your environment variables
2. Next install virtual env wrapper using "pip install virtualenvwrapper-win"
3. Then create a new folder in your machine, let's say on desktop "mkdir VirtualEnv"
4. Next "cd virtualEnv"
5. Next create virtual env "mkvirtualenv env_name"
6. Now to activate your venv on windows use this "workon env_name" then press enter.
7. To activate venv on git bash use this "source ./env_name/Scripts/activate" and press enter.
8. Now install Django using "pip install django"
9. Check django is installed using "django-admin --version"
10. Now create a new folder on desktop "mkdir projects"
11. Next "cd projects" then start a django project using "django-admin startproject project_name"
12. Next "cd project_name" now create an app "python manage.py startapp app_name"
13. Now your directory will be like
14. Projects
     1. project_name
        1.1 project_name
         1.11 __pycache__ # this is pycache folder
         1.12 __init__.py
         1.13 asgi.py
         1.14 settings.py
         1.15 urls.py
         1.16 wsgi.py
     1.2 app_name
         1.21 migrations # this is migration folder"
         1.22 __init__.py
         1.23 admin.py
         1.24 apps.py
         1.25 models.py
         1.26 tests.py
         1.27 views.py
        manage.py
15. Now to start django developement server use this "python manage.py runserver"
16. Then a development server start on this link http://127.0.0.1:8000/ if you want to change the server port number then do this "python manage.py runserver 5000" here 5000 is a port number.
17. To exit the server just press ctrl+c in command line
18. If you create any models in models.py then do this first register those models in admin.py and then do migrations using this "python manage.py makemigrations" after this do migrate by isng this "python manage.py migrate"
19. Then create super user using these "python manage.py createsuperuser", then fill details like Username, Email address, Passeord, and confirm password.
20. After this again start the development server and add admin at the end of the link http://127.0.0.1:8000/admin to access admin panel and use the super user credentials to login.

