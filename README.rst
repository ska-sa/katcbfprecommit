==========================
Python pre-commit Workflow
==========================

A Python, pre-commit workflow for auto-formatting code and checking for
inconsistencies in style, design and complexity according to `PEP8`_
guidelines. It also checks for compliance with Python docstring conventions
according to `PEP257`_ and supports `mypy`_ type-checking if type hints are
used in the code.

The workflow runs whenever Python code is to be committed to a git repository
which has it installed.

Initial Setup
-------------

To configure your project to use this automated Python workflow, copy the
configuration files from this repository to the top-level directory of your
project's git repository:

- ``.pre-commit-config.yaml`` for `pre-commit`_. Specifies which git hooks will
  be run before committing to the repo.
- ``pyproject.toml`` contains configuration for `black`_, The Uncompromising
  Python Code Formatter. This can also contain configuration if you use advanced
  build systems such as C++ compilation (e.g. `pybind11`_) for your Python
  module, so don't overwrite this file if it's already there.
- ``.flake8`` for `flake8`_, a tool for enforcing PEP8-based style guide for
  Python.
- ``.pydocstyle.ini`` for `pydocstyle`_, a tool for enforcing PEP257-based
  doc-string style guides for Python.
- You can also have a ``mypy.ini`` file for mypy, but the default settings are
  relatively sane so this may be unnecessary.

Install Prerequisites
---------------------

Although ``black``, ``flake8``, ``mypy`` and ``pydocstyle`` are used, the only
prerequisite is **pre-commit** as the configuration file is set up so that
when the pre-commit hooks are installed, all dependencies are automatically
installed. (Note, they won't be available to you in Python, they will be used
only by pre-commit. If you want to use them separately, you'll need to install
them individually with pip.)

**pre-commit** is a framework for managing git hooks.

Install **pre-commit** by running:

  .. code-block:: bash

    $ pip install pre-commit

It recommended to list **pre-commit** as a requirement for your project in
requirements.txt (or requirements-dev.txt):

  .. code-block::

    pre-commit

Generate pre-commit Git Hooks
-----------------------------

To generate the git hooks,  run the following in your project directory. Note
that the ``.pre-commit-config.yaml`` file must be in your project directory
**before** generating the git hooks.

  .. code-block:: bash

    $ pre-commit install

After this, ``pre-commit`` will run automatically on ``git commit`` with the
installed hooks.

.. _PEP8: https://www.python.org/dev/peps/pep-0008/
.. _PEP257: https://www.python.org/dev/peps/pep-0257/
.. _pre-commit: https://pre-commit.com/
.. _black: https://github.com/psf/black
.. _flake8: https://flake8.pycqa.org/en/latest/
.. _pydocstyle: http://www.pydocstyle.org/
.. _mypy: https://mypy.readthedocs.io/en/stable/index.html
.. _pybind11: https://pybind11.readthedocs.io/