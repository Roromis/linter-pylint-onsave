# linter-pylint-onsave
[![Build Status](https://travis-ci.org/Roromis/linter-pylint-onsave.svg?branch=master)](https://travis-ci.org/Roromis/linter-pylint-onsave)
[![Dependency Status](https://david-dm.org/Roromis/linter-pylint-onsave.svg)](https://david-dm.org/Roromis/linter-pylint-onsave)
[![Plugin installs!](https://img.shields.io/apm/dm/linter-pylint-onsave.svg)](https://atom.io/packages/linter-pylint-onsave)
[![Package version!](https://img.shields.io/apm/v/linter-pylint-onsave.svg?style=flat)](https://atom.io/packages/linter-pylint-onsave)

This package will lint your opened Python-files in Atom, using [pylint](http://www.pylint.org/).

This is a fork of the [linter-pylint](https://github.com/AtomLinter/linter-pylint/) package.

## Difference with linter-pylint

In order to lint files on the fly, linter-pylint executes pylint on a temporary file. This creates various issues, especially with relative imports. linter-pylint-onsave only lint files when they are saved, allowing it to work directly on the original file, as you would do if you used pylint directly.

## Installation

* Install [pylint](http://www.pylint.org/#install).
* `$ apm install linter-pylint-onsave`

## Configuration
* **Executable** Path to your pylint executable. This is useful if you have different versions of pylint for Python 2
  and 3 or if you are using a virtualenv. Use `%p` for the current project (no trailing /).
* **Message Format** Format for Pylint messages where `%m` is the message, `%i` is the numeric message ID (e.g. W0613)
  and `%s` is the human-readable message ID (e.g. unused-argument).
* **Python Path** Paths to be added to the `PYTHONPATH` environment variable. Use `%p` for the current project
  directory (e.g. `%p/vendor`) or `%f` for the directory of the current
  file location.
* **Rc File** Path to pylintrc file. Use `%p` for the current project directory or `%f` for the directory of the current
  file location.
* **Working Directory** Directory pylint is run from. Use `%p` for the current project directory or `%f` for the
  directory of the current file.
* `%p` will fallback to the current file's directory (equivilent to `%f`) if no project directory can be determined.

## Other available linters
There are other linters available - take a look at the linters [mainpage](https://github.com/AtomLinter/Linter).

## Changelog

### 1.1.0
- Allow use of project and file directories in rcfile, cwd, and PYTHONPATH (d82116d)
- Fix use of PYTHONPATH (7fb325)

### 1.0.0
- Use latest linter API

### 0.2.1
 - Use new API for project path

### 0.2.0
 - Settings to configure rcfile, executable name [#24](https://github.com/AtomLinter/linter-pylint/pull/24)

### 0.1.5
 - Fix lint message display on Windows [#15](https://github.com/AtomLinter/linter-pylint/issues/15)
 - Fix temporary file leak when pylint isn't present

### 0.1.3
 - Display pylint message ids
 - Fix debug mode [#9](https://github.com/AtomLinter/linter-pylint/issues/9)
 - Use project directory as cwd (works better with Atom projects)

### 0.1.2
 - fix 'has no method getCmd' bug [#4](https://github.com/AtomLinter/linter-pylint/issues/4)

### 0.1.0

 - Implemented first version of 'linter-pylint'
 - Added support for Errors and Warnings, "Refactor", "Convention and "Fatal"-messages are ignored due to missing display-capabilities.
