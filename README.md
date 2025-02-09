# simple-modern-poetry

`simple-modern-poetry` is a minimal, modern **Python project template** for new
projects. It seemed surprisingly hard to find a good, simple, and modern one so I'm
sharing what I came up with.

It should be a good base for serious projects but also understandable so a new Python
developer can use it for even small projects.

It aims to be modern and absolutely as simple as possible and ready to use:

- Modern [**Poetry 2.0**](https://github.com/python-poetry/poetry) setup with
  [dynamic versioning](https://github.com/mtkennerly/poetry-dynamic-versioning) to make
  releases easier along with the
  [shell](https://github.com/python-poetry/poetry-plugin-shell), and
  [up](https://github.com/MousaZeidBaker/poetry-plugin-up) plugins.

- Simple **GitHub CI workflow** including **publishing to PyPI**. To publish a release,
  just create a release on GitHub.

- Standard, modern linting, formatting, and testing with
  [**black**](https://github.com/psf/black),
  [**ruff**](https://github.com/charliermarsh/ruff),
  [**usort**](https://github.com/facebook/usort),
  [**mypy**](https://github.com/python/mypy),
  [**codespell**](https://github.com/codespell-project/codespell), and
  [**pytest**](https://github.com/pytest-dev/pytest).

- A starter readme (here and in the template) with handy reminders on setup and basic
  workflow.

It doesn't have lots of options or try to use every bell and whistle.
It just adds the above essential things that should be in place for any new Python
project.

## How To Use This Template

### Option 1: GitHub Template

Just use
[**this template repository**](https://github.com/jlevy/simple-modern-poetry-template),
which is the output of this template.

Go there and hit the "Use this template" button.
Once you have the code, search for `_changeme_` for all field names like project name,
author, etc. You may also want to change the license/copyright.

### Option 2: Use Copier

This template uses [**copier**](https://github.com/copier-org/copier), which seems like
the best tool nowadays for project templates.

This is the recommended approach since it then lets you instantiate the template
variables, but it requires a few more commands.

To create a new project repo with `copier`:

```shell
# Ensure you have Python 3.11+ and pipx installed. (If not, see below.)

# Install copier:
pipx install copier

# Clone this template:
copier copy gh:jlevy/simple-modern-poetry your-project-name
# Then follow the instructions.
```

You can enter names for the project, description, etc., or just press enter and later
look for `_changeme_` in the code.

Once you have the template set up, you will need to check the code into Git for Poetry
to work. [Create a new GitHub
repo](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)
and add your initial code:

```shell
cd PROJECT
git init
# Adjust code. 
# Remember to look for any unfilled _changeme_ strings and confirm the LICENSE file!
git add .
git commit -m "Initial commit from simple-modern-poetry."
# Create repo on GitHub.
git remote add origin git@github.com:OWNER/PROJECT.git  # or https://github.com/...
git branch -M main
git push -u origin main
```

## Using the Template

The
[**default template readme**](https://github.com/jlevy/simple-modern-poetry-template)
covers the install and build workflows.
It's just poetry and a tiny Makefile with shortcuts.
It also has concise documentation on installing Python and Poetry, to save time for you
or your users.

## Why this Template?

Poetry is likely the best package manager for most new projects.
Those who love the very latest tools should consider
[**uv**](https://github.com/astral-sh/uv) instead of Poetry, but currently (early 2025)
tool support, such as GitHub workflows and dependabot, still seem much better for
Poetry.

Assuming you want to use Poetry, there are several other good templates, such as
[cookiecutter-poetry](https://github.com/fpgmaas/cookiecutter-poetry) and
[poetry-copier](https://github.com/lukin0110/poetry-copier) you may wish to consider.

This template takes a different philosophy.
I found existing ones to be out of date or have lots of options and scaffolding for
different frameworks.
That's hard to maintain in the template repo and overwhelming to read at first.
This is intended instead to be a very simple base.
You can add to it if you want.

## Contributing

PRs welcome on [this repository](https://github.com/jlevy/simple-modern-poetry) (not on
the GitHub template repo, which mirrors this one).
Please use the Discussions tab with your feedback, questions, or suggestions!
