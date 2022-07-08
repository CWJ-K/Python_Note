<!-- omit in toc -->
# Goal of package
TODO
Packaging a Python project helps import a project without concerning developing environments. It implies you can directly use a project.

<br />

<!-- omit in toc -->
# Table of Contents
- [Distribute Tools](#distribute-tools)
  - [1. distutils](#1-distutils)
  - [2. pyinstaller](#2-pyinstaller)
- [Examples](#examples)
- [The structure of directory](#the-structure-of-directory)
  - [1. set package_dir so the package can go through it to find code](#1-set-package_dir-so-the-package-can-go-through-it-to-find-code)
- [Commands](#commands)
  - [use pyinstaller to add other folders](#use-pyinstaller-to-add-other-folders)

<br />

# [Distribute Tools](https://packaging.python.org/en/latest/tutorials/packaging-projects/)

<br />

## 1. [distutils](https://www.gushiciku.cn/pl/gOIm/zh-tw)
* setup.py
* Methods
  1. write a `setup.py`
  2. `pipenv install -e .`
  3. in `pipfile`, there will be an line - `project_name = {editable=true,patth="."}` 
* set the version number in the “setup.py” in [CICD](https://medium.com/vlmedia-tech/step-by-step-guide-to-create-python-library-using-ci-cd-pipeline-8e66022108df)

## 2. pyinstaller
* package python scripts to an executable file (.exe)

<br />

# Examples
https://www.waynerv.com/cookiecutter-pypackage/

<br />

# The structure of directory
https://stackoverflow.com/questions/193161/what-is-the-best-project-structure-for-a-python-application/3419951

<br />

## 1. set package_dir so the package can go through it to find code
https://stackoverflow.com/questions/14417236/setup-py-renaming-src-package-to-project-name


# Commands
## use pyinstaller to add other folders
* some packages are not installed by pyinstaller. So, `--hidden-import` is used
1. make sure packages are installed in your environment
2. 
```s
  pyinstaller --onefile --hidden-import=pandas --add-data=roles/;./roles/  main.py

```
