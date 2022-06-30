<!-- omit in toc -->
# Introduction
How to use Path in python?

<br />

<!-- omit in toc -->
# Table of Contents
- [Packages](#packages)
  - [1. pathlib](#1-pathlib)
- [Commands](#commands)
  - [1. import Path class](#1-import-path-class)
  - [2. Instantiate the current directory as a Path](#2-instantiate-the-current-directory-as-a-path)
  - [3. glob](#3-glob)
  - [4. mkdir](#4-mkdir)
  - [5. os.path.join(os.path.dirname(__file__), "..", "dags/**.py")](#5-ospathjoinospathdirnamefile--dagspy)
  - [6. path.parent](#6-pathparent)

<br />

# Packages

## 1. pathlib
*  to represent **filesystem** paths with semantics appropriate for **different operating systems**

<br />

# Commands

## 1. import Path class
    from pathlib import Path

## 2. Instantiate the current directory as a Path
    p = Path('.')

## 3. glob

    # globing the files with the pattens of Python scripts
    list(p.glob('**/*.py'))

## 4. mkdir
    p.mkdir(mode=0o777, parents=False, exist_ok=False)


## 5. os.path.join(os.path.dirname(__file__), "..", "dags/**.py")
https://github.com/dokelung/Python-QA/blob/master/questions/standard_lib/Python%20%E7%8D%B2%E5%8F%96%E6%96%87%E4%BB%B6%E8%B7%AF%E5%BE%91%E5%8F%8A%E6%96%87%E4%BB%B6%E7%9B%AE%E9%8C%84(__file__%20%E7%9A%84%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95).md

## 6. path.parent
get the parent directory