---
title: Contributing to the codebase
excerpt: How to modify code and create pull requests
category: 6581eaa89a00e6001012822c
---

If you plan on making big changes to the codebase, the easiest way to make contributions is to install Letta directly from the source code (instead of via `pypi`, which you do with `pip install ...`).

Once you have a working copy of the source code, you should be able to modify the Letta codebase an immediately see any changes you make to the codebase change the way the `letta` command works! Then once you make a change you're happy with, you can open a pull request to get your changes merged into the official Letta package.

> 📘 Instructions on installing from a fork and opening pull requests
>
> If you plan on contributing your changes, you should create a fork of the Letta repo and install the source code from your fork.
>
> Please see [our contributing guide](https://github.com/cpacker/Letta/blob/main/CONTRIBUTING.md) for instructions on how to install from a fork and open a PR.

## Installing Letta from source

**Reminder**: if you plan on opening a pull request to contribute your changes, follow our [contributing guide's install instructions](https://github.com/cpacker/Letta/blob/main/CONTRIBUTING.md) instead!

To install Letta from source, start by cloning the repo:

```sh
git clone git@github.com:cpacker/Letta.git
```

### Installing dependencies with poetry (recommended)

First, install Poetry using [the official instructions here](https://python-poetry.org/docs/#installation).

Once Poetry is installed, navigate to the Letta directory and install the Letta project with Poetry:

```sh
cd Letta
poetry install --all-extras
poetry shell
```

Now when you want to use `letta`, make sure you first activate the `poetry` environment using poetry shell:

```sh
$ poetry shell
(pyletta-py3.10) $ letta run
```

Alternatively, you can use `poetry run` (which will activate the `poetry` environment for the `letta run` command only):

```sh
poetry run letta run
```

### Installing dependencies with pip

First you should set up a dedicated virtual environment. This is optional, but is highly recommended:

```sh
cd Letta
python3 -m venv venv
. venv/bin/activate
```

Once you've activated your virtual environment and are in the Letta project directory, you can install the dependencies with `pip`:

```sh
pip install -e '.[dev,postgres,local]'
```

Now, you should be able to run `letta` from the command-line using the downloaded source code (if you used a virtual environment, you have to activate the virtual environment to access `letta`):

```sh
$ . venv/bin/activate
(venv) $ letta run
```

If you are having dependency issues using `pip`, we recommend you install the package using Poetry. Installing Letta from source using Poetry will ensure that you are using exact package versions that have been tested for the production build.
