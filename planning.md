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
1. projects/admin.py --- register Project model in the admin


### ProjectListView
1. in projects/views.py create ProjectListView ✔️
1. in projects/urls.py register the view for a path in URLPATTERNS ✔️
1. register the PROJECTS paths with the TRACKER project in tracker/urls.py ✔️
    1. add the RedirectView to urlpatterns ✔️
1. create the project/list.html ✔️
1. Protect the list view for the Project model so that only a person that has logged in can access it ✔️
    1. Change the queryset of the view to filter the Project objects where *members equals the logged in user* ✔️


### Login Page
1. register LoginView in accounts/urls.py ✔️
    1. import:  from django.contrib.auth.views import LoginView ✔️
1. include url patterns from accounts app in tracker project ✔️
1. in tracker/settings.py add:  LOGIN_REDIRECT_URL = "home" to the last line in the file ✔️
1. create a login.html file:  accounts app -> create templates folder -> create registration folder -> create login.html ✔️
    1. create a POST form ✔️


### Logout 
1. in accounts/urls.py import LogoutView & register LogoutView path in urlpatterns ✔️
1. in tracker/settings.py add:  LOGOUT_REDIRECT_VIEW="login" ✔️


### Signup
1. In accounts/views.py create signup function ✔️
    1. import:  from django.contrib.auth.forms import UserCreationForm ✔️
    1. use the create_user method in your function, ✔️
        1. use form = UserCreationForm -- import:  from django.contrib.auth.models import User
        1. use the login function -- import:  from django.contrib.auth import login
1. in accounts/templates/registration, create signup.html ✔️
1. in accounts/urls.py add signup to URLPATTERNS ✔️