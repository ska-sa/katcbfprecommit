# Python pre-commit Workflow
A Python, pre-commit workflow for auto-formatting code and checking for inconsistencies in style, design and complexity according to [PEP8]([https://www.python.org/dev/peps/pep-0008/](https://www.python.org/dev/peps/pep-0008/)) guidelines. It also checks for compliance with Python docstring conventions [PEP257](https://www.python.org/dev/peps/pep-0257/) and supports [mypy](https://mypy.readthedocs.io/en/stable/index.html) type checking if static typing is used.

The workflow runs whenever Python code is to be committed to a git repository using `git commit`.

## Initial Setup
To configure your project to use this automated Python workflow, copy the three configuration files, from this repository, to the top-level directory of your project's git repository:

* `.pre-commit-config.yaml` - configuration for _[pre-commit](https://pre-commit.com/)_. Specifies which git hooks will be run on `git commit`
* `pyproject.toml` - contains configuration for _[black](https://github.com/psf/black)_. The Uncompromising Python Code Formatter.
* `.flake8`  - configuration for _[flake8](https://flake8.pycqa.org/en/latest/)_. A tool for enforcing PEP8-based style guide for Python.

## Install Prerequisites
Although _black_, _flake8_, _mypy_ and _[pydocstyle](http://www.pydocstyle.org/en/5.0.2/index.html)_ are used, the only prerequisite is _**pre-commit**_ as the configuration file is set up so that when the pre-commit hooks are installed, all dependencies are automatically installed.

_pre-commit_ is a framework for managing git hooks.

Install _pre-commit_ by running:
```
pip install pre-commit
```

It recommended to list _pre-commit_ as a requirement for your project in requirements.txt (or requirements-dev.txt):
```
pre-commit
``` 

## Generate pre-commit Git Hooks
To generate the git hooks,  run the following in your project directory. Note that the `.pre-commit-config.yaml` file must be in your project directory **before** generating the git hooks.

```
pre-commit install
```

After this,  `pre-commit` will run automatically on `git commit` with the installed hooks.

