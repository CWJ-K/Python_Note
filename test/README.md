<!-- omit in toc -->
# Introduction
Take note of Pytest

<br />

<!-- omit in toc -->
# Table of Contents
- [Files](#files)
  - [.coveragerc](#coveragerc)
- [Packages](#packages)
  - [pytest-cov](#pytest-cov)
  - [pytest-mock](#pytest-mock)
- [Commands](#commands)
  - [install pytest](#install-pytest)
  - [run pytest](#run-pytest)
  - [check configurations in pytest.ini](#check-configurations-in-pytestini)
  - [mocker](#mocker)
  - [fast api](#fast-api)
  - [test too slow](#test-too-slow)
  - [log in pytest](#log-in-pytest)

<br />

# Files
## .coveragerc
* omit (multi-string): a list of file name patterns, the files to leave out of measurement or reporting
* example: omit __init__.py

    [run]
    omit =
        */__init__.py

<br />

# Packages
## pytest-cov
## pytest-mock

<br />

# Commands
## install pytest 

    pipenv install pytest

    # test coverage
    pipenv install pytest-cov pytest-mock

## run pytest
    pipenv run pytest test_sampel.py

    # with test coverage
    pipenv run pytest --cov-report term-missing --cov-config=.coveragerc --cov=./<directory_with_functions_to_be_tested>/ tests/

## check configurations in pytest.ini
    pytest --help


## mocker

    mock_requests = mocker.patch(
        "financialdata.crawler.taiwan_stock_price.requests"
    )
    mock_requests.get.return_value = ""





## fast api
https://fastapi.tiangolo.com/tutorial/testing/


## test too slow
https://stackoverflow.com/questions/3824762/how-slow-is-too-slow-for-unit-tests

## [log in pytest](https://stackoverflow.com/questions/4673373/logging-within-pytest-tests)
pytest -o log_cli=true