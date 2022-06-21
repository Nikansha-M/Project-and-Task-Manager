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


### Create Task Model in tasks/models.py and register in admin


### Project DetailView
1. in projects/views.py create class ProjectDetailView ✔️
    1. import:  from django.views.generic.detail import DetailView ✔️
1. in projects/urls.py register the view with the path "<int:pk>/" and the name "show_project" ✔️
1. Create detail.html
1. update list.html
    1. update to show num of tasks for a project ✔️
    1. include link from project name to detail view for that project ✔️


### Project CreateView
1. in projects/views.py create class ProjectCreateView
    1. will show the name, description, and members properties ✔️
1. if project successfully created, redirect to detail page for that project ✔️
1. in projects/urls.py register view with the path "create/" in the projects urls.py and the name
"create_project" ✔️
1. create create.html template ✔️
1. update list view (list.html) for Project to navigate to new create view ✔️


### Task CreateView
1. in tasks/views.py create a TaskCreateView
    1. fields = name, start date, due date, project, assignee (everything in the model except is completed)
    1. when view successfully handles form submission redirect to detail page of task's project
1. Register that view in the tasks app for the path "create/" and the name "create_task" in a new file named tasks/urls.py ✔️
1. Include the URL patterns from the tasks app in the tracker project with the prefix "tasks/" ✔️
1. HTML template to create a new task : tasks -> templates -> tasks -> create.html ✔️
1. Add link to create a task from Project detail page ✔️ 


### Task ListView
1. TaskListView so that user can only see tasks assigned to them. filter with assignee = logged in user ✔️
1. Register TaskListView in tasks/urls.py, for the path "mine/" and the name "show_my_tasks" in the tasks urls.py file ✔️
1. create tasks/list.html ✔️


### Allows user to update status on assigned task(s) from incomplete to complete
1. create TaskUpdateView in tasks/views.py, fields = is_completed ✔️
    1. when the view successfully handles a submission, redirect to "show_my_tasks" URL path, redirect to the "My Tasks" view (success_url property on a view class)
1. in tasks/urls.py register the view for the path "<int:pk>/complete/" and the name "complete_task" in the tasks urls.py file ✔️
1. NO HTML TEMPLATE for UpdateView! ✔️
1. modify tasks/list.html ✔️


### Install Markdownify
1. pip install django-markdownify ✔️
1. tracker/settings.py add markdownify to INSTALLED_APPS ✔️
    1. add the configuration setting to disable sanitation  ✔️
1. projects/detail.html load the markdownify template library:  {% load markdownify %} ✔️
    1. change p tag and {{ project.description }} to {{ project.description|markdownify }} ✔️
