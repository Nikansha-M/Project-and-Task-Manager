### Create Django Project = TRACKER
1. Create the django PROJECT named tracker:  
    1. **django-admin startproject tracker .** (don’t forget the dot!!!)


### Create Django Apps = ACCOUNTS, PROJECTS, TASKS
1. Create 3 django apps:  
    1. python manage.py startapp accounts
    1. python manage.py startapp projects
    1. python manage.py startapp tasks
1. add all 3 apps to Installed_Apps list in settings.py
    1. "accounts.apps.AccountsConfig",
    1. "projects.apps.ProjectsConfig",
    1. "tasks.apps.TasksConfig",
1. run & make migrations:
    1. python manage.py makemigrations
    1. python manage.py migrate
1. create a superuser
    1. python manage.py createsuperuser


### Create Projects model & register in admin
1. In projects/models.py:
    1. 3 attributes: name, description, members
    1. use __str__ method on name property
1. projects/admin.py:
    2. 
