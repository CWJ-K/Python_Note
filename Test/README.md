<!-- omit in toc -->
# Introduction
How to use pytest to test functions?

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [1. monkey-patched](#1-monkey-patched)
- [Files](#files)
  - [1. coveragerc](#1-coveragerc)
- [Packages](#packages)
  - [1. pytest](#1-pytest)
    - [1.1. fixtures](#11-fixtures)
      - [1.1.1. tmp_path](#111-tmp_path)
  - [2. pytest-cov](#2-pytest-cov)
  - [3. pytest-mock](#3-pytest-mock)
    - [3.1. Goal:](#31-goal)
    - [3.2. How:](#32-how)
- [Commands](#commands)
  - [1. install pytest](#1-install-pytest)
  - [2. install pytest-mock, pytest-cov](#2-install-pytest-mock-pytest-cov)
  - [3. run pytest](#3-run-pytest)
  - [4. check configurations in pytest.ini](#4-check-configurations-in-pytestini)
  - [5. mocker](#5-mocker)
    - [5.1. monkey-patched](#51-monkey-patched)
    - [5.2. substitute a call to an external system](#52-substitute-a-call-to-an-external-system)
  - [6. fast api](#6-fast-api)
  - [7. test too slow](#7-test-too-slow)
  - [8. log in pytest](#8-log-in-pytest)
  - [9. pytest decorators](#9-pytest-decorators)
- [Issue](#issue)
  - [1. import path](#1-import-path)

<br />

# Fundamental Concepts

## 1. monkey-patched

<br />

# Files

## 1. coveragerc
* omit (multi-string): a list of file name patterns, the files to leave out of measurement or reporting
* example: omit __init__.py

    [run]
    omit =
        */__init__.py

<br />

# Packages

## 1. pytest

### 1.1. fixtures

#### 1.1.1. tmp_path
* create a temp path for testing functions about storing results
* after assert output_data = input_data in the temp path, the temp path and its contents are removed

## 2. pytest-cov

## 3. pytest-mock
* a faking operations or objects

### 3.1. Goal: 
* tests should be isolated from each other => database connections should not be shared between tests

### 3.2. How:
* tells Python to return a certain value instead of making the actual call to the database  


<br />

# Commands

## 1. install pytest 

  ```sh
  pipenv install pytest
  ```

<br />

## 2. install pytest-mock, pytest-cov
  ```sh
  # test coverage
  pipenv install pytest-cov pytest-mock
  ```

<br />

## 3. run pytest
  ```sh
  pipenv run pytest test_sampel.py

  # with test coverage
  pipenv run pytest --cov-report term-missing --cov-config=.coveragerc --cov=./<directory_with_functions_to_be_tested>/ tests/
  ```

<br />

## 4. check configurations in pytest.ini
  ```sh
  pytest --help
  ```

<br />

## 5. mocker

### 5.1. monkey-patched

  ```python
  mock_requests = mocker.patch(
      "financialdata.crawler.taiwan_stock_price.requests"
  )
  mock_requests.get.return_value = ""
  ```

<br />

### 5.2. substitute a call to an external system

  ```python
  mock_get = mocker.patch.object()
  ```

<br />

## 6. fast api
https://fastapi.tiangolo.com/tutorial/testing/

<br />

## 7. test too slow
https://stackoverflow.com/questions/3824762/how-slow-is-too-slow-for-unit-tests

<br />

## 8. [log in pytest](https://stackoverflow.com/questions/4673373/logging-within-pytest-tests)
pytest -o log_cli=true

<br />

## 9. pytest decorators
* enables parametrization of arguments for a test function
  => make parameters as arguments into a test function

    pytest.mark.parametrize

<br />

# Issue

## 1. import path

https://stackoverflow.com/questions/25827160/importing-correctly-with-pytest