# simple-modern-uv

[![As usual, XKCD has a comic for
this](https://imgs.xkcd.com/comics/python_environment.png)](https://xkcd.com/1987/)

(Approriately enough, this comic is out of date.)

Python installation and setup is notoriously confusing for both beginners and
experienced Python developers.

- In the beginning, there was a hack called
  [`setup.py`](https://github.com/pypa/setuptools) for packaging (1990s–2000s) and it
  was not good

- … then came [`virtualenv`](https://github.com/pypa/virtualenv),
  [`pip`](https://github.com/pypa/pip), and `requirements.txt` for isolated environments
  (2008–2011) yet confusion still reigned

- … and meanwhile, [`conda`](https://github.com/conda/conda),
  [`brew`](https://github.com/Homebrew/brew), and
  [`PyInstaller`](https://github.com/pyinstaller/pyinstaller) vied to rule the system
  installations (2010s)

- … until at last [`pyproject.toml`](https://github.com/pypa/pyproject.toml) matured and
  [`poetry`](https://github.com/python-poetry/poetry) and
  [`pipx`](https://github.com/pypa/pipx) promised peace and prosperity (2020s)

- … but new rebel forces [`uv`](https://github.com/astral-sh/uv) and
  [`pixi`](https://github.com/prefix-dev/pixi) aligned with Rust now gather strength …

* * *

## What is This?

**simple-modern-uv** is a minimal, modern **Python project template** for new projects
(Python 3.10–3.13). This template aims to be a good base for serious work but also
simple so it's an easy option for any small project.

It is still surprisingly hard to learn modern best practices for setting up Python
installations. This is a new **uv** template.

So I'm sharing a template that I am using myself as I migrate from Poetry to uv.
(See [simple-modern-poetry](https://github.com/jlevy/simple-modern-poetry) if you want a
recent Poetry template.)
I'd originally been a little hesitent to switch tooling, but the advantages of uv
(beyond it's touted speed) are getting to be too numerous to ignore.

This template aims to be "done right" with modern tools but still absolutely as simple
as possible:

- Modern [**uv**](https://github.com/astral-sh/uv) setup with
  [dynamic versioning](https://github.com/ninoseki/uv-dynamic-versioning/).

- Simple [**GitHub Actions**](https://github.com/actions/setup-python) CI workflow
  including (optional) **publishing to PyPI**. To publish a release, just create a
  release on GitHub.

- Standard, modern linting, formatting, and testing with
  [**black**](https://github.com/psf/black),
  [**ruff**](https://github.com/charliermarsh/ruff),
  [**usort**](https://github.com/facebook/usort),
  [**mypy**](https://github.com/python/mypy),
  [**codespell**](https://github.com/codespell-project/codespell), and
  [**pytest**](https://github.com/pytest-dev/pytest).

- A **starter readme** with handy reminders on Python setup/installation and basic dev
  workflows using to save time for you and users or collaborators.

- The whole template is **only ~300 lines of code** so you can read it and change what
  you want.

It doesn't have lots of options or try to use every bell and whistle.
It just adds the above essential things that should be in place for any new Python
project.

## When to Use This Template

It should work whenever you want to use modern Python and uv and have a build workflow
in GitHub. It does not handle:

- Using Docker (but you could add this later)

- Using [Conda](https://github.com/conda/conda) for dependencies (but note many deep
  learning libraries like PyTorch now support pip so this isn't as necessary as often as
  it used to be)

- Using a code repo or build system that isn't GitHub and GitHub Actions

(See [below](#alternatives) for other options.)

## How to Use This Template

> [!NOTE]
> 
> By default this template uses MIT license.
> If you want a different license or are not publishing your project as open source,
> update `license` in pyproject.yaml and the LICENSE file.
> If desired, you may delete the `.github/workflows/publish.yml` file if you are not
> publishing to PyPI.

The template can be used in two ways.
Option 1 is quickest.
For more flexibility, consider Option 2.

### Option 1: GitHub Template

Just use
[**this template repository**](https://github.com/jlevy/simple-modern-uv-template),
which is the output of this template.

Go there and hit the "Use this template" button.
Once you have the code, search for **`_changeme_`** for all field names like project
name, author, etc. You may also want to change the license/copyright.

### Option 2: Use Copier

This template uses [**copier**](https://github.com/copier-org/copier), which seems like
the best tool nowadays for project templates.
Using copier is the recommended approach since it then lets you instantiate the template
variables, but it requires a few more commands.

Note that copier also has the cool feature to [update your project
template](#updating-your-project-template) as this template improves in the future.

To create a new project repo with `copier`:

```shell
# Ensure you have Python 3.11+ and pipx installed. (If not, see below.)

# Install copier:
pipx install copier

# Clone this template:
copier copy gh:jlevy/simple-modern-uv your-project-name
# Then follow the instructions.
```

You can enter names for the project, description, etc., or just press enter and later
look for `_changeme_` in the code.

Once you have the template set up, you will need to check the code into Git for uv to
work. [Create a new GitHub
repo](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-new-repository)
and add your initial code:

```shell
cd PROJECT
git init
# Make license or other initial adjustments if needed.
git add .
git commit -m "Initial commit from simple-modern-uv."
# Create repo on GitHub.
git remote add origin git@github.com:OWNER/PROJECT.git  # or https://github.com/...
git branch -M main
git push -u origin main
```

## Getting Started on Your Project

In the template project itself, the
[**default readme**](https://github.com/jlevy/simple-modern-uv-template) and the file
[**development.md**](https://github.com/jlevy/simple-modern-uv-template) covers the
install and build workflows.

## Updating Your Project Template

If you use Option 2 or if you pick Option 1 and correctly fill in your
`.copier-answers.yml` file, you have the option to update your project with any future
updates to this template at any time.

If this file is updated with your project name etc., then you can
[update your project](https://copier.readthedocs.io/en/latest/updating/) to reflect any
changes to this template by running `copier update`.

## Alternatives

[**Poetry 2.0**](https://python-poetry.org/docs/basic-usage/) is a good option for
managing dependencies and is more mature so not as new as uv.
For [**Conda**](https://github.com/conda/conda) dependencies, also consider the newer
[**pixi**](https://github.com/prefix-dev/pixi/) package manager.

Currently (early 2025) uv is emerging as a far more powerful option.

Assuming you want to use uv, there are several other good templates, such as
[cookiecutter-uv](https://github.com/fpgmaas/cookiecutter-uv) and
[copier-uv](https://github.com/pawamoy/copier-uv) you may wish to consider.

This template takes a different more minimalist philosophy.
I found existing templates to have a lot of machinery you often don't need.
And it's hard to maintain a complex template repo.
This is intended instead to be a very simple base.
You can add to it if you want.

## Contributing

PRs welcome on [this repository](https://github.com/jlevy/simple-modern-uv) (not on the
GitHub template repo, which mirrors this one).
Please use the Discussions tab with your feedback, questions, or suggestions!
