# venv-notes

There are several ways of creating a virtual environment.  

I typically make a base environment with `conda` where I specify which version of python I am using.  My goal is to match the version of python with what the deployment machine has available.  For example, google and heroku only support specific versions of python when deploying to their free services.  

I have started using `pipenv` as my project virtual environment since I find it easy to install packages and have them added to a Pipfile and the virtual enviroment is stored in a central location on my computer (root inside the .virtualenvs/ folder)  

On occasions I have used `virtualenv` but I did not like it as much as `pipenv`.  The main difference is that `virtualenv` creates a repo folder called `env` that holds the environment defintions.  Also creating the `Pipfile` is not as easy.  

> I have provided a mostly complete example of the project flow found in [example-app.md](example-app.md).  



## References:  

[Recreating Environments](https://kiwidamien.github.io/save-the-environment-with-conda-and-how-to-let-others-run-your-programs.html)

