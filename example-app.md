## Example Project

> Below is an example of terminal commands for a project that uses a pipenv environment, postgres database, flask and heroku.  

## Gitbash Tasks

>Ref: https://pipenv-fork.readthedocs.io/en/latest/basics.html  

- first ensure pipenv is installed
    ```
    pip install pipenv
    ```

- to determine if an environment has already be installed, check the root directory for a hidden folder typically called `.virtualenvs`.  The name of the environment is automatically generated and typically begins with the name of the folder holding the project.  

- you can also check for a `Pipfile` which would indicate that packages have already been added to the environment. 

- navigate to a location where you want to store the project and create a folder  
    ``` 
    mkdir <project_name>
    ```

- access the folder
    ```
    cd <project_name>
    ```

- to install packages and create/append Pipfile and to create/access the hidden `.virtualenvs` folder
    ```
    pipenv install <package>
    ```  

- to activate the environment
    ```
    pipenv shell
    ```

- to exit type `exit`

- install the following packages:  
    ```
    pipenv install flask
    pipenv install psycopg2
    pipenv install psycopg2-binary
    pipenv install flask-sqlalchemy
    pipenv install gunicorn
    ```

## VSCode Tasks
- in VSCode select the environment that was created.  
    ```
    Shift-ctrl-P to show pallette  
    Select the right interpreter
    ```

- open the folder containing the project  

- create `templates` folder with these files:
    * `index.html`

- create `static` folder with these folders:
    * `css`
    * `images`
    * `js`  

- create `app.py` in main project folder. The `app.py` will contain the flask boilerplate code  

- create `.gitignore`
    * `.vscode`
    * `__pycache__`
    * all other standard python template items


## Heroku Database Setup

1.  Create Heroku account
1.  Install Heroku CLI

- initiate repo in git bash
    ```
    git init
    ```
- login to heroku  
    ```
    heroku --version
    heroku login
    ```
- create heroku app
    ```
    heroku create nameofyourchoosing
    ```
- create heroku database
    ```
    heroku addons:create heroku-postgresql:hobby-dev --app nameofyourchoosing
    ```
- get sql db address
    ```
    heroku config --app nameofyourchoosing
    ```

- copy the provided db url.  This will need to be added to the connection string in the `app.py`.

- the heroko setup needs several files

- create Procfile
    *  `touch Procfile`
    * add on line to file:  `web: gunicorn app:app`

- create Runtime
    * `touch runtime.txt`
    * add `python-3.7.2`  (check with heroku documentation for valide python versions and try to match with the version being used in this environment)

- create requirements file
    *  `pip freeze > requirements.txt`

- prepare to push the repo to the heroku server
    * `git add . && git commit -m "intial deploy"`

- Go to the Heroku website and read the deployment directions.  These change occasionally.  

- the commands will be something like:  
    *  `heroku git:remote -a nameofyourchoosing`
    * `git push heroku master (or main)`  

- view the heroku web interface or terminal to view the status 

## Other commands that need documented  

heroku run python  
from app import db  
db.create_all()  
exit()  
heroku pg:psql --app nameofyourchoosing   

