# clean-poetry-template

This is a minimal, modern Python project template using
[copier](https://github.com/copier-org/copier):

- Modern Poetry 2.0 setup with
  [dynamic versioning](https://github.com/mtkennerly/poetry-dynamic-versioning)
  to make releases easier along with the
  [shell](https://github.com/python-poetry/poetry-plugin-shell),
  and [up](https://github.com/MousaZeidBaker/poetry-plugin-up) plugins.

- Simple GitHub CI workflow including publishing to PyPI.
  To publish a release, just create a release on GitHub.

- Standard, modern linting, formatting, and testing with black, ruff,
  usort, mypy, codespell, and pytest.

- A starter readme with reminders on setup and basic workflow.

It aims to be absolutely as simple as possible and ready to use.

It doesn't have lots of options or things you need to fill in.
It just configures Poetry and adds the above essential dev setup
that should be in place for any modern Python project.

To use:

```shell
pipx install copier
copier jlevy/clean-poetry-template my-project-name
```

Then create a new GitHub repo and add it:

```shell
cd my-project-name
git init
git add .
git commit -m "Initial commit from clean-poetry-template."
git branch -M main
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin main
```