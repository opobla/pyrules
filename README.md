# Pyrules
These are a series of tools based on coding conventions for code made 
in Python.

Some of these tools contain rules based on [PEP8][pep8], others are 
agreed upon by the Making Science development team itself.


# Installation
Installation of pre-commit must be done outside the Docker environment, 
i.e. by creating a virtualenv on your own host machine.

If you currently have a version installed on your host machine that does not correspond to the 
version of Python used in the Docker environment, it is advisable to use [pyenv][pyenv] to 
manage different versions of Python on your host machine.

Once the Python version is installed, we proceed to create a virtualenv 
in our local environment. We can create the virtualenv in this repository 
or we can create it in the repository where we are going to work.

If we create a local repository in another place, we have to copy all 
the files contained in this repository.

We create our virtualenv in our local environment, activate it and 
install the pre-commit package by executing the following commands:

    pip install pre-commit
    pre-commit install
    pre-commit install --install-hooks


# Methods of use
Once installed, there are two ways to launch hooks:

### Automatic
When attempting a commit, pre-commit will automatically launch all the 
hooks on the files to be committed.

### Manual - Recommended
Launching hooks before committing, via terminal.

1 - Run all hooks on the files to commit:

    pre-commit run

2 - Run a specific hook on the files to commit:

    pre-commit run {hook_id}
    pre-commit run black

hook_id is the value of the "id" field of each hook defined in `.pre-commit-config.yaml`.

3 - Run all hooks on all files in the repository:

    pre-commit run --all-files


### Ignore all hooks
If we want to skip hooks because we don't want to apply any rules, then 
we can run the following command:

    git commit --no-verify

With this command we can perform our commits without applying any 
pre-commit hooks.



[pep8]: https://peps.python.org/pep-0008/
[pyenv]: https://github.com/pyenv/pyenv
