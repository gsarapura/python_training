# Poetry 

Using [version 2.1](https://python-poetry.org/docs)

## Installation
- This case, using pipx since it's appropriate for CLI tools and it already creates a virutal environment

## Basic Usage
```bash
# Creating a new project
poetry new 01_poetry_automatic_demo

# Adding to existing project
cd 03_poetry_pre_existing_demo
poetry init

```
### Operating modes
1 - Package mode -> building sdist (source distribution, so it can be shared as gzip) or wheel (for packaging project so it can be published, for instance, in Pypi)
2 - Non package mode:
```toml
[tool.poetry]
package-mode = false
```
In this mode, metadata such as name and version are optional. Therefore, it is not possible to build a distribution or publish the project to a package index. Further, when running poetry install, Poetry does not try to install the project itself, but only its dependencies (same as poetry install --no-root).

[The pyproject.toml file](https://python-poetry.org/docs/pyproject/)

### Virtual environment
By default, Poetry creates a virtual environment in {cache-dir}/virtualenvs. You can change the cache-dir value by editing the Poetry configuration. Additionally, you can use the [virtualenvs.in-project](https://python-poetry.org/docs/configuration/#virtualenvsin-project) configuration variable to create virtual environments within your project directory.

There are several ways to run commands within this virtual environment.

External virtual environment management

Poetry will detect and respect an existing virtual environment that has been externally activated. This is a powerful mechanism that is intended to be an alternative to Poetry’s built-in, simplified environment management.

To take advantage of this, simply activate a virtual environment using your preferred method or tooling, before running any Poetry commands that expect to manipulate an environment.


### Committing your poetry.lock file to version control


## Commands
https://python-poetry.org/docs/cli/

```bash
poetry about

# Allow >=2.0.5, <3.0.0 versions
poetry add pendulum@^2.0.5
# Allow >=2.0.5, <2.1.0 versions
poetry add pendulum@~2.0.5
# Allow >=2.0.5 versions, without upper bound
poetry add "pendulum>=2.0.5"
# Allow only 2.0.5 version
poetry add pendulum==2.0.5

# The cache clear command removes packages from a cached repository.
# For example, to clear the whole cache of packages from the PyPI repository, run:
poetry cache clear PyPI --all
poetry cache list

# The check command validates the content of the pyproject.toml file and its consistency with the poetry.lock file. It returns a detailed report if there are any errors.
poetry check

poetry config --list

# Example of local configuration - poetry.toml will be created
poetry config virtualenvs.create false --local
poetry config virtualenvs.in-project true --local

# Check where is virtual env
poetry env info --path
```


