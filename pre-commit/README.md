# Pre-commit

Git executes a set of [hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks "Git Hooks") before and after important actions. The user can customize this hooks to perform any kind of operations.

> There are two groups of these hooks: client-side and server-side. Client-side hooks are triggered by operations such as committing and merging, while server-side hooks run on network operations such as receiving pushed commits.
>
> -- <cite>https://git-scm.com/</cite>

One of those hooks is the pre-commit. Git executes the pre-commit hook before the commit step. Developers use the pre-commit hook to perform a quick check of the staged code. The user can check if the code has the correct format, passes the tests, or compiles correctly.

Using a pre-commit hook can save a lot of time for developers. Developers don't need to wait for the CI to check their code. Moreover, it prevents pushing and executing the CI multiple times due to a format issues.

The pre-commit can be customized using a shell script. Otherwise, there are tools to automatize the installation and execution of the pre-commit hooks. One of these tools is the [Pre-commit](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks "Pre-commit") tool. **Pre-commit** is a Python tool that offers an easy and quick configuration of a pre-commit that any developer can install and execute. Pre-commit is a multi-language package manager.

> We built pre-commit to solve our hook issues. It is a multi-language package manager for pre-commit hooks. You specify a list of hooks you want and pre-commit manages the installation and execution of any hook written in any language before every commit.
>
> -- <cite>https://pre-commit.com/</cite>

Pre-commit has a large library of plugins for multiple languages and formats. Developers can also develop and customize their plugins and create new hooks.

## Pre-commit Installation

Before running the pre-commit hook you need to install the Python package.

Using pip:

```sh
$ pip install pre-commit
```

## Pre-commit Configuration

Creat a new file in the project root named: `.pre-commit-config.yaml`.

*Example:*

```yaml
repos:
-   repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v2.3.0
    hooks:
    -   id: check-yaml
    -   id: end-of-file-fixer
    -   id: trailing-whitespace
```

## Pre-commit Execution

First, install the pre-commit to set up the git hooks scripts:

```sh
$ pre-commit install
```

Then, run the pre-commit:

```sh
$ pre-commit run --all-files
```

The pre-commit will execute the pre-commit hook automatically before your commits.

## Midokura Pre-commit

```
pre-commit
│   README.md
│   .pre-commit-config.yaml # Base Configuration
│
└───python
│   └─── .pre-commit-config.yaml # Python Configuration

└───java
│   └─── .pre-commit-config.yaml # Java Configuration
│
└───C
│   └─── .pre-commit-config.yaml # C Configuration
│
└───.github
    └───workflows
        └─── pre-commit.yaml # GitHub Workflow
```


## More Information

The following links can help you to learn more about the Git Hooks and the Pre-commit tool:

- https://pre-commit.com/
- https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks
