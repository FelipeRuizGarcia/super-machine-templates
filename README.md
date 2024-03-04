# Super Machine Templates

Configs and Templates to configure infra and software,
This files are designed to smooth integration with `super-machine-setup`

### Common Modules

@(Simple implementation across multiple projects)

**Modules** repository enable the best of the common multiple projects encapsulated and ready to be implement in your project in an easy, scalable and flexible way.

Pros:

-   Centralization: Avoid duplicated libraries repo by repo.
-   Import the core and best functionalities easily.
-   This repo can be use as Template for coming repos.

# Developer Tools

## Initial setup

-   Navigate to the root of the project
-   Create a virtual environment in the root folder by calling `virtualenv -p 3 ~/tmp/venv_modules`
-   Activate it by executing `source ~/tmp/venv_modules/bin/activate`
-   -   or - use your virtual environment
-   make sure that you are using the virtualenv with `which pip3`, it should point to the venv_modules dir
-   Install developer tools by executing `pip3 install -r requirements-dev.txt`
-   Do an one-time call of `pre-commit install`

Next time you restart the console, do run the `source ~/tmp/venv_modules/bin/activate`
This project uses https://pre-commit.com/ to do a linting and validation. It acts as a git pre commit hook.

## Code commit checks

Each time you stage your changes and commit your code, a code-commit hook will be triggered. It will:

-   Upgrade your syntax to the new Python syntax using https://github.com/asottile/pyupgrade
-   Run black formatter against your code
-   Run spell checking of your code though https://github.com/codespell-project/codespell
-   Run flake8 lining
-   Run bandit against your code to check for the security issues https://github.com/PyCQA/bandit
-   Run isort to automatically sort dependencies https://github.com/PyCQA/isort
-   Check all executables has a sheband
-   Run yaml linting
-   Run minimal prettier
-   Run mypy to do a type checking against your code
-   Deny from committing into the `master` branch

If you feel trapped and can't make it through, run `git commit --no-verify`

You can run pre-commit with the the current upstream code, for example
to run pre-commit in the HEAD

```
pre-commit run --from-ref HEAD~1 --to-ref HEAD
```

## Configuration files

-   .pre-commit-config.yaml
-   .yamllint
-   bandit.yaml

References:

https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/creating-a-template-repository
