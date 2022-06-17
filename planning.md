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
