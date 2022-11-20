# venv-notes

pip install pipenv

How to check to see how you have this installed.
Go to your app folder
pipenv shell

To exit type exit

pipenv install flask
pipenv install psycopg2
pipenv install psycopg2-binary
pipenv install flask-sqlalchemy
pipenv install gunicorn

Shift-ctrl-P
Select the right interpreter

Create templates folder with these files:
* index.html


Create static folder with these folders:
* css
* images
* js

Create app.py
use flask boilerplate

Create database

Create Heroku account
Install Heroku CLI

Create .gitignore
* .vscode
* __pycache__
* all other 

git init

heroku --version
heroku login

heroku create nameofyourchoosing

heroku addons:create heroku-postgresql:hobby-dev --app nameofyourchoosing

Get sql db address:
heroku config --app nameofyourchoosing

copy db url

Add url to flask app



touch Procfile
add:  web: gunicorn app:app

runtime.txt
add python-3.7.2  (check with heroku documentation )

Create requirements file
pip freeze > requirements.txt

git add . && git commit -m "intial deploy"

Go to deploy and read directions

something like:
heroku git:remote -a nameofyourchoosing

git push heroku master (or main)

heroku open - doesn't work yet


heroku run python
from app import db
db.create_all()
exit()

heroku pg:psql --app nameofyourchoosing

Now you can change the db
check if db is updated

select * from ????  


## References:  

[Recreating Environments](https://kiwidamien.github.io/save-the-environment-with-conda-and-how-to-let-others-run-your-programs.html)


