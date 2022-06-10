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