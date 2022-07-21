<!-- omit in toc -->
# Introduction
WIP
<br />

<!-- omit in toc -->
# Table of Contents
- [Packages](#packages)
  - [1. click](#1-click)
  - [argparse](#argparse)
- [Commands](#commands)
  - [click](#click)
    - [1. click.command()](#1-clickcommand)
    - [2. click.option()](#2-clickoption)
  - [argparse](#argparse-1)

<br />


# Packages

## 1. [click](https://click.palletsprojects.com/en/8.1.x/)
* handle parsing and validating arguments from CLI commands

<br />

## argparse


<br />

# Commands 
## click
### 1. click.command()
* convert functions to be executed with arguments in CLI command

<br />

### 2. click.option()
* tell the click library which arguments to be accepted and what types of values are accepted

<br />

## argparse

```python
  import argparse
  parser = argparse.ArgumentParser()
  parser.add_argument('-n', type=int, default=1)
  parser.add_argument('number', type=int, nargs='?', default=34)
  parser.add_argument('test', type=int, nargs='+', default=34)
  args = parser.parse_args()

  # args.n, args.number
```
* `nargs`
* `-`: options. see `--help` 