<!-- omit in toc -->
# Introduction
Take note of some tips to solve problems.

<br />

<!-- omit in toc -->
# Table of Contents
- [Customize string format by two variables](#customize-string-format-by-two-variables)
- [join](#join)
- [how to write converters to translate variables](#how-to-write-converters-to-translate-variables)
- [check if the type of variable is the same as a specific type](#check-if-the-type-of-variable-is-the-same-as-a-specific-type)
- [double kwargs at the same time](#double-kwargs-at-the-same-time)
- [use two pointers and avoid stopping at the first case - all equal to zero](#use-two-pointers-and-avoid-stopping-at-the-first-case---all-equal-to-zero)
- [Connection](#connection)
  - [make sure connections are closed even if error occurs](#make-sure-connections-are-closed-even-if-error-occurs)

# Customize string format by two variables

> ' `StockID` = "0050" , `TradeVolume` = "18437079"  '

```python
    update_sql = ",".join(
        [
            ' `{}` = "{}" '.format(
                colname[i],
                str(value[i]),
            )
            for i in range(len(colname))
            if str(value[i])
        ]
    )
```

> 'INSERT INTO `test_table`(`StockID`,`TradeVolume`,`Transaction`,`TradeValue`,`Open`,`Max`,`Min`,`Close`,`Change`,`date`)VALUES ("0050","18437079") ON DUPLICATE KEY UPDATE  `StockID` = "0050" , `TradeVolume` = "18437079" \n            '

```python
    sql = (
        """INSERT INTO `{}`({}) VALUES ({}) ON DUPLICATE KEY UPDATE {}"""
        .format(
            table,
            '`{}`'.format('`,`'.join(data_columns)),
            '"{}"'.format('","'.join(value)),
            update_sql # = `StockID` = "0050" , `TradeVolume` = "18437079"
        )
    )

```


# join

```python
    names = ['Adam', 'Bob', 'Cyril']
    nl = '\n'
    text = f"Winners are:{nl}{nl.join(names)}"
    print(text)

```

# [how to write converters to translate variables](https://github.com/PyMySQL/PyMySQL/blob/main/pymysql/converters.py)
* pymysql/converters.py

```python
    _escape_table = [chr(x) for x in range(128)]
    _escape_table[0] = "\\0"
    _escape_table[ord("\\")] = "\\\\"
    _escape_table[ord("\n")] = "\\n"
    _escape_table[ord("\r")] = "\\r"
    _escape_table[ord("\032")] = "\\Z"
    _escape_table[ord('"')] = '\\"'
    _escape_table[ord("'")] = "\\'"


    def escape_string(value, mapping=None):
        """escapes *value* without adding quote.
        Value should be unicode
        """
        return value.translate(_escape_table)

```

# check if the type of variable is the same as a specific type

```python
    isinstance(sql, list)
```

# double kwargs at the same time
response = session.get(
            url, params={**params, **{"offset": offset, "limit": batch_size}}
        )

# use two pointers and avoid stopping at the first case - all equal to zero 
```python
    # total, offset are all integers
        offset = 0
        total = None
        while total is None or offset < total:  
            offset += batch_size
            total = response_json['total']

```

# Connection
## make sure connections are closed even if error occurs
