<!-- omit in toc -->
# Introduction
Take note of path

<br />

<!-- omit in toc -->
# Table of Contents
- [Packages](#packages)
  - [pathlib](#pathlib)
- [Commands](#commands)
  - [import Path class](#import-path-class)
  - [Instantiate the current directory as a Path](#instantiate-the-current-directory-as-a-path)
  - [glob](#glob)
  - [mkdir](#mkdir)
  - [os.path.join(os.path.dirname(__file__), "..", "dags/**.py")](#ospathjoinospathdirnamefile--dagspy)
  - [path.parent](#pathparent)

<br />

# Packages
## pathlib
*  to represent **filesystem** paths with semantics appropriate for **different operating systems**

<br />

# Commands

## import Path class
    from pathlib import Path

## Instantiate the current directory as a Path
    p = Path('.')

## glob

    # globing the files with the pattens of Python scripts
    list(p.glob('**/*.py'))

## mkdir
    p.mkdir(mode=0o777, parents=False, exist_ok=False)


## os.path.join(os.path.dirname(__file__), "..", "dags/**.py")
https://github.com/dokelung/Python-QA/blob/master/questions/standard_lib/Python%20%E7%8D%B2%E5%8F%96%E6%96%87%E4%BB%B6%E8%B7%AF%E5%BE%91%E5%8F%8A%E6%96%87%E4%BB%B6%E7%9B%AE%E9%8C%84(__file__%20%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95).md

## path.parent
get the parent directory