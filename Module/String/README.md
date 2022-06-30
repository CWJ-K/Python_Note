<!-- omit in toc -->
# Introduction
How to use different methods of string representation in Python?

<br />

<!-- omit in toc -->
# Table of Contents
- [Methods](#methods)
  - [f-string](#f-string)
  - [format](#format)

<br />

# Methods
## f-string
* f-string expression part cannot include a [backslash](https://www.python.org/dev/peps/pep-0498/#escape-sequences)

  ```python
  f'{\n}'
  ```

  * assign \ to other variables

  ```python
  n = '\n'
  f'{n}'
  ```

<br />

## format
* [backslash](https://stackoverflow.com/a/44780840)

  ```python
  '{}'.format('\n')
  ```