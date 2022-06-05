
## run pytest
    pipenv run pytest test_sampel.py

    pipenv run pytest --cov-report term-missing --cov-config=.coveragerc --cov=./financialdata/ tests/

# check configurations in pytest.ini
    pytest --help


# .coveragerc
* omit (multi-string): a list of file name patterns, the files to leave out of measurement or reporting

# mocker
    mock_requests = mocker.patch(
        "financialdata.crawler.taiwan_stock_price.requests"
    )
    mock_requests.get.return_value = ""