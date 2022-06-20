### Set Up Directory and GitLab Project

1. Cd into your projects directory
1. Fork and Clone the starter project to your Projects Directory:
    1. Since I already have a PROJECT ALPHA repository in GitLab, additional steps I need to  follow:
        1. Create a blank GitLab project, set visibility to Public, initialize **without** the README file
        1. While in your projects directory:  git clone https://gitlab.com/sjp19-public-resources/sjp-2022-april/project-alpha-apr.git(SJP)
        1. Cd PROJECT ALPHA
        1. Git remote rm origin (to remove the origin branch)
        1. Git remote add origin https://gitlab.com/Nikansha.M/project-alpha-june.git (clone the blank PROJECT ALPHA I created in my GitLab repository - the one without the readme file
        1. Git remote -v
            1. This will list out:
                1. origin  https://gitlab.com/Nikansha.M/project-alpha-june.git (fetch)
                1. origin  https://gitlab.com/Nikansha.M/project-alpha-june.git (push)
        1. git push --set-upstream origin main (this is a one-time command you’ll use)
1. Refresh GitLab page, you should now see the same commits that were made to the original SJP project on GitLab

TO PUSH YOUR PROJECT UP TO GITLAB, USE **git push origin main**


### Set Up Commands

1. Create Virtual environment:  **python -m venv .venv**
1. Activate Virtual environment:  **./.venv/Scripts/Activate.ps1**
1. Upgrade pip:  **python -m pip install --upgrade pip**
1. Install django:  **pip install django**
1. Install black:  **pip install black**
1. Install flake8:  **python -m pip install flake8**
1. Install djhtml:  **pip install djhtml**
1. Deactivate your virtual environment:  **deactivate**
1. Activate your virtual environment:  **./.venv/Scripts/Activate.ps1**
1. Use pip freeze to generate a requirements.txt file:  **pip freeze > requirements.txt**