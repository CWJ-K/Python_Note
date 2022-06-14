<!-- omit in toc -->
# Goal of package
Packaging a Python project helps import a project without concerning developing environments. It implies you can directly use a project.

<br />

<!-- omit in toc -->
# Table of Contents

# [Distribute Tools](https://packaging.python.org/en/latest/tutorials/packaging-projects/)
## [distutils](https://www.gushiciku.cn/pl/gOIm/zh-tw)
* setup.py
* Methods
  1. write a `setup.py`
  2. `pipenv install -e .`
  3. in `pipfile`, there will be an line - `project_name = {editable=true,patth="."}` 
* set the version number in the “setup.py” in [CICD](https://medium.com/vlmedia-tech/step-by-step-guide-to-create-python-library-using-ci-cd-pipeline-8e66022108df)