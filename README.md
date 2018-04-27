# Core Data Modules Usage Demonstrator
A simple example project which shows how to import and use a cleaning function from
[CoreDataModules](https://github.com/AfricasVoices/CoreDataModules).

### GitHub Keys
Building this project, either locally or in Docker, requires ssh access to a private AVF GitHub repository,
CoreDataModules. 
For instructions on how to generate a new ssh key, and how to add this key to GitHub, refer to the
[instructions provided by GitHub](https://help.github.com/articles/connecting-to-github-with-ssh/).
You must do this in order for the following steps to work.

### Running Locally
1. Install [pipenv](https://docs.pipenv.org/#install-pipenv-today). 
The easiest way to do this is `$ brew install pipenv` or `$ pip install pipenv`. 
This project was developed with pipenv version 11.10.0. 

1. Install project dependencies with: `$ pipenv sync`.

1. Run this project with `$ pipenv run python demo.py`.

### Running in Docker
1. Install Docker. This project was tested with Docker version 18.03.0-ce, build 0520e24 on macOS.

1. Run `$ sh docker-run.sh <path_to_GitHub_key>` e.g. `$ sh docker-run.sh ~/.ssh/gh_rsa`.

### Steps Undertaken to Produce this Project
These instructions describe how to set-up a new project to be able to use CoreDataModules.

1. Install [pipenv](https://docs.pipenv.org/#install-pipenv-today). 
The easiest way to do this is `$ brew install pipenv` or `$ pip install pipenv`. 
This project was developed with pipenv version 11.10.0. 

1. Set-up a pipenv environment which uses the desired version of Python: `$ pipenv --python <version>`.
For example, for Python 2.7 use `$ pipenv --python 2.7`.

1. Install CoreDataModules as an application dependency: 
`$ pipenv install -e git+ssh://git@github.com/AfricasVoices/CoreDataModules.git@v0.1#egg=CoreDataModules`. 
Note that "@v0.1" informs pipenv to install the commit of CoreDataModules tagged as "v0.1". 
PyPI dependencies can be installed similarly to `pip install` e.g. `$ pipenv install numpy`.

1. Write an application which depends on CoreDataModules. For a trivial example, see `demo.py`.

1. Run your application with `$ pipenv run python <main_file.py>` e.g. `$ pipenv run python demo.py`.

For Docker builds, refer to `docker-run.sh` and `Dockerfile` for an example.
