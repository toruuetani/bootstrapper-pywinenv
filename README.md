# bootstrapper-pywinenv
The windows batch file to bootstrap for python environment.

This batch file `bootstrap.bat` executes following steps.

* If option `clean` is specified like `bootstrap clean`, clean existing .venv directory.
* If not exist .venv directory, execute following steps.
  * Check python version via py.exe. If version is not match, this batch is canceled.
  * Check pip version via py.exe. If version is not match, pip will be updated.
  * Check poetry version via py.exe. If version is not match, poetry will be installed or updated.
  * If .venv is not exist, create venv.
  * Activate venv.
  * Check pip version in venv. If version is not match, pip will be updated.
  * Check poetry version in venv. If version is not match, poetry will be installed or updated.
  * Syncronize venv library via poetry.
    * If `poetry.lock` and `pyproject.toml` are not exist, execute `poetry init` and install pytest, flake8, black, and mypy for developping.
* Activate venv.
