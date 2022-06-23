<!-- omit in toc -->
# Introduction
Take note of different methods of string representation.

<br />

<!-- omit in toc -->
# Table of Contents
- [f-string](#f-string)
- [format](#format)



# f-string
* f-string expression part cannot include a [backslash](https://www.python.org/dev/peps/pep-0498/#escape-sequences)

    f'{\n}'

  * assign \ to other variable

        n = '\n'
        f'{n}'


# format
* [backslash](https://stackoverflow.com/a/44780840)

    '{}'.format('\n')