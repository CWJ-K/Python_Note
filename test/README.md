<!-- omit in toc -->
# Introduction
Take note of Pytest

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [monkey-patched](#monkey-patched)
- [Files](#files)
  - [.coveragerc](#coveragerc)
- [Packages](#packages)
  - [pytest](#pytest)
    - [fixtures](#fixtures)
      - [tmp_path](#tmp_path)
  - [pytest-cov](#pytest-cov)
  - [pytest-mock](#pytest-mock)
    - [Goal:](#goal)
    - [How:](#how)
- [Commands](#commands)
  - [install pytest](#install-pytest)
  - [install pytest-mock, pytest-cov](#install-pytest-mock-pytest-cov)
  - [run pytest](#run-pytest)
  - [check configurations in pytest.ini](#check-configurations-in-pytestini)
  - [mocker](#mocker)
    - [monkey-patched](#monkey-patched-1)
    - [substitute a call to an external system](#substitute-a-call-to-an-external-system)
  - [fast api](#fast-api)
  - [test too slow](#test-too-slow)
  - [log in pytest](#log-in-pytest)
  - [pytest decorators](#pytest-decorators)
- [import path](#import-path)

<br />

# Fundamental Concepts
## monkey-patched


# Files
## .coveragerc
* omit (multi-string): a list of file name patterns, the files to leave out of measurement or reporting
* example: omit __init__.py

    [run]
    omit =
        */__init__.py

<br />

# Packages
## pytest
### fixtures
#### tmp_path
* create a temp path for testing functions about storing results
* after assert output_data = input_data in the temp path, the temp path and its contents are removed
## pytest-cov
## pytest-mock
* a faking operations or objects
### Goal: 
* tests should be isolated from each other => database connections should not be shared between tests

### How:
* tells Python to return a certain value instead of making the actual call to the database  


<br />

# Commands
## install pytest 

    pipenv install pytest

## install pytest-mock, pytest-cov
    # test coverage
    pipenv install pytest-cov pytest-mock

## run pytest
    pipenv run pytest test_sampel.py

    # with test coverage
    pipenv run pytest --cov-report term-missing --cov-config=.coveragerc --cov=./<directory_with_functions_to_be_tested>/ tests/

## check configurations in pytest.ini
    pytest --help


## mocker
### monkey-patched
    mock_requests = mocker.patch(
        "financialdata.crawler.taiwan_stock_price.requests"
    )
    mock_requests.get.return_value = ""

### substitute a call to an external system

    mock_get = mocker.patch.object()




## fast api
https://fastapi.tiangolo.com/tutorial/testing/


## test too slow
https://stackoverflow.com/questions/3824762/how-slow-is-too-slow-for-unit-tests

## [log in pytest](https://stackoverflow.com/questions/4673373/logging-within-pytest-tests)
pytest -o log_cli=true


## pytest decorators
* enables parametrization of arguments for a test function
  => make parameters as arguments into a test function

    pytest.mark.parametrize

# import path
https://stackoverflow.com/questions/25827160/importing-correctly-with-pytest