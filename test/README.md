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



    