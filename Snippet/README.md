<!-- omit in toc -->
# Introduction
Take note of some tips to solve problems

<br />

<!-- omit in toc -->
# Table of Contents


# Customize string format by two variables

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

    > ' `StockID` = "0050" , `TradeVolume` = "18437079"  '


# join

    names = ['Adam', 'Bob', 'Cyril']
    nl = '\n'
    text = f"Winners are:{nl}{nl.join(names)}"
    print(text)


# [how to write converters to translate variables](https://github.com/PyMySQL/PyMySQL/blob/main/pymysql/converters.py)
* pymysql/converters.py

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