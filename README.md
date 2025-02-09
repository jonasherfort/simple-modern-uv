# simple-modern-poetry

`simple-modern-poetry` is a minimal, modern **Python project template** for new
projects. It seemed surprisingly hard to find a good, simple, and modern one so I'm
sharing what I came up with.

It aims to be absolutely as simple as possible and ready to use:

- Modern [**Poetry 2.0**](https://github.com/python-poetry/poetry) setup with
  [dynamic versioning](https://github.com/mtkennerly/poetry-dynamic-versioning) to make
  releases easier along with the
  [shell](https://github.com/python-poetry/poetry-plugin-shell), and
  [up](https://github.com/MousaZeidBaker/poetry-plugin-up) plugins.

- Simple GitHub CI workflow including publishing to PyPI. To publish a release, just
  create a release on GitHub.

- Standard, modern linting, formatting, and testing with
  [**black**](https://github.com/psf/black),
  [**ruff**](https://github.com/charliermarsh/ruff),
  [**usort**](https://github.com/facebook/usort),
  [**mypy**](https://github.com/python/mypy),
  [**codespell**](https://github.com/codespell-project/codespell), and
  [**pytest**](https://github.com/pytest-dev/pytest).

- A starter readme (here and in the template) with handy reminders on setup and basic
  workflow.

It uses [**copier**](https://github.com/copier-org/copier), which seems like the best
tool nowadays for project templates.

It doesn't have lots of options or try to use every bell and whistle.
It just adds the above essential things that should be in place for any new Python
project.

Those who love the very latest tools might consider
[**uv**](https://github.com/astral-sh/uv) instead of Poetry, but tool support, including
GitHub workflows and dependabot, still seem much better for Poetry.

## How To Use This Template

It's recommended to use `copier` so you can instantiate the template variables.
But if you prefer, you can just [**use this GitHub template
repo**](https://github.com/jlevy/simple-modern-poetry-template) which is the output of
this template, with `_changeme_` for all field names like project name, author, etc.

To create the repo with `copier`:

```shell
# Ensure you have Python 3.11+ and pipx installed. (If not, see below.)

# Install copier:
pipx install copier

# Clone this template:
copier copy gh:jlevy/simple-modern-poetry my-new-project
```

You can enter names for project, description, etc., or just press enter and later look
for `_changeme_` in the code.

## Check Code Into GitHub

You now have the template set up.
But you will need to check the code into Git for Poetry to work.

For convenience, here is the quick cheat sheet commit to GitHub.
[Create a new GitHub
repo](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)
and add your initial code.

```shell
cd PROJECT
git init
# Adjust code. 
# Remember to look for any unfilled _changeme_ strings and confirm the LICENSE file!
git add .
git commit -m "Initial commit from simple-modern-poetry."
# Create repo on GitHub.
git remote add origin git@github.com:OWNER/PROJECT.git  # or https://...
git branch -M main
git push -u origin main
```

## Installing Python, pipx, and Poetry

Sadly, there are many, many ways to install and set up your Python environment, each
with its own pitfalls.

This is a quick cheat sheet for one of the simplest and most reliable ways to set up
**Python 3.11+** and **Poetry 2.0+** (what you should use as of 2025) using
[**pyenv**](https://github.com/pyenv/pyenv) and
[**pipx**](https://github.com/pypa/pipx).

For macOS:

```shell
brew update
brew install pyenv pipx
```

For Ubuntu:

```shell
curl https://pyenv.run | bash
apt install pipx
```

Now you can install a current Python and Poetry:

```shell
pyenv install 3.12.9  # Pick the version you want.
pipx install poetry
```

For Windows or other platforms, see the pyenv and poetry instructions (and I'd love a PR
to help me update these instructions for Windows!).

## Why this Template?

There are several other good templates, such as
[cookiecutter-poetry](https://github.com/fpgmaas/cookiecutter-poetry) and
[poetry-copier](https://github.com/lukin0110/poetry-copier) you may wish to consider.

This template takes a different philosophy.
I found existing ones to be out of date or have lots of options and scaffolding for
different frameworks.
That's hard to maintain in the template and overwhelming to read at first.
This is intended instead to be a very simple base.
You can add to it if you want.

## Contributing

PRs welcome. Please use the Discussions tab for questions or suggestions!
