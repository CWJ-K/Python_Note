<!-- omit in toc -->
# Introduction
How to apply config files in Python?

<br />

<!-- omit in toc -->
# Table of Contents
- [Fundamental Concepts](#fundamental-concepts)
  - [1. ini files](#1-ini-files)
- [Packages](#packages)
  - [1. ConfigParser](#1-configparser)
- [Commands](#commands)
  - [1. Instantiated Configparser](#1-instantiated-configparser)
  - [2. read .ini](#2-read-ini)
  - [3. write .ini](#3-write-ini)
  - [4. inspect sections of .ini file](#4-inspect-sections-of-ini-file)

<br />

# Fundamental Concepts

## 1. [ini files](https://docs.python.org/3/library/configparser.html#supported-ini-file-structure)
* the file consists of sections, each of which contains keys with values
  
<br />

# Packages

## 1. ConfigParser
* can read and write .ini files

<br />

# Commands

## 1. Instantiated Configparser
    config = ConfigParser()

<br />

## 2. read .ini
    config.read("example.ini")

<br />

## 3. write .ini
    with open('example.ini', 'w') as configfile:
    ...   config.write(configfile)

<br />

## 4. inspect sections of .ini file 
    config.sections()
